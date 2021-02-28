1. Go to https://github.com/minio/charts

2. To install single node, `helm install --namespace minio --generate-name minio/minio`.

3. Some commands:

```
 kubectl get secrets --namespace minio
  504  kubectl get secret minio-1614514927
  505  kubectl -n minio get secret minio-1614514927
  506  kubectl -n minio describe secret minio-1614514927 | less
  507  ACCESS_KEY=$(kubectl get secret minio-1614514927 -o jsonpath="{.data.accesskey}" | base64 --decode)
  508  ACCESS_KEY=$(kubectl get secret -ns minio minio-1614514927 -o jsonpath="{.data.accesskey}" | base64 --decode)
  509  ACCESS_KEY=$(kubectl get secret -n minio minio-1614514927 -o jsonpath="{.data.accesskey}" | base64 --decode)
  510  cat ACCESS_KEY
  511  echo ACCESS_KEY
  512  echo $ACCESS_KEY
  513  SECRET_KEY=$(kubectl get secret -n minio minio-1614459383 -o jsonpath="{.data.secretkey}" | base64 --decode)
  514  SECRET_KEY=$(kubectl get secret -n minio minio-1614514927 -o jsonpath="{.data.secretkey}" | base64 --decode)
  515  echo $SECRET_KEY
  516  brew install minio/stable/mc
  517  mc alias set minio-1614514927-local http://localhost:9000 "$ACCESS_KEY" "$SECRET_KEY" --api s3v4
  518  mc ls minio-1614514927-local
  519  mc -h
  520  mc mb "eric-test-1"
  521  mc ls
  522  ls
  523  mc rb eric-test-1
  524  man mc
  525  ls
  526  mc cd minio-1614514927-local
  527  mc ls play
  528  mc ls minio-1614514927-local
  529  mc mb minio-1614514927-local/eric-test-1
  530  ls
  531  mc ls
  532  mc cd eric-test-1
  533  mc cd minio-1614514927-local
  534  cd minio-1614514927-local
  535  touch hello_world.txt
  536  vim hello_world.txt
  537  mc cp hello_world.txt minio-1614514927-local/eric-test-1
  538  mc -h
  539  mc cat hello_world.txt minio-1614514927-local/eric-test-1/hello_world.txt
  540  mc --autocompletion
  541  source ~/.bashrc && source ~/.bash_profile
  542  mc rm hello_world.txt minio-1614514927-local/eric-test-1/hello_world.txt
  543  cat hello_world.txt
  544  mc rb minio-1614514927-local/eric-test-1/
  545  history
  ```
