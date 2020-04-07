# HTTPie

## HTTPie 설치

### chocolatey 설치

참고: https://chocolatey.org/install

```shell
$ Get-ExecutionPolicy

$ Set-ExecutionPolicy AllSigned

$ Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

### python 38 설치, by choco

```shell
$ choco install python
```

### HTTPie 설치, by python

```shell
$ pip install --upgrade pip setuptools

WARNING: You are using pip version 19.2.3, however version 20.0.2 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

$ python -m pip install --upgrade pip

ERROR: Could not install packages due to an EnvironmentError: HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Max retries exceeded with url: /packages/54/0c/d01aa759fdc501a58f431eb594a17495f15b88da142ce14b5845662c13f3/pip-20.0.2-py2.py3-none-any.whl (Caused by SSLError(SSLCertVerificationError(1, '[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: self signed certificate in certificate chain (_ssl.c:1108)')))

$ python -m pip install --upgrade pip --trusted-host pypi.python.org --trusted-host files.pythonhosted.org --trusted-host pypi.org

$ pip install --upgrade pip setuptools

ERROR: Could not install packages due to an EnvironmentError: HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Max retries exceeded with url: /packages/54/0c/d01aa759fdc501a58f431eb594a17495f15b88da142ce14b5845662c13f3/pip-20.0.2-py2.py3-none-any.whl (Caused by SSLError(SSLCertVerificationError(1, '[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: self signed certificate in certificate chain (_ssl.c:1108)')))

$ pip install --upgrade pip setuptools --trusted-host pypi.python.org --trusted-host files.pythonhosted.org --trusted-host pypi.org

$ pip install --upgrade httpie --trusted-host pypi.python.org --trusted-host files.pythonhosted.org --trusted-host pypi.org

$ http --version

'http'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.

$ 명령 프롬프트 관리자로 실행

$ pip uninstall httpie

$ pip install --upgrade httpie --trusted-host pypi.python.org --trusted-host files.pythonhosted.org --trusted-host pypi.org
```

참고: [[Python] CERTIFICATE_VERIFY_FAILED error 해결 방법](https://m.blog.naver.com/PostView.nhn?blogId=ambidext&logNo=221423553624&proxyReferer=https%3A%2F%2Fwww.google.com%2F)

### HTTPie 사용

http GET http://[host]:[port]/path

http POST http://[host]:[port]/path [header name]:[header value] [param name]=[param value]

ex)

http GET http://localhost:8080/api/v1/members

http POST http://localhost:8080/api/v1/members Content-Type:application/json name=손흥민 phoneNumber=01012341234
