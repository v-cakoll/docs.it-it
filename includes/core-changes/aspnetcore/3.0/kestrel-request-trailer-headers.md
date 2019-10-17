---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394198"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="d0a91-101">Gheppio: intestazioni del trailer della richiesta spostate in una nuova raccolta</span><span class="sxs-lookup"><span data-stu-id="d0a91-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="d0a91-102">Nelle versioni precedenti, gheppio ha aggiunto le intestazioni dei trailer in blocchi HTTP/1.1 nella raccolta delle intestazioni della richiesta quando il corpo della richiesta è stato letto alla fine.</span><span class="sxs-lookup"><span data-stu-id="d0a91-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="d0a91-103">Questo comportamento causava problemi di ambiguità tra le intestazioni e i trailer.</span><span class="sxs-lookup"><span data-stu-id="d0a91-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="d0a91-104">È stata presa la decisione di spostare i trailer in una nuova raccolta.</span><span class="sxs-lookup"><span data-stu-id="d0a91-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="d0a91-105">I trailer delle richieste HTTP/2 non sono disponibili in ASP.NET Core 2,2, ma sono ora disponibili anche nella nuova raccolta ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="d0a91-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="d0a91-106">Per accedere a questi trailer sono stati aggiunti nuovi metodi di estensione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="d0a91-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="d0a91-107">I trailer HTTP/1.1 sono disponibili dopo la lettura dell'intero corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="d0a91-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="d0a91-108">I trailer HTTP/2 sono disponibili una volta ricevuti dal client.</span><span class="sxs-lookup"><span data-stu-id="d0a91-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="d0a91-109">Il client non invierà i trailer finché l'intero corpo della richiesta non verrà memorizzato nel buffer almeno dal server.</span><span class="sxs-lookup"><span data-stu-id="d0a91-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="d0a91-110">Potrebbe essere necessario leggere il corpo della richiesta per liberare spazio nel buffer.</span><span class="sxs-lookup"><span data-stu-id="d0a91-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="d0a91-111">I trailer sono sempre disponibili se il corpo della richiesta viene letto alla fine.</span><span class="sxs-lookup"><span data-stu-id="d0a91-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="d0a91-112">I trailer contrassegnano la fine del corpo.</span><span class="sxs-lookup"><span data-stu-id="d0a91-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d0a91-113">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d0a91-113">Version introduced</span></span>

<span data-ttu-id="d0a91-114">3.0</span><span class="sxs-lookup"><span data-stu-id="d0a91-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d0a91-115">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="d0a91-115">Old behavior</span></span>

<span data-ttu-id="d0a91-116">Le intestazioni del trailer della richiesta verranno aggiunte alla raccolta `HttpRequest.Headers`.</span><span class="sxs-lookup"><span data-stu-id="d0a91-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d0a91-117">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="d0a91-117">New behavior</span></span>

<span data-ttu-id="d0a91-118">Le intestazioni del trailer della richiesta **non sono presenti** nella raccolta `HttpRequest.Headers`.</span><span class="sxs-lookup"><span data-stu-id="d0a91-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="d0a91-119">Usare i seguenti metodi di estensione su `HttpRequest` per accedervi:</span><span class="sxs-lookup"><span data-stu-id="d0a91-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="d0a91-120">`GetDeclaredTrailers()`-Ottiene l'intestazione della richiesta "Trailer" che elenca i trailer da prevedere dopo il corpo.</span><span class="sxs-lookup"><span data-stu-id="d0a91-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="d0a91-121">`SupportsTrailers()`: indica se la richiesta supporta la ricezione di intestazioni trailer.</span><span class="sxs-lookup"><span data-stu-id="d0a91-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="d0a91-122">`CheckTrailersAvailable()`: determina se la richiesta supporta i trailer e se sono disponibili per la lettura.</span><span class="sxs-lookup"><span data-stu-id="d0a91-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="d0a91-123">`GetTrailer(string trailerName)`-Ottiene l'intestazione finale richiesta dalla risposta.</span><span class="sxs-lookup"><span data-stu-id="d0a91-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d0a91-124">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d0a91-124">Reason for change</span></span>

<span data-ttu-id="d0a91-125">I trailer sono una funzionalità chiave in scenari come gRPC.</span><span class="sxs-lookup"><span data-stu-id="d0a91-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="d0a91-126">Unire i trailer in per richiedere le intestazioni era una confusione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d0a91-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d0a91-127">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d0a91-127">Recommended action</span></span>

<span data-ttu-id="d0a91-128">Usare i metodi di estensione correlati al trailer in `HttpRequest` per accedere ai trailer.</span><span class="sxs-lookup"><span data-stu-id="d0a91-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="d0a91-129">Category</span><span class="sxs-lookup"><span data-stu-id="d0a91-129">Category</span></span>

<span data-ttu-id="d0a91-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d0a91-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d0a91-131">API interessate</span><span class="sxs-lookup"><span data-stu-id="d0a91-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
