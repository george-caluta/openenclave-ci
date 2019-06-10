Open Enclave CI
================
This library contains common Jenkins pipeline functions to be used by https://github.com/microsoft/openenclave

Usage
================
- In your Jenkins instance define a Global Pipeline Library that points to this repo (for the purpose of this doc we'll name it 'OpenEnclaveCommon')
- In your pipeline script simply import the library
```groovy
@Library("OpenEnclaveCommon") _
oe = new jenkins.common.Openenclave()
```
- Use the functions
```groovy
stage("test1") {
  node("linux") {
    cleanWs()
    def task = """
                echo "Hello World!"
                """
    oe.Run("clang-7", task)
  }
}
```

Licensing
=========

This project is released under the [MIT License](https://github.com/Microsoft/openenclave/blob/master/LICENSE).