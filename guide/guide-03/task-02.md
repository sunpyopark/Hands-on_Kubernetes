## 애플리케이션 배포를 위한 GKE 만들기

Inline `code`

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code


1. Cloud Shell에서 새 GKE 클러스터를 만듭니다.

```
REGION=us-west1-b
gcloud config set compute/zone $REGION
gcloud container clusters create app-cluster \
--machine-type=n1-standard-2
```

2. 새 GKE 클러스터를 Spinnaker에 추가합니다

```
~/spinnaker-for-gcp/scripts/manage/add_gke_account.sh
```

3. kubernetes 컨텍스트를 다시 Spinnaker 클러스터로 변경

```
kubectl config use-context gke_${DEVSHELL_PROJECT_ID}_${REGION}_spinnaker-1
```

4. 구성 변경사항을 푸시하여 Spinnaker에 적용

```
~/spinnaker-for-gcp/scripts/manage/push_and_apply.sh
```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```
