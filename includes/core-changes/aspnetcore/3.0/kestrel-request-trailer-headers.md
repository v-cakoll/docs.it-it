---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394198"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="5d2b7-101">Kestrel: richiesta di intestazioni rimorchio spostato in nuova collezione</span><span class="sxs-lookup"><span data-stu-id="5d2b7-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="5d2b7-102">Nelle versioni precedenti, Kestrel aggiungeva intestazioni di trailer in blocchi HTTP/1.1 nella raccolta di intestazioni di richiesta quando il corpo della richiesta veniva letto fino alla fine.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="5d2b7-103">Questo comportamento causava problemi relativi all'ambiguità tra intestazioni e trailer.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="5d2b7-104">È stata presa la decisione di spostare i rimorchi in una nuova collezione.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="5d2b7-105">I trailer delle richieste HTTP/2 non erano disponibili in ASP.NET Core 2.2, ma ora sono disponibili anche in questa nuova raccolta in ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="5d2b7-106">Sono stati aggiunti nuovi metodi di estensione delle richieste per accedere a questi trailer.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="5d2b7-107">I trailer HTTP/1.1 sono disponibili una volta che l'intero corpo della richiesta è stato letto.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="5d2b7-108">I trailer HTTP/2 sono disponibili una volta ricevuti dal client.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="5d2b7-109">Il client non invierà i trailer fino a quando l'intero corpo della richiesta non è stato almeno memorizzato nel buffer dal server.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="5d2b7-110">Potrebbe essere necessario leggere il corpo della richiesta per liberare spazio nel buffer.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="5d2b7-111">I trailer sono sempre disponibili se leggi il corpo della richiesta fino alla fine.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="5d2b7-112">I rimorchi segnano la fine del corpo.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5d2b7-113">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5d2b7-113">Version introduced</span></span>

<span data-ttu-id="5d2b7-114">3.0</span><span class="sxs-lookup"><span data-stu-id="5d2b7-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5d2b7-115">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="5d2b7-115">Old behavior</span></span>

<span data-ttu-id="5d2b7-116">Le intestazioni del trailer `HttpRequest.Headers` della richiesta verranno aggiunte alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5d2b7-117">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="5d2b7-117">New behavior</span></span>

<span data-ttu-id="5d2b7-118">Le intestazioni dei trailer delle `HttpRequest.Headers` richieste non sono **presenti** nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="5d2b7-119">Utilizzare i seguenti `HttpRequest` metodi di estensione per accedervi:</span><span class="sxs-lookup"><span data-stu-id="5d2b7-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="5d2b7-120">`GetDeclaredTrailers()`- Ottiene l'intestazione della richiesta "Trailer" che elenca i trailer da aspettarsi dopo il corpo.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="5d2b7-121">`SupportsTrailers()`- Indica se la richiesta supporta la ricezione delle intestazioni del trailer.- Indicates if the request supports receiving trailer headers.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="5d2b7-122">`CheckTrailersAvailable()`- Determina se la richiesta supporta i trailer e se sono disponibili per la lettura.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="5d2b7-123">`GetTrailer(string trailerName)`- Ottiene l'intestazione finale richiesta dalla risposta.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5d2b7-124">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="5d2b7-124">Reason for change</span></span>

<span data-ttu-id="5d2b7-125">I trailer sono una caratteristica chiave in scenari come gRPC.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="5d2b7-126">L'unione dei trailer nelle intestazioni delle richieste è stata fonte di confusione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5d2b7-127">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5d2b7-127">Recommended action</span></span>

<span data-ttu-id="5d2b7-128">Utilizzare i metodi di `HttpRequest` estensione relativi al rimorchio per accedere ai rimorchi.</span><span class="sxs-lookup"><span data-stu-id="5d2b7-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="5d2b7-129">Category</span><span class="sxs-lookup"><span data-stu-id="5d2b7-129">Category</span></span>

<span data-ttu-id="5d2b7-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5d2b7-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5d2b7-131">API interessate</span><span class="sxs-lookup"><span data-stu-id="5d2b7-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
