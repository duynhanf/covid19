# Cổng thông tin chống dịch CoVid-19 của TP Tokyo

![](https://github.com/tokyo-metropolitan-gov/covid19/workflows/production%20deploy/badge.svg)

[![Cổng thông tin chống dịch CoVid-19 của TP Tokyo](https://user-images.githubusercontent.com/1301149/75629392-1d19d900-5c25-11ea-843d-2d4376e3a560.png)](https://stopcovid19.metro.tokyo.lg.jp/)

### [日本語](./README.md) | [English](./README_EN.md) | [Spanish](./README_ES.md) | [Korean](./README_KO.md) | [Chinese (Taiwan)](./README_ZH_TW.md) | [Chinese (Simplified)](./README_ZH_CN.md) | [Vietnamese](./README_VI.md) | [Thai](./README_TH.md) | [French](./README_FR.md)

## Làm thế nào để đóng góp
Mọi đóng góp của các bạn đều được chào đón.
Xin vui lòng đọc [tại đây](./.github/CONTRIBUTING_VI.md) để biết thêm chi tiết.


## Quy tắc ứng xử
Chi tiết vui lòng xem [tại đây](./.github/CODE_OF_CONDUCT_VI.md)

## Giấy phép
Phần mềm này được phân phối dưới giấy phép [MIT](./LICENSE.txt)

Vui lòng check tài liệu này [How to translate](./.github/TRANSLATION.md)

## Thông tin cho nhà phát triển

### Xây dựng môi trường

- Node.js phiên bản: 10.19.0 hoặc cao hơn

**Nếu dùng yarn**
```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev
```

**Nếu dùng docker compose**
```bash
# serve with hot reload at localhost:3000
$ docker-compose up --build
```

### Trường hợp phát triển bằng VSCode và Remote Containers

1. Cài đặt [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension trong VSCode
2. Nếu chọn root repository này bằng menu 「Open Folder in Container」 phía dưới bên trái như [ảnh này（external link）](https://code.visualstudio.com/docs/remote/containers#_quick-start-try-a-dev-container) thì setup môi trường sẽ bắt đầu

#### Topic
- Trường hợpp muốn sửa setting, hãy sửa file `.devcontainer/devcontainer.json`.
Chi tiết thì hãy tham khảo file [devcontainer.jsonのリファレンス](https://code.visualstudio.com/docs/remote/containers#_devcontainerjson-reference)

- Mặc dù 「ESLint」 extension hợp lệ cài đặt chỉ khi chạy Remote Container nhưng khi cần thiết, hãy thêm vào `extensions` trong file `devcontainer.json`

Chi tiết hướng dẫn cài đặt thì bạn có thể tham khảo [tại đây(external link）](https://code.visualstudio.com/docs/remote/containers#_managing-extensions)
- Trường hợp muốn setup lại biến môi trường hãy chạy lại 「Rebuild Container」 phía dưới bên trái

### Detect production/others environment

On the production environment, `'production'` is assigned to `process.env.GENERATE_ENV` variable, on the other case `'development'` is assigned to the variable.  
Please use the variable to detect which enviroinment is used at the runtime.

[/PLEASE TRANSLATE ME]

### Triển khai lên môi trường staging và production

Khi nhánh `master` được cập nhật, file HTML sẽ tự động được build dựa trên nhánh `production`. Sau đó https://stopcovid19.metro.tokyo.lg.jp/ sẽ được cập nhật.

Khi nhánh `staging` được cập nhật, file HTML sẽ tự động được build dựa trên nhánh `gh-pages`. Sau đó https://stg-covid19-tokyo.netlify.com/ sẽ được cập nhật.

Khi nhánh `development` được cập nhật, file HTML sẽ tự động được build dựa trên nhánh `dev-pages`. Sau đó https://dev-covid19-tokyo.netlify.com/ sẽ được cập nhật.


[PLEASE TRANSLATE ME]

### Branch rules

Pull Request is allowed only for `development`, `dev-i18n` and `dev-hotfix`.  
Please use the following naming rules for the branch when sending a Pull Request.

Feature implementation: feature/#{ISSUE_ID}-#{branch_title_name}
Hotfix commit: hotfix/#{ISSUE_ID}-{branch_title_name}

#### Basic branch
| Purpose | Branch | Confirmation URL | Remarks |
| ---- | -------- | ---- | ---- |
| Development | development | http://dev-covid19-tokyo.netlify.com/ | base branch. Basically send a Pull Request here |
| Hotfix branch | dev-hotfix | None | Fixes that should be applied to production in haste. Use this if requested by the administrator |
| i18n working branch | dev-i18n | https://i18n-covid-tokyo.netlify.com/ | Temporarily used |
| Staging | staging | https://stg-covid19-tokyo.netlify.com/ | For final confirmation before production. Non-admin pull requests are prohibited |
Production | master | http://stopcovid19.metro.tokyo.lg.jp/ | Pull Requests other than Administrators are prohibited |

#### Branch used by the system
| Purpose | Branch | Confirmation URL | Remarks |
| ---- | -------- | ---- | ---- |
| Production site HTML | production | http://stopcovid19.metro.tokyo.lg.jp/ | Location where statically built HTML is located |
| Staging site HTML | gh-pages | https://stg-covid19-tokyo.netlify.com/ | Where to find statically built HTML |
| For OGP working directory | deploy / new_obp | None | For updating OGP |

[/PLEASE TRANSLATE ME]
