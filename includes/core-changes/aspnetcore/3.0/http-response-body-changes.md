---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198463"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="55197-101">HTTP: modifiche dell'infrastruttura del corpo della risposta</span><span class="sxs-lookup"><span data-stu-id="55197-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="55197-102">L'infrastruttura supportata da un corpo della risposta HTTP è cambiata.</span><span class="sxs-lookup"><span data-stu-id="55197-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="55197-103">Se si usa direttamente `HttpResponse`, non è necessario apportare modifiche al codice.</span><span class="sxs-lookup"><span data-stu-id="55197-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="55197-104">Leggere ulteriormente se si esegue il wrapping o si sostituisce `HttpResponse.Body` o si accede a `HttpContext.Features`.</span><span class="sxs-lookup"><span data-stu-id="55197-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="55197-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55197-105">Version introduced</span></span>

<span data-ttu-id="55197-106">3.0</span><span class="sxs-lookup"><span data-stu-id="55197-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="55197-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="55197-107">Old behavior</span></span>

<span data-ttu-id="55197-108">Sono presenti tre API associate al corpo della risposta HTTP:</span><span class="sxs-lookup"><span data-stu-id="55197-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="55197-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="55197-109">New behavior</span></span>

<span data-ttu-id="55197-110">Se si sostituisce `HttpResponse.Body`, l'intero `IHttpResponseBodyFeature` viene sostituito con un wrapper per il flusso specificato tramite `StreamResponseBodyFeature` per fornire implementazioni predefinite per tutte le API previste.</span><span class="sxs-lookup"><span data-stu-id="55197-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="55197-111">Se si imposta di nuovo il flusso originale, questa modifica viene ripristinata.</span><span class="sxs-lookup"><span data-stu-id="55197-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="55197-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="55197-112">Reason for change</span></span>

<span data-ttu-id="55197-113">La motivazione consiste nel combinare le API del corpo della risposta in un'unica nuova interfaccia di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="55197-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="55197-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="55197-114">Recommended action</span></span>

<span data-ttu-id="55197-115">Utilizzare `IHttpResponseBodyFeature`, in cui in precedenza veniva utilizzato `IHttpResponseFeature.Body`, `IHttpSendFileFeature` o `IHttpBufferingFeature`.</span><span class="sxs-lookup"><span data-stu-id="55197-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="55197-116">Category</span><span class="sxs-lookup"><span data-stu-id="55197-116">Category</span></span>

<span data-ttu-id="55197-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55197-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="55197-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="55197-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
