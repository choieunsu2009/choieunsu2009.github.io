# Choies Blog

[Chirpy Starter](https://github.com/cotes2020/chirpy-starter)를 바탕으로 만든 Jekyll 블로그입니다.

- 예정 주소: `https://blog.choies.kr`
- GitHub 저장소: `https://github.com/choieunsu2009/choieunsu2009.github.io`
- 글 위치: `_posts/YYYY-MM-DD-title.md`

## 로컬 실행

Ruby 3.4와 Bundler를 설치한 뒤 다음 명령을 실행합니다.

```sh
bundle install
bundle exec jekyll serve
```

사이트는 `http://127.0.0.1:4000`에서 확인할 수 있습니다.

## GitHub Pages 배포

`main` 브랜치에 푸시하면 `.github/workflows/pages-deploy.yml`이 사이트를 빌드하고 배포합니다. GitHub 저장소의 **Settings → Pages → Build and deployment → Source**를 **GitHub Actions**로 설정해야 합니다.

## `blog.choies.kr` 연결

1. 저장소 **Settings → Pages → Custom domain**에 `blog.choies.kr`를 등록합니다.
2. Cloudflare DNS에서 `blog`의 CNAME 레코드를 `choieunsu2009.github.io`로 지정하고 **Proxy status**를 **DNS only**로 설정합니다.
3. GitHub Pages에서 DNS 확인과 인증서 발급이 끝나면 **Enforce HTTPS**를 켭니다.

이 저장소의 배포 방식은 GitHub Actions입니다. GitHub Pages의 사용자 지정 도메인은 위 Pages 설정에서 등록해야 합니다. `_config.yml`의 `url`은 사이트가 생성하는 링크와 메타데이터에 쓰입니다.

## 출처

Chirpy Starter의 [MIT 라이선스](LICENSE)를 따릅니다.
