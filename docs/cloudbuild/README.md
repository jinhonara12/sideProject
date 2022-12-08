# Cloud Build란

## [공식 소개글](https://cloud.google.com/build/docs?hl=ko&_ga=2.128704780.-1845808227.1657200392)

> Cloud Build는 Google Cloud 인프라에서 빌드를 실행하는 서비스입니다. Cloud Build는 Cloud Storage, Cloud Source Repositories, GitHub 또는 Bitbucket에서 소스 코드를 가져오고, 사양에 맞게 빌드를 실행하고, Docker 컨테이너 또는 자바 아카이브와 같은 아티팩트를 생성할 수 있습니다.

# 관계도

![cloud build cicd](/docs/imgs/cloudbuild_1.png)

1. github에서 release branch로 `push` 발생
2. Cloud Build에서 설정한 Trigger가 `push` 를 인지하고 Build 실행
3. 필요한 package `install`, `build`, `test` 실행
   1. [cloudbuild.yaml 파일](https://cloud.google.com/build/docs/build-config-file-schema?hl=ko)을 참조하여 실행
4. 완료되면 App Engine 으로 deploy 실행
   1. [app.yaml 파일](https://cloud.google.com/appengine/docs/standard/reference/app-yaml?tab=python)을 참조하여 실행
5. App Engine에서 웹 서비스 배포됨

# Reference

- [Cloud Build 개요](https://cloud.google.com/build/docs/overview?hl=ko)
- [Cloud Build - 빌드 구성 파일 스키마](https://cloud.google.com/build/docs/build-config-file-schema?hl=ko)
- [App Engine - app.yaml 구성 파일](https://cloud.google.com/appengine/docs/standard/reference/app-yaml?tab=python)
