# README file
echo "# Cryptography Basics Assignment" > README.md

# Symmetric encryption demo files
echo "Hello Cybersecurity World" > message.txt
openssl enc -aes-256-cbc -salt -in message.txt -out message.enc -pass pass:MySecretKey
openssl enc -aes-256-cbc -d -in message.enc -out decrypted.txt -pass pass:MySecretKey

# Asymmetric encryption demo files
echo "Confidential Data" > secret.txt
openssl genrsa -out private.pem 2048
openssl rsa -in private.pem -outform PEM -pubout -out public.pem
openssl rsautl -encrypt -inkey public.pem -pubin -in secret.txt -out secret.enc
openssl rsautl -decrypt -inkey private.pem -in secret.enc -out revealed.txt