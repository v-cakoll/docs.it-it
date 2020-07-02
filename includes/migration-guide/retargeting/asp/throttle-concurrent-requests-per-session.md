---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614433"
---
### <a name="throttle-concurrent-requests-per-session"></a><span data-ttu-id="5dcc7-101">Limitazione delle richieste simultanee per sessione</span><span class="sxs-lookup"><span data-stu-id="5dcc7-101">Throttle concurrent requests per session</span></span>

#### <a name="details"></a><span data-ttu-id="5dcc7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5dcc7-102">Details</span></span>

<span data-ttu-id="5dcc7-103">In .NET Framework 4.6.2 e versioni precedenti, ASP.NET esegue le richieste in sequenza con lo stesso Sessionid e in ASP.NET Sessionid viene sempre generato usando un cookie per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5dcc7-103">In the .NET Framework 4.6.2 and earlier, ASP.NET executes requests with the same Sessionid sequentially, and ASP.NET always issues the Sessionid through cookies by default.</span></span> <span data-ttu-id="5dcc7-104">Se una pagina richiede molto tempo per rispondere, le prestazioni del server risulteranno significativamente peggiorate semplicemente premendo <kbd>F5</kbd> sul browser.</span><span class="sxs-lookup"><span data-stu-id="5dcc7-104">If a page takes a long time to respond, it will significantly degrade server performance just by pressing <kbd>F5</kbd> on the browser.</span></span> <span data-ttu-id="5dcc7-105">Nella correzione è stato aggiunto un contatore per tenere traccia delle richieste in coda e terminare le richieste quando superano il limite specificato.</span><span class="sxs-lookup"><span data-stu-id="5dcc7-105">In the fix, we added a counter to track the queued requests and terminate the requests when they exceed a specified limit.</span></span> <span data-ttu-id="5dcc7-106">Il valore predefinito è 50.</span><span class="sxs-lookup"><span data-stu-id="5dcc7-106">The default value is 50.</span></span> <span data-ttu-id="5dcc7-107">Se si raggiunge il limite, verrà registrato un avviso nel registro eventi e potrebbe essere registrata una risposta HTTP 500 nel log di IIS.</span><span class="sxs-lookup"><span data-stu-id="5dcc7-107">If the limit is reached, a warning will be logged in the event log, and an HTTP 500 response may be recorded in the IIS log.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5dcc7-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5dcc7-108">Suggestion</span></span>

<span data-ttu-id="5dcc7-109">Per ripristinare il comportamento precedente, è possibile aggiungere l'impostazione seguente al file web. config per rifiutare esplicitamente il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="5dcc7-109">To restore the old behavior, you can add the following setting to your web.config file to opt out of the new behavior.</span></span>

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| <span data-ttu-id="5dcc7-110">Nome</span><span class="sxs-lookup"><span data-stu-id="5dcc7-110">Name</span></span>    | <span data-ttu-id="5dcc7-111">Valore</span><span class="sxs-lookup"><span data-stu-id="5dcc7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5dcc7-112">Scope</span><span class="sxs-lookup"><span data-stu-id="5dcc7-112">Scope</span></span>   | <span data-ttu-id="5dcc7-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5dcc7-113">Edge</span></span>        |
| <span data-ttu-id="5dcc7-114">Version</span><span class="sxs-lookup"><span data-stu-id="5dcc7-114">Version</span></span> | <span data-ttu-id="5dcc7-115">4.7</span><span class="sxs-lookup"><span data-stu-id="5dcc7-115">4.7</span></span>         |
| <span data-ttu-id="5dcc7-116">Type</span><span class="sxs-lookup"><span data-stu-id="5dcc7-116">Type</span></span>    | <span data-ttu-id="5dcc7-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="5dcc7-117">Retargeting</span></span> |
