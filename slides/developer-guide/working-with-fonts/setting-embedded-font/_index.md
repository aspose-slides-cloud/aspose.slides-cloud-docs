---
title: "Setting Embedded Font"
type: docs
url: /setting-embedded-font/
weight: 30
---
## **Introduction**
Aspose.Slides Cloud API allows you embeding a font used in the presentation. The feature can be applied to presentations located in the storage or presentations uploaded in the request.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/fonts/embedded/{fontName}|POST|Embeds specified font and returns presentation fonts info.|[SetEmbeddedFont]()|
/slides/fonts/embedded/{fontName}|POST|Embeds specified font and returns presentation.|[SetEmbeddedFontOnline]()|
### **cURL Example**

The code examples below show how to embedded font both, in presentation from the request or the storage. 
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Storage**
```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts/embedded/calibri" -H "Authorization: Bearer [Access Token]"
```

**Request**
```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/fonts/embedded/Calibri" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@TestData/MyPresentation.pptx"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Storage**
```sh

Code: 200
Returns presentation fonts info.

```
**Request**
```sh

Document with embedded font.

```
{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
**Storage**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FontsData response = api.SetEmbeddedFont("MyPresentation.pptx", "Calibri", false);

Console.WriteLine("Font " + response.List[2].FontName + " has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FontsData response = api.setEmbeddedFont("MyPresentation.pptx", "Calibri", false, null, null, null);

System.out.println("Font " + response.getList().get(2).getFontName() + " has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\FontsData;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$result = $api->setEmbeddedFont("MyPresentation.pptx", "Calibri", false);

print("Font " + $result->getList()[2]->getFontName() + " has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

#Code example will be added soon.
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

response = api.set_embedded_font("MyPresentation.pptx", "Calibri", False)

print("Font " + response.list[2].font_name + " has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let result = await api.setEmbeddedFont("MyPresentation.pptx", "Calibri", false);
            
console.log("Font " + result.body.list[2].fontName + " has been embedded.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
fontName := "Calibri"
var onlyUsed bool = false
response, _, e := api.SetEmbeddedFont(fileName, fontName, &onlyUsed, "", "", "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Font " + response.GetList()[2].GetFontName() + " has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

**Request**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream file = File.OpenRead("MyPresentation.pptx");
api.SetEmbeddedFontOnline(file, "Calibri", false);

Console.WriteLine("Font Calibri has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes("MyPresentation.pptx");
api.setEmbeddedFontOnline(file, "Calibri", false);

System.out.println("Font Calibri has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\FontsData;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("MyPresentation.pptx", 'r');
$api->setEmbeddedFontOnline($file, "Calibri", false);

print("Font Calibri has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

#Code example will be added soon.
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

with open("MyPresentation.pptx", 'rb') as f:
    source = f.read()

api.set_embedded_font_online(source, "Calibri", False)

print("Font Calibri has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx")
let result = await api.setEmbeddedFontOnline(stream, "Calibri", false);
            
console.log("Count of fonts used in the presentation: " +  response.body.list.length);
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("MyPresentation.pptx")
fontName := "Calibri"
var onlyUsed bool = false
_, _, e = api.SetEmbeddedFontOnline(document, fontName, &onlyUsed, "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Font Calibri has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}