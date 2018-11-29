# google-authenticator

Generate Google Authentication Codes with golang

```go
package main

import (
	"io/ioutil"
	"log"
	"os"

	"github.com/maurodelazeri/google-authenticator"
)

func main() {
	data, err := ioutil.ReadFile("secret")
	if err != nil {
		log.Print(err)
		os.Exit(1)
	}
	secret := string(data)
	otp := authenticator.GetTOTPToken(secret)
	log.Printf(otp)
}
```

```
$ go run main.go
2018/11/29 08:43:50 153071
```
