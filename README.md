# NMError

NMError shows to the user an alert with the request error according to the status code.


## Usage

1. Add "NMError.swift" to your project
2. Call alertNMError from your ViewController when the request fail.


```swift
    // city request code
    .responseObject { (response: DataResponse<[City]>) in
        switch response.result {
            case .success:
                print("Validation Successful")

                NMRealmDataBaseAssistant.deleteAllObjectsFrom(entity: City.self)
                NMRealmDataBaseAssistant.saveAll(objects: resultArray)

            case .failure(let error):
                alertNMError(statusCode: response.response?.statusCode, error: error)
    }
```

## License

[MIT License](https://github.com/nmacambira/NMError/blob/master/LICENSE)

## Info

- Swift 4.1
