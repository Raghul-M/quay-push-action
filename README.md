


#  📤 Quay Push Action

[![GitHub release](https://img.shields.io/github/v/release/raghulm/quay-push-action)](https://github.com/raghulm/quay-push-action/releases) [![Marketplace](https://img.shields.io/badge/GitHub%20Actions-Quay--Push--Action-blue?logo=github-actions&logoColor=white)](https://github.com/marketplace/actions/quay-push-action) [![License: MIT](https://img.shields.io/badge/License-Apache2.0-green.svg)](LICENSE)

A lightweight and reusable GitHub  Action to **build and push Container images to Quay.io Registry**  perfect for CI/CD workflows that require seamless container registry integration within Github Workflows

![Streamlit -app (2)](https://github.com/user-attachments/assets/bbd8b40b-7bc1-4987-be78-6b81a4aaae59)




## 📦 Features

-  **Secure Login** with Quay.io using username/token
-  **Docker Image Build** using repo-root `Dockerfile` 
-  **Push to Quay** with auto-tagging using commit SHA
-  **Custom Tags** supported (`v1.0`, `latest`, etc.)


## 📌 Inputs

| Name             | Required | Description |
|------------------|----------|-------------|
| `quay_username`  | ✅ Yes   | Quay.io Registry username  |
| `quay_password`  | ✅ Yes   | Quay.io Registry password  |
| `repository_name`| ✅ Yes   | Full Quay.io repo (e.g., `raghul/app`) |
| `image_tag`      | ❌ No    | Tag name (e.g., `latest`, `v1.0`). Defaults to `commit SHA` |



## 📌 Sample Workflow

```yaml
name: Push to Quay.io

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Use Quay Push Action
        uses: raghul-m/quay-push-action@v1
        with:
          quay_username: ${{ secrets.QUAY_USERNAME }}
          quay_password: ${{ secrets.QUAY_PASSWORD }}
          repository_name: raghul-m/myapp
          image_tag: latest  # optional
````


## ⚠️ Prerequisites

* [x] A `Dockerfile` in your repo root
* [x] Add `QUAY_USERNAME` and `QUAY_PASSWORD` as **secrets**
* [x] Include `actions/checkout@v4` before this step



##  License

⚖️ This project is licensed under the [Apache 2.0 License](LICENSE).



## 🤝 Contribute

This project is open-source, and contributions are welcome! Feel free to submit issues, feature requests, or pull requests.

Got improvements or ideas? Open an [issue](https://github.com/Raghul-M/quay-push-action/issues) or submit a PR!

> If you found this useful, don't forget to ⭐ star the repo!



## 🙋‍♂ Maintainer

Made with ❤️ by [Raghul M](https://www.linkedin.com/in/m-raghul/)


