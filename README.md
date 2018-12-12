# minio-raspberry-pi-s3-gateway
Minio on raspberry pi as s3 gateway


##on raspberry pi:


wget https://dl.google.com/go/go1.10.3.linux-armv6l.tar.gz
sudo tar -C /usr/local -xzf go1.10.3.linux-armv6l.tar.gz
export PATH=$PATH:/usr/local/go/bin # put into ~/.bash_profile
source .bash_profile
go get -u github.com/minio/minio
mkdir ~/minio-data
cd go/bin

export AWS_ACCESS_KEY_ID: "thekey"
export AWS_SECRET_ACCESS_KEY: "thesecret"

export MINIO_SECRET_KEY="akeyanykey"
export MINIO_ACCESS_KEY="anyaccesskeyhere"

./minio gateway s3

##Output should look like this:

Endpoint:  http://192.168.22.104:9000  http://127.0.0.1:9000
AccessKey: akeyanykey 
SecretKey: anyaccesskeyhere

Browser Access:
   http://192.168.24.104:9000  http://127.0.0.1:9000

Command-line Access: https://docs.minio.io/docs/minio-client-quickstart-guide
   $ mc config host add mys3 http://192.168.22.104:9000 Q3Aakeyanykey anyaccesskeyhere

Object API (Amazon S3 compatible):
   Go:         https://docs.minio.io/docs/golang-client-quickstart-guide
   Java:       https://docs.minio.io/docs/java-client-quickstart-guide
   Python:     https://docs.minio.io/docs/python-client-quickstart-guide
   JavaScript: https://docs.minio.io/docs/javascript-client-quickstart-guide
   .NET:       https://docs.minio.io/docs/dotnet-client-quickstart-guide
