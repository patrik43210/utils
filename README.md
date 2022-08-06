# Utils

![tests](https://github.com/gouniverse/utils/workflows/tests/badge.svg)

Various utility functions

## Array Functions
- <b>ArrayContains(array interface{}, val interface{}) (exists bool, index int)</b>
- <b>ArrayMerge(array ...[]interface{}) []interface{}</b>
- <b>ArrayEqualsInt(a []int, b []int) bool</b> - checks whether 2 int arrays are the same
- <b>ArrayEqualsStr(a []int, b []int) bool</b> - checks whether 2 string arrays are the same
- <b>ArrayReverse[T any](arr []T) []T</b> - returns a new reversed array
```go
arr := []string{"one", "two", "three"}
newArr := ArrayReverse(arr)
// newArr is: []string{"three", "two", "one"}
```
- <b><strike>IsStringArrayEqual(a, b []string) bool</strike></b> - Deprecated. new code should use ArrayEqualsStr

## Email Functions
- <b>EmailSend(from string, to []string, subject string, htmlMessage string) (bool, error)</b>

## Environment Variables Functions
- <b>AppAddress() string</b> - returns the URL addree the app is running under (APP_URL:APP:PORT)
- <b>AppEnv() string</b> - returns the environment the app is running in  (APP_ENV)
- <b>AppInDevelopment() bool</b> - return whether app is in development
- <b>AppInLive() bool</b> - return whether app is in production / live
- <b>AppInProduction() bool</b> - return whether app is in production / live
- <b>AppInTesting() bool</b> - return whether app is being tested
- <b>AppName() string</b> - returns the name the app is running under (APP_NAME)
- <b>AppPort() string</b> - returns the port the app is running under (APP_PORT)
- <b>AppURL() string</b> - returns the URL the app is running under (APP_URL)
- <b>DbDriver() string</b> - returns the database driver (DB_DRIVER)
- <b>DbHost() string</b> - returns the database host (DB_HOST)
- <b>DbPort() string</b> - returns the database port (DB_PORT)
- <b>DbDatabase() string</b> - returns the database name driver (DB_DATABASE)
- <b>DbUsername() string</b> - returns the database username (DB_USERNAME)
- <b>DbPassword() string</b> - returns the database password (DB_PASSWORD)
- <b>EmailFromAddress() string</b> - returns the mail from address (MAIL_FROM)
- <b>EmailFromName() string</b> - returns the mail from name (MAIL_NAME)
- <b>Env(key string) string</b> - returns an enviroment vaialble (i.e. Env("DB_DRIVER"))
- <b>EnvIntialize(key string) string</b> - Intializes an .env file, if exists. Fails loudly if the file is invalid and cannot be parsed
```go
utils.EnvIntialize()
```

## File Functions
- <b>FileExists(filePath string) bool</b>
- <b>FileGetContents(filename string) (string, error)</b>
- <b>FilePutContents(filename string, data string, mode os.FileMode) error</b> - writes a string to file
- <b>FileToBase64(filePath string) string</b> - converts a file to Base64 encoded string
- <b>ImgToBase64Url(filePath string) string</b> - converts an image file to Base64 encoded URL string

## HTML Functions
- <b>MinCSS(cssString string) (string, error)</b> - Minifies a Css string
- <b>MinHTML(htmlString string) (string, error)</b> - Minifies a HTML string
- <b>MinScript(sctiptString string) (string, error)</b> - Minifies a JavaScript string
- <b>ScriptsHTML(str string) string</b> - returns an HTML fragment of scripts tags, with embedded and minified local scripts (mainly suitable for serverless environment)
- <b>StylesHTML(str string) string</b> - returns an HTML fragment of scripts tags, with embedded and minified local styles (mainly suitable for serverless environment)


## HTTP Functions
- <b>IP(r *http.Request) string</b> - Returns the IP address of the user
- <b>Req(r *http.Request, key string, defaultValue string) string</b> - Returns a POST or GET value for a key, or default if not exists
- <b>RespondJSON(w http.ResponseWriter, response api.Response)</b> - Respond returns an API response as JSON

## Interface Functions
- <b>InterfaceToStringArray(v interface{}) []string</b>

## Link Functions
- <b>LinkWebsite() string</b>

## Map Functions
- <b>MapToColumn(inputMap []map[string]string, keyName string) []string</b> -  returns a column from map
- <b>MapToKeyValue(inputMap []map[string]string, keyName string, valueName string) map[string]string</b> -  returns a key-value array from an array of maps

## String Functions
- <b>AddSlashes(str string) string</b> - adds slashes
- <b>Base64Decode(src string) ([]byte, error)</b> - decodes a string from Base64
- <b>Base64Encode(src []byte) string</b> - encodes a string to Base64
- <b><strike>RandStr(len int) string</strike></b> - Deprecated: new code should use StrRandom instead
- <b><strike>RandStrFromGamma(length int, gamma string) string</strike></b> - Deprecated. new code should use StrRandomFromGamma instead.
- <b><strike>Slugify(s string, replaceWith rune) string</strike></b> - Deprecated. new code should use StrSlugify
- <b>StrBetween(str string, startNeedle string, endNeedle string) (result string, found bool) </b> - returns the substring between two needles
- <b>StrLeftFrom(s string, needle, string) string</b> - returns the substring on the left side of the needle
- <b>StrRandom(len int) string</b> - generates a random string
- <b>StrRandomFromGamma(length int, gamma string) string</b> - generates random string of specified length with the characters specified in the gamma string
- <b>StrRightFrom(s string, needle, string) string</b> - returns the substring on the right side of the needle
- <b>StrSlugify(s string, replaceWith rune) string</b> - converts a string to slug
- <b>StrToInt(s string) (int, error)</b> - converts a string to Int32
- <b>StrToInt64(s string) (int64, error)</b> -  converts a string to Int64
- <b>StrToMD5Hash(text string) string</b> - StrToMD5Hash converts a string to MD5 hash
- <b>StrToSHA1Hash(text string) string</b> - StrToSHA1Hash converts a string to SHA1 hash
- <b>StrToSHA256Hash(text string) string</b> - converts a string to SHA256 hash
- <b>TemplateParseString(template string, data) string</b> - parses a template file and returns as string
- <b>ToString(v interface{}) string</b> - converts an interface to string

# Time Functions
- <b>StrToTimeUnix(str string) (int64, error)</b> - converts string to Unix time
```go
time, err := StrToTimeUnix("2020-12-29 11:00:00")
```

# Other Functions
- <b>IsNumeric(s string) bool</b> - checks if a string is numeric

- <b>CookieGet(r *http.Request, name string) string</b> - gets a cookie

- <b>CookieSet(w http.ResponseWriter, name string, value string, seconds int)</b> - sets a cookie

- <b>FromJSON(jsonString string, valueDefault interface{}) (interface{}, error)</b> - JSON decodes a string

- <b>ToJSON(value interface{}) (string, error)</b> - JSON encodes a value

- <b>ToBool(str string) bool</b> - converts a string with common names ("yes", "true", "1") to boolean
```
isDebugEnabled := ToBool("yes")
```

- <b>XOREncode(buffer []byte, key []byte) []byte</b> - XOR encodes a byte array

- <b>XORDencode(buffer []byte, key []byte) []byte</b> - XOR decodes a byte array

# Change Log

2022-08-06 - Added function ToBool

2022-08-04 - Added functions CookieGet, CookieSet, FromJSON, ToJSON, XORDecode, XOREncode

2022-08-02 - Added function ArrayReverse

2022-07-31 - Added functions ArrayEqualsInt, ArrayEqualsStr

2022-07-30 - Added functions StrBetween, StrRandom, StrRandomFromGamma, StrToBytes. Deprecated RandStr, RandStrFromGamme

2022-07-28 - Added functions StrLeftFrom, StrRightFrom

2022-06-01 - Moved Fiber functions into separate repo to remove extra dependencies

2021-07-19 - Added functions AppInDevelopment, AppInLive, AppInProduction, AppInTesting

## Similar Libraries

- https://github.com/gookit/goutil
