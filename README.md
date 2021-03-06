<h1 align="center">
  <br>
  <a href=""><img src="https://github.com/Shivangx01b/LfiMe/blob/main/static/logo.png" alt="" width="200px;"></a>
  <br>
  <img src="https://img.shields.io/github/languages/top/Shivangx01b/BountyIt?style=flat-square">
  <a href="https://goreportcard.com/report/github.com/Shivangx01b/BountyIt"><img src="https://goreportcard.com/badge/github.com/Shivangx01b/BountyIt"></a>
  <a href="https://twitter.com/intent/follow?screen_name=shivangx01b"><img src="https://img.shields.io/twitter/follow/shivangx01b?style=flat-square"></a>
</h1>

## What is BountyIt ?
A fuzzer made in golang for finding issues like xss, lfi, rce, ssti...that detects issues using change in content length and verify it using signatures.

## Help
```
-grep string
        Specify custom grepping signatures. Ex -grep signatures.txt
  -header string
        Add any custom header if required. Ex: -header "Cookie: Session=12cbcx...."
  -method string
        Add method name if required. Ex: -method PUT. Default "GET" (default "GET")
  -p string
        Feed the list of payloads to fuzz. Ex: -p ~/wordlists/lfi.txt
  -t int
        Number of workers to use..default 40. Ex: -t 50 (default 40)
  -verify
        Only prints confirmed results. Ex -verify

```

## How to Install

```
$ go get -u -v github.com/shivangx01b/BountyIt
```
## Usage

- Note:
 Urls must have keyword "FUZZ" like
 ```
 https://example.com/FUZZ 
        or 
 https://example.com/?query=FUZZ
 ```

Single Url
```plain
echo "https://example.com/FUZZ" | BountyIt
```
Multiple Url
```plain
cat http_https.txt | BountyIt -t 70 -p payloads.txt -verify
```
Add another method if required
```plain
cat http_https.txt | BountyIt -t 70  -method "POST" -p payloads.txt -grep signatures.txt
```
Add header if required
```plain
cat http_https.txt | BountyIt -t 70  -header "Cookie: session=311x1211sx4..." -p payloads.txt -grep signatures.txt
```

- Note:
  Check wordlist dir for signatures.txt and basic fuzzing list for basic ssti, rce, lfi.
  Make sure to add -verify as potential issues create false positive.

## Screenshot
![1414](https://github.com/Shivangx01b/LfiMe/blob/main/static/run.PNG)




