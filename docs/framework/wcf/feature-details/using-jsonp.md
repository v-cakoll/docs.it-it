---
title: Uso di JSONP
ms.date: 03/30/2017
ms.assetid: f386718c-b4ba-4931-a610-40c27a46672a
ms.openlocfilehash: 82290319b5d8b58708f0b2ebf40522ee76127b84
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594959"
---
# <a name="using-jsonp"></a><span data-ttu-id="ea484-102">Uso di JSONP</span><span class="sxs-lookup"><span data-stu-id="ea484-102">Using JSONP</span></span>

<span data-ttu-id="ea484-103">JSON Padding (JSONP) è un meccanismo che abilita il supporto di script tra siti nei Web browser.</span><span class="sxs-lookup"><span data-stu-id="ea484-103">JSON Padding (JSONP) is a mechanism that enables cross-site scripting support in Web browsers.</span></span> <span data-ttu-id="ea484-104">JSONP è progettato sulla base della capacità dei Web browser di caricare script da un sito diverso rispetto a quello da cui è stato recuperato il documento attualmente caricato.</span><span class="sxs-lookup"><span data-stu-id="ea484-104">JSONP is designed around the ability of Web browsers to load scripts from a site different from the one the current loaded document was retrieved from.</span></span> <span data-ttu-id="ea484-105">Il meccanismo funziona riempiendo il payload JSON con un nome di funzione di callback definito dall'utente, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-105">The mechanism works by padding the JSON payload with a user-defined callback function name, as shown in the following example.</span></span>

```javascript
callback({"a" = \\"b\\"});
```

<span data-ttu-id="ea484-106">Nell'esempio precedente viene eseguito il wrapping del payload JSON, `{"a" = \\"b\\"}`, in una chiamata di funzione, `callback`.</span><span class="sxs-lookup"><span data-stu-id="ea484-106">In the preceding example the JSON payload, `{"a" = \\"b\\"}`, is wrapped in a function call, `callback`.</span></span> <span data-ttu-id="ea484-107">La funzione di callback deve essere già definita nella pagina Web corrente.</span><span class="sxs-lookup"><span data-stu-id="ea484-107">The callback function must already be defined in the current Web page.</span></span> <span data-ttu-id="ea484-108">Il tipo di contenuto di una risposta JSONP è `application/javascript` .</span><span class="sxs-lookup"><span data-stu-id="ea484-108">The content type of a JSONP response is `application/javascript`.</span></span>

<span data-ttu-id="ea484-109">JSONP non è automaticamente abilitato.</span><span class="sxs-lookup"><span data-stu-id="ea484-109">JSONP is not automatically enabled.</span></span> <span data-ttu-id="ea484-110">Per abilitarlo, impostare l'attributo `javascriptCallbackEnabled` su `true` in uno degli endpoint HTTP standard (<xref:System.ServiceModel.Description.WebHttpEndpoint> o <xref:System.ServiceModel.Description.WebScriptEndpoint>), come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-110">To enable it, set the `javascriptCallbackEnabled` attribute to `true` on one of the HTTP standard endpoints (<xref:System.ServiceModel.Description.WebHttpEndpoint> or <xref:System.ServiceModel.Description.WebScriptEndpoint>), as shown in the following example.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint name="" javascriptCallbackEnabled="true"/>
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="ea484-111">È possibile specificare il nome della funzione di callback in una variabile della query denominata callback, come indicato nell'URL seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-111">The name of the callback function can be specified in a query variable called callback as shown in the following URL.</span></span>

`http://baseaddress/Service/RestService?callback=functionName`

<span data-ttu-id="ea484-112">Se richiamato, il servizio invia una risposta analoga alla seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-112">When invoked, the service sends a response like the following.</span></span>

```javascript
functionName({"root":"Something"});
```  

<span data-ttu-id="ea484-113">È inoltre possibile specificare il nome della funzione di callback applicando <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> alla classe di servizio, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-113">You can also specify the callback function name by applying the <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> to the service class, as shown in the following example.</span></span>

```csharp
[ServiceContract]
[JavascriptCallbackBehavior(ParameterName = "$callback")]
public class Service1
{
    [OperationContract]
    [WebGet(ResponseFormat=WebMessageFormat.Json)]
    public string GetData()
    {
    }
}
```

<span data-ttu-id="ea484-114">Per il servizio mostrato in precedenza, una richiesta è analoga alla seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-114">For the service shown previously, a request looks like the following.</span></span>

`http://baseaddress/Service/RestService?$callback=anotherFunction`

<span data-ttu-id="ea484-115">Se richiamato, il servizio risponde come segue.</span><span class="sxs-lookup"><span data-stu-id="ea484-115">When invoked, the service responds with the following.</span></span>

```javascript
anotherFunction ({"root":"Something"});
```

## <a name="http-status-codes"></a><span data-ttu-id="ea484-116">Codici di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="ea484-116">HTTP Status Codes</span></span>

<span data-ttu-id="ea484-117">Le risposte JSONP con codici di stato HTTP diversi da 200 includono un secondo parametro con la rappresentazione numerica del codice di stato HTTP, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ea484-117">JSONP responses with HTTP status codes other than 200 include a second parameter with the numeric representation of the HTTP status code, as shown in the following example.</span></span>

```javascript
anotherFunction ({"root":"Something"}, 201);
```

## <a name="validations"></a><span data-ttu-id="ea484-118">Convalide</span><span class="sxs-lookup"><span data-stu-id="ea484-118">Validations</span></span>

<span data-ttu-id="ea484-119">Se JSONP è abilitato, vengono eseguite le convalide indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ea484-119">The following validations are performed when JSONP is enabled:</span></span>

- <span data-ttu-id="ea484-120">L'infrastruttura WCF genera un'eccezione se `javascriptCallback` è abilitato, è presente un parametro della stringa di query di callback nella richiesta e il formato della risposta è impostato su JSON.</span><span class="sxs-lookup"><span data-stu-id="ea484-120">The WCF infrastructure throws an exception if `javascriptCallback` is enabled, a callback query-string parameter is present in the request and the response format is set to JSON.</span></span>

- <span data-ttu-id="ea484-121">Se la richiesta contiene il parametro della stringa di query di callback ma l'operazione non è un'operazione HTTP GET, il parametro di callback viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ea484-121">If the request contains the callback query string parameter but the operation is not an HTTP GET, the callback parameter is ignored.</span></span>

- <span data-ttu-id="ea484-122">Se il nome del callback è `null` o una stringa vuota, la risposta non è formattata come JSONP.</span><span class="sxs-lookup"><span data-stu-id="ea484-122">If the callback name is `null` or empty string the response is not formatted as JSONP.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea484-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea484-123">See also</span></span>

- [<span data-ttu-id="ea484-124">Panoramica sul modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="ea484-124">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
