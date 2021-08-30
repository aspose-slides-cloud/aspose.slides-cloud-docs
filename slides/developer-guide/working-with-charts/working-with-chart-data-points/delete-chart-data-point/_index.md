---
title: "Delete Chart Datapoint"
type: docs
url: /delete-chart-data-point/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud allows you to delete chart datapoints from a PowerPoint Presentation. 
### **API Information**
Aspose.Slides Cloud provides resources to achieve this.

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series/{seriesIndex}/dataPoints/{dataPointIndex}|DELETE|Delete the chart datapoint|[DeleteChartDataPoint](https://apireference.aspose.cloud/slides/#/Chart/DeleteChartDataPoint)|
### **cURL Example**
{{% alert color="primary" %}}

The referenced shape must be a chart, otherwise the operation will fail.

{{% /alert %}}

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/series/2/dataPoints/3" -H "Authorization: Bearer [Access Token]

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Body: Chart JSON

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart chart = api.DeleteChartDataPoint("myPresentaion.pptx", 1, 2, 2, 3);
Console.WriteLine(chart.Series[1].DataPoints.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart chart = (Chart)api.deleteChartDataPoint("MyPresentation.pptx", 1, 2, 2, 3, null, null, null);
System.out.println(chart.getSeries().get(1).getDataPoints().size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);
$result = $api->DeleteChartDataPoint("MyPresentation.pptx", 1, 2, 2, 3);
print(count($result->getSeries()[1]->getDataPoints()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

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
result = api.delete_chart_data_point("MyPresentation.pptx", 1, 2, 2, 3)
print(len(result.series[1].data_points))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
return api.deleteChartDataPoint("MyPresentation.pptx", 1, 2, 2, 3).then((result) => {
    console.log(((result.body as model.Chart).series[1] as model.ScatterSeries).dataPoints.length);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}