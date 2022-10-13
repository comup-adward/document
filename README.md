# Adward integration guide.



This guide describes how DSPs can integrate with Adward using OpenRTB 2.5(Native Ads 1.2, VAST 3.0).  
For more information on these, please check OpenRTB 2.5(Native Ads 1.2, VAST 3.0) specification from the link below.

[OpenRTB v2.5](https://www.iab.com/wp-content/uploads/2016/03/OpenRTB-API-Specification-Version-2-5-FINAL.pdf)<br>
[Native v1.2](https://www.iab.com/wp-content/uploads/2018/03/OpenRTB-Native-Ads-Specification-Final-1.2.pdf)<br>
[VAST v3.0](https://www.iab.com/wp-content/uploads/2015/06/VASTv3_0.pdf)

If you have any questions or require further clarity about this guide, you can reach out to adward@comup.co.kr
<br>

**Scope**
- Request : **always passed**, optional, x(not supported)
- Response : **required** fields must be included, recommended/optional fields have positive impact on operations.
<br>

# 1. Bid Request Specification
## Supported Objects

Object | Supported 
:--- | :---
BidRequest | O 
Source | O 
Regs | O 
Imp | O 
Metric | X 
Banner | O 
Video | O 
Native | O 
Format | X 
PMP | O 
Deal | O 
Site | O 
App | O 
Publisher | O 
Content | O 
Producer | X 
Device | O 
Geo | O 
User | O 
Data | X 
Segment | X 
Native Markup | O 
Asset | O 
Title | O 
Image | O 
Video | O 
Data | O 
EventTrackers | O 
<br>

## BidRequest Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string | **always passed**
imp | O | object array | **always passed**
site | O | object | **always passed**(only web)
app | O | object | **always passed**(only app)
device | O | object | **always passed**
user | O | object | optional
test | O | integer | optional
at | O | integer | **always passed**
tmax | O | integer | **always passed**
wseat | X | string array
bseat | X | string array
allimps | X | integer
cur | O | string array(USD only) | **always passed**
wlang | X | string array
bcat | O | string array | optional
badv | O | string array | optional
bapp | O | string array | optional
source | O | object | optional
regs | O | object | optional
ext | O | object | optional
<br>

## Imp Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  **always passed**
metric | O | object array |  optional
banner | O | object |  **always passed**(for banner imp)
video | O | object |  **always passed**(for video imp)
native | O | object |  **always passed**(for native imp)
pmp | O | object |  optional
displaymanager | O | string |  optional
displaymanagerver | O | string |  optional
instl | O | integer |  optional
tagid | O | string |  **always passed**
bidfloor | O | float |  **always passed**
bidfloorcur | O (USD only) | string |  **always passed**
secure | O | integer |  optional
iframebuster | X | string array
exp | X | integer
ext | O | object |  optional
<br>

## Banner Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
w | O | integer |  **always passed**
h | O | integer |  **always passed**
format | O | object array |  optional
wmax | X | integer
hmax | X | integer
wmin | X | integer
hmin | X | integer
id | O | string |  optional
btype | O | integer array |  optional
battr | O | integer array |  optional
pos | O | integer |  optional
mimes | X | string array
topframe | O | integer |  optional
expdir | X | integer array
api | O | integer array |  optional
vcm | X | integer
ext | X | object
<br>

## Video Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
mimes | O | string array |  **always passed**
minduration | O | integer |  **always passed**
maxduration | O | integer |  **always passed**
protocols | O | integer array |  optional
protocol | X | integer
w | O | integer |  optional
h | O | integer |  optional
startdelay | O | integer |  optional
placement | O | integer |  optional
linearity | O | integer |  optional
skip | O | integer |  optional
skipmin | O | integer |  optional
skipafter | O | integer |  optional
sequence | O | integer |  optional
battr | O | integer array |  optional
maxextended | O | integer |  optional
minbitrate | O | integer |  optional
maxbitrate | O | integer |  optional
boxingallowed | O | integer |  optional
playbackmethod | O | integer array |  optional
playbackend | O | integer |  optional
delivery | O | integer array |  optional
pos | O | integer |  optional
companionad | O | objects array |  optional
api | O | integer array |  optional
companiontype | O | integer array |  optional
ext | O | object |  optional
<br>

## Native Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
request | O | string |  **always passed**
ver | O | string |  optional
api | O | integer array |  optional
battr | O | integer array |  optional
ext | O | object |  optional
<br>

## Pmp Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
private_auction | O | integer |  optional
deals | O | objects array |  optional
ext | O | object |  optional
<br>

## Deal Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  optional
bidfloor | O | float |  optional
bidfloorcur | O | string |  optional
at | O | integer |  optional
wseat | O | string array |  optional
wadomain | O | string array |  optional
ext | O | object |  optional
<br>

## Site Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  **always passed**
name | O | string |  **always passed**
domain | O | string |  **always passed**
cat | O | string array |  optional
sectioncat | O | string array |  optional
pagecat | O | string array |  optional
page | O | string |  optional
ref | O | string |  optional
search | X | string
mobile | O | integer |  optional
privacypolicy | X | integer
publisher | O | object |  optional
content | O | object |  optional
keywords | O | string |  optional
ext | O | object |  optional
<br>

## App Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  **always passed**
name | O | string |  **always passed**
bundle | O | string |  **always passed**
domain | O | string |  optional
storeurl | O | string |  optional
cat | O | string array |  optional
sectioncat | X | string array
pagecat | X | string array
ver | O | string |  optional
privacypolicy | X | integer
paid | X | integer
publisher | O | object |  optional
content | O | object |  optional
keywords | O | string |  optional
ext | O | object |  optional
<br>

## Publisher Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  **always passed**
name | O | string |  optional
cat | X | string array
domain | X | string
ext | X | object
<br>

## Content Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string | optional
episode | X | integer
title | O | string | optional
series | X | string
season | X | string
artist | X | string
genre | O | string | optional
album | X | string
isrc | X | string
producer | X | object
url | X | string
cat | O | string array | optional
prodq | X | integer
videoquality | X | integer
context | O | integer | optional
contentrating | X | string
userration | X | string
gagmediarating | X | integer
keywords | O | string | optional
livestream | X | integer
sourcerelationship | X | integer
len | X | integer
language | X | string
embeddable | X | integer
data | X | object array
ext | X | object
<br>

## Device Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
ua | O | string |  **always passed**
geo | O | object |  optional
lmt | O | integer |  optional
dnt | O | integer |  optional
ip | O | string |  **always passed**
devicetype | O | integer |  optional
make | O | string |  optional
model | O | string |  optional
os | O | string |  **always passed**
osv | O | string |  optional
hwv | O | string |  optional
h | O | integer |  optional
w | O | integer |  optional
pxratio | O | float |  optional
js | O | integer |  optional
language | O | string |  optional
carrier | O | string |  optional
connectiontype | O | integer |  optional
ifa | O | string |  optional
didsha1 | X | string
didmd5 | X | string
dpidsha1 | X | string
dpidmd5 | X | string
ext | O | object |  optional
<br>

## Geo Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
lat | O | float |  optional
lon | O | float |  optional
type | O | integer |  optional
accuracy | X | integer
lastfix | X | integer
ipservice | X | integer
country | O | string |  optional
region | O | string |  optional
regionfips104 | O | string |  Optional
metro | O | string |  Optional
city | O | string |  Optional
zip | O | string |  Optional
utcoffset | X | integer
ext | X | object
<br>

## User Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  optional
buyerid | O | string |  optional
yob | O | integer |  optional
gender | O | string |  optional
keywords | O | string |  optional
customdata | X | string
geo | O | object |  optional
data | O | object array |  optional
ext | O | object |  optional
<br>

## Source Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
fd | O | integer |  optional
tid | O | integer |  optional
pchain | O | string |  optional
ext | O | object |  optional(schain)
<br>

## Reg Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
coppa | O | string |  optional
ext | O | object |  optional
<br>

## Native Markup Request Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
ver | O | string | optional
context | O | integer | optional
contextsubtype | X | integer | 
plcmttype | O | integer | optional
plcmtcnt | X | integer | 
seq | X | integer | 
assets | O | array of objects | **always passed**
aurlsupport | X | integer | -
durlsupport | X | integer | -
eventtrackers | O | array of objects | optional
privacy | O | integer | optional
ext | X | object |
<br>

## Asset Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
Id | O | integer | **always passed**
required | O | integer | optional
title | O | object | **always passed**
img | O | object | **always passed**
video | O | object | optional
data | O | object | **always passed**
ext | X | object | 

(each asset object may contain only one of title, img, data or video)
<br><br>

## Title Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
len | O | integer | **always passed**
ext | O | object | optional
<br>

## Image Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
type | O | integer | **always passed**
w | O | integer | optional
wmin | O | integer | **always passed**
h | O | integer | optional
hmin | O | integer | **always passed**
mimes | X | array of strings
ext | X | object
<br>

## Video Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
mimes | O | array of strings | **always passed**
minduration | O | integer | **always passed**
maxduration | O | integer | **always passed**
protocols | O | array of integers | **always passed**
ext | X | object
<br>

## Data Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
type | O | integer | **always passed**
len | O | integer | optional
ext | X | object
<br>

## EventTrackers Object

Field | Supported | Type | Scope
:--- | :---: | :---: | :---
event | O | integer | optional
methods | O | integer | optional
ext | X | object
<br>


## Request sample

## Banner
	{
		"id": "comup-banner-00001",
		"imp": [
			{
				"id": "imp-0001",
				"banner": {
					"w": 320,
					"h": 480,
					"battr": [
						11
					],
					"format": [
						{
							"w": 320,
							"h": 480
						}
					]
				},
				"instl": 1,
				"secure": 1,
				"bidfloorcur": "USD",
				"tagid": "comupmedia_tag01",
				"bidfloor": 0.212
			}
		],
		"at": 2,
		"tmax": 300,
		"cur": [
			"USD"
		],
		"device": {
			"dnt": 0,
			"lmt": 0,
			"geo": {
				"country": "KOR",
				"type": 2,
				"city": "seoul"
			},
			"ifa": "81743eca-13de-4s21-898c-d7aad5175a00",
			"connectiontype": 3,
			"language": "ko",
			"model": "SM-S908N",
			"carrier": "SKTelecom",
			"os": "android",
			"osv": "12",
			"js": 1,
			"ua": "Mozilla/5.0 (Linux; Android 12; SM-S908N Build/SP1A.210812.016; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/102.0.5005.78 Mobile Safari/537.36",
			"ip": "123.234.43.96",
			"devicetype": 4
		},
		"ext": {
		},
		"app": {
			"bundle": "com.test.comup",
			"storeurl": "https://play.google.com/store/apps/details?id=com.test.comup",
			"cat": [
				"IAB1",
				"IAB2"
			],
			"publisher": {
				"id": "1000"
			},
			"id": "comupmedia01",
			"name": "comup_test_media"
		},
		"user": {
			"id": "ab86a6d9b56d898a537csddfe",
			"ext": {
				"consent": ""
			}
		},
		"regs": {
			"coppa": 0,
			"ext": {
				"gdpr": 0
			}
		}
	}
<br>

## Video
	{
		"id": "comup-video-00001",
		"imp": [
			{
				"id": "imp-0002",
				"video": {
					"minduration": 5,
					"maxduration": 30,
					"boxingallowed": 1,
					"w": 1024,
					"h": 768,
					"mimes": [
						"video/mp4"
					],
					"protocol": 3,
					"protocols": [
						1,
						2,
						3,
						4,
						5
					],
					"linearity": 1,
					"battr": [
						8,
						10
					],
					"minbitrate": 250,
					"playbackmethod": [
						2
					]
				},
				"tagid": "comupmedia_tag01",
				"instl": 0,
				"secure": 0,
				"bidfloor": 4.567
			}
		],
		"at": 2,
		"tmax": 500,
		"cur": [
			"USD"
		],
		"device": {
			"dnt": 0,
			"geo": {
				"country": "KOR",
				"city": "Seoul"
			},
			"ifa": "81743eca-13de-4s21-898c-d7aad5175a01",
			"connectiontype": 2,
			"model": "SM-S908N",
			"carrier": "SKTelecom",
			"os": "android",
			"osv": "12",
			"js": 1,
			"ua": "Mozilla/5.0 (Linux; Android 12; SM-S908N Build/SP1A.210812.016; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/102.0.5005.78 Mobile Safari/537.36",
			"ip": "123.234.43.96",
			"devicetype": 4
		},
		"app": {
			"bundle": "com.test.comup1",
			"storeurl": "https://play.google.com/store/apps/details?id=com.test.comup1",
			"cat": [
				"IAB1"
			],
			"pagecat": [
				"IAB24"
			],
			"publisher": {
				"id": "1000"
			},
			"id": "comupmedia02",
			"name": "comuptestmedia2"
		},
		"bcat": [
			"IAB26",
			"IAB24"
		],
		"user": {
			"id": "ab86a6d9b56d898a537csddfe",
			"ext": {
				"consent": ""
			}
		},
		"regs": {
			"ext": {
				"gdpr": 0
			}
		},
		"ext": {
		}
	}
<br>

## Native
	{
		"id": "comup-native-00001",
		"imp": [
			{
				"id": "imp-0003",
				"instl": 0,
				"secure": 0,
				"native": {
					"request": "{\"native\":{\"assets\":[{\"id\":1,\"img\":{\"h\":0,\"hmin\":120,\"type\":3,\"w\":0,\"wmin\":180},\"required\":1},{\"id\":0,\"required\" :1,\"title\":{\"len\":100}},{\"data\":{\"len\":50,\"type\":1},\"id\":3,\"required\":1},{\"data\":{\"len\":200,\"type\":2},\"id\":5,\"required\":1}],\"context\":1,\"layout\":1,\"plcmtcnt\":1,\"plcmttype\":2,\"ver\":\"1.2\"}}"
				},
				"bidfloor": 0.72
			}
		],
		"at": 2,
		"tmax": 500,
		"cur": [
			"USD"
		],
		"device": {
			"dnt": 0,
			"geo": {
				"country": "KOR",
				"city": "Busan"
			},
			"ifa": "81743eca-13de-4s21-898c-d7aad5175a02",
			"connectiontype": 2,
			"model": "SM-S908N",
			"carrier": "SKTelecom",
			"osv": "12",
			"js": 1,
			"ua": "Mozilla/5.0 (Linux; Android 12; SM-S908N Build/SP1A.210812.016; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/102.0.5005.78 Mobile Safari/537.36",
			"ip": "123.151.140.127",
			"devicetype": 1
		},
		"app": {
			"bundle": "com.test.comup",
			"storeurl": "https://play.google.com/store/apps/details?id=com.test.comup",
			"cat": [
				"IAB1"
			],
			"pagecat": [
				"IAB24"
			],
			"publisher": {
				"id": "1000"
			},
			"id": "comupmedia03",
			"name": "comup_test_media3"
		},
		"user": {
			"id": "ab86a6d9b56d898a537csddfe"
		},
		"regs": {
			"ext": {
				"gdpr": 0
			}
		},
		"ext": {
		}
	}
<br>

# 2. Bid Response Specification
## Supported Objects

Object | Supported 
:--- | :---
BidResponse | O 
SeatBid | O 
Bid | O 
<br>

## BidResponse Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string | **required**
seatbid | O | objects array | **required**
bidid | O | string | optional
cur | O (USD only) | string | optional
customdata | O | string | optional
nbr | O | integer | optional
ext | O | object | optional
<br>

## SeatBid Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
bid | O | object array | **requried**
seat | O | string | recommended
group | X | integer
ext | X | object
<br>

## Bid Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | string |  **required**
impid | O | string |  **required**
price | O | float |  **required**
adid | O | string |  recommended
nurl | O | string |  optional
burl | O | string |  optional
lurl | O | string |  optional
adm | O | string |  **required**, Format: HTML<br>Win notice URL must be included within HTML.
adomain | O | string array |  recommended
iurl | O | string |  recommended
cid | O | string |  recommended
crid | O | string |  recommended
api | O | integer |  optional
bundle | O | string |  recommended
attr | O | integer array |  optional
cat | O | string array |  recommended
dealid | O | string |  optional
h | O | integer |  optional
w | O | integer |  optional
ext | X | object
<br>

## Win notice

Method | Explanation
:--- | :---
Client-to-Server | Win notice URL must be included within Bid.adm.<br>SSP should replace macro of win-price Macro of win-price : `${AUCTION_PRICE}`, `${AUCTION_PRICE:B64}`<br>After the Macro Replacement process of the URL, it gets sent to the client.<br>-> Calls for Win notice URL during the client’s ad HTML loading process.
<br>

## Native Markup Response Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
ver | O | string | **required**
assets | O | array of objects | **required**
assetsurl | O | string | optional
dcourl | X | string
link | O | object | **required**
imptrackers | O | array of strings | optional
jstracker | X | string
eventtrackers | O | array of objects | recommended
privacy | O | string | optional
ext | X | object
<br>

## Asset Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
id | O | integer | recommended
required | O | integer | optional
title | O | object | recommended
img | O | object | recommended
video | O | object | recommended
data | O | object | recommended
link | O | object | optional
ext | X | object

(Asset object may contain only one of title, img, data or video.)
<br>

## Title Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
text | O | string | **required**
len | O | integer | optional
ext | X | object
<br>

## Image Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
type | O | integer | recommended
url | O | string | **required**
w | O | integer | recommended
h | O | integer | recommended
ext | X | object
<br>

## Data Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
type | O | integer | recommended
len | O | integer | optional
value | O | string | **required**
ext | X | object
<br>

## Video Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
vasttag | O | string | **required**
<br>

## Link Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
url | O | string | **required**
clicktrackers | O | array of strings | recommended
fallback | X | string(URL)
ext | X | object
<br>

## Event Tracker Object

Attribute | Supported | Type | Scope
:--- | :---: | :---: | :---
event | O | integer | **required**
method | O | integer | **required**
url | O | text | recommended
customdata | X | object
ext | X | object
<br>

## Response sample

## Banner
	{
		"id": "comup-banner-00001",
		"bidid": "banner00001",
		"cur": "USD",
		"seatbid": [{
			"seat": "1001",
			"bid": [{
				"id": "1",
				"impid": "imp-0001",
				"price": 1.23,
				"adomain": ["test.example.com"],
				"bundle": "com.example.test",
				"iurl": "http://test.example.com/image/aaa.jpg",
				"cid": "100",
				"crid": "1000",
				"adm": "<div style=\"width:100% | height:100% | text-align:center | \"><a href=\"http://test.example.com/click\" target=\"_top\" style=\"text-decoration:none | \"><img id=\"ad\" src=\"http://test.example.com/image.jpg\" style=\"width:320px | height:480px | border:0px | \"/></a><img src=\"http://test.example.com/imp?impid=imp-0001&price=${AUCTION_PRICE}\" style=\"width:1px | height:1px | display:none | \" /></div>",
				"attr": [1, 2, 3, 12]
			}]
		}]
	}
<br>

## Video
	{
		"id": "comup-video-00002",
		"bidid": "video00002",
		"cur": "USD",
		"seatbid": [{
			"seat": "1001",
			"bid": [{
				"id": "1",
				"impid": "imp-0002",
				"price": 1.23,
				"adomain": ["test.example.com"],
				"bundle": "com.example.test",
				"cid": "100",
				"crid": "1000",
				"adm": "<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"3.0\">.....</VAST>"
			}]
		}]
	}
 
<br>

## Native
	{
		"id": "comup-native-00003",
		"bidid": "native00003",
		"cur": "USD",
		"seatbid": [{
			"seat": "1001",
			"bid": [{
				"id": "1",
				"impid": "imp-0003",
				"price": 1.23,
				"adomain": ["test.example.com"],
				"bundle": "com.example.test",
				"iurl": "http://test.example.com/image/aaa.jpg",
				"cid": "100",
				"crid": "10000",
				"adm": "{\"native\":{\"ver\":\"1.2\",\"link\":{ ... }, \"eventtrackers\":[ ... ],\"assets\":[ ... ]}}"
			}]
		}]
	}
<br>

## Substitution Macros

Macro | Description | Supported
:--- | :--- | :---
${AUCTION_ID} | ID of the bid request; from BidRequest.id attribute. | O
${AUCTION_BID_ID} | ID of the bid; from BidResponse.bidid attribute. | O
${AUCTION_IMP_ID} | ID of the impression just won; from imp.id attribute. | O
${AUCTION_SEAT_ID} | ID of the bidder seat for whom the bid was made. | O
${AUCTION_AD_ID} | ID of the ad markup the bidder wishes to serve; from bid.adid attribute. | O
${AUCTION_PRICE} | Clearing price using the same currency and units as the bid. | O
${AUCTION_PRICE:B64} | Clearing price using the same currency and units as the bid. (Base64 encoding) | O
${AUCTION_CURRENCY} | The currency used in the bid (explicit or implied); for confirmation only. | O
${CLICK_TRACK_URL} | Click measurement URL | O
<br>

