## Docker 이미지 빌드

## 소스 코드 저장소 만들기

1. Cloud Shell에서 샘플 소스 코드를 다운로드
```
cd ~
wget https://gke-spinnaker.storage.googleapis.com/sample-app-v2.tgz
```

2. 소스 코드의 압축을 풉니다.

```
tar xzfv sample-app-v2.tgz
```

3. 디렉터리를 소스 코드로 변경

```
cd sample-app
```

4. 이 저장소의 Git 커밋에 대한 사용자 이름과 이메일 주소를 설정

```
git config --global user.email "[EMAIL_ADDRESS]"
git config --global user.name "[USERNAME]"
```

5. 소스 코드 저장소에 대한 최초 커밋을 수행

```
git init
git add .
git commit -m "Initial commit"
```

6. 코드를 호스팅할 저장소를 만듭니다.

```
gcloud source repos create sample-app
git config credential.helper gcloud.sh
```

7. 새로 만든 저장소를 원격으로 추가

```
export PROJECT=$(gcloud info --format='value(config.project)')
git remote add origin https://source.developers.google.com/p/$PROJECT/r/sample-app
```

8. 새 저장소의 마스터 브랜치에 코드를 푸시

```
git push origin master
```

9. 콘솔에서 소스 코드를 볼 수 있는지 확인

```

```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```
