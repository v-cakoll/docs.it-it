---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198463"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="30afd-101">HTTP: Modifiche all'infrastruttura del corpo della risposta</span><span class="sxs-lookup"><span data-stu-id="30afd-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="30afd-102">L'infrastruttura che esegue il backup di un corpo della risposta HTTP è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="30afd-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="30afd-103">Se si utilizza `HttpResponse` direttamente, non è necessario apportare modifiche al codice.</span><span class="sxs-lookup"><span data-stu-id="30afd-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="30afd-104">Leggere ulteriormente se si sta `HttpResponse.Body` avvolgendo `HttpContext.Features`o sostituendo o accedendo .</span><span class="sxs-lookup"><span data-stu-id="30afd-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="30afd-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="30afd-105">Version introduced</span></span>

<span data-ttu-id="30afd-106">3.0</span><span class="sxs-lookup"><span data-stu-id="30afd-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="30afd-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="30afd-107">Old behavior</span></span>

<span data-ttu-id="30afd-108">Al corpo della risposta HTTP erano associate tre API:</span><span class="sxs-lookup"><span data-stu-id="30afd-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="30afd-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="30afd-109">New behavior</span></span>

<span data-ttu-id="30afd-110">Se sostituisci `HttpResponse.Body`, sostituisce `IHttpResponseBodyFeature` l'intero con un `StreamResponseBodyFeature` wrapper intorno al flusso specificato utilizzando per fornire implementazioni predefinite per tutte le API previste.</span><span class="sxs-lookup"><span data-stu-id="30afd-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="30afd-111">L'impostazione del flusso originale annulla questa modifica.</span><span class="sxs-lookup"><span data-stu-id="30afd-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="30afd-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="30afd-112">Reason for change</span></span>

<span data-ttu-id="30afd-113">La motivazione consiste nel combinare le API del corpo della risposta in un'unica nuova interfaccia di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="30afd-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="30afd-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="30afd-114">Recommended action</span></span>

<span data-ttu-id="30afd-115">Utilizzare `IHttpResponseBodyFeature` la posizione `IHttpResponseFeature.Body`in `IHttpSendFileFeature`cui `IHttpBufferingFeature`si utilizzava in precedenza , , o .</span><span class="sxs-lookup"><span data-stu-id="30afd-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="30afd-116">Category</span><span class="sxs-lookup"><span data-stu-id="30afd-116">Category</span></span>

<span data-ttu-id="30afd-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30afd-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="30afd-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="30afd-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
