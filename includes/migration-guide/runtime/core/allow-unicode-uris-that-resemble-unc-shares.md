---
ms.openlocfilehash: 3e8601ba76dfb05e3d70b3af7440bd7e228768d0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621172"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="b6551-101">Consentire Unicode negli URI simili a condivisioni UNC</span><span class="sxs-lookup"><span data-stu-id="b6551-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="b6551-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b6551-102">Details</span></span>

<span data-ttu-id="b6551-103">In <xref:System.Uri?displayProperty=fullName>, la costruzione dell'URI di un file contenente sia un nome condivisione URI che caratteri Unicode non ha più come risultato un URI con stato interno non valido.</span><span class="sxs-lookup"><span data-stu-id="b6551-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="b6551-104">Il comportamento cambia solo se tutte le condizioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="b6551-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="b6551-105">Lo schema dell'URI è <code>file:</code> ed è seguito da almeno quattro barre.</span><span class="sxs-lookup"><span data-stu-id="b6551-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="b6551-106">Il nome host inizia con un carattere di sottolineatura o con un altro simbolo non riservato.</span><span class="sxs-lookup"><span data-stu-id="b6551-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="b6551-107">L'URI contiene caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="b6551-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="b6551-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b6551-108">Suggestion</span></span>

<span data-ttu-id="b6551-109">Le applicazioni che utilizzano URI contenenti Unicode in modo coerente avrebbero presumibilmente potuto usare questo comportamento per impedire riferimenti a condivisioni UNC.</span><span class="sxs-lookup"><span data-stu-id="b6551-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="b6551-110">Tali applicazioni devono invece usare <xref:System.Uri.IsUnc>.</span><span class="sxs-lookup"><span data-stu-id="b6551-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="b6551-111">Nome</span><span class="sxs-lookup"><span data-stu-id="b6551-111">Name</span></span>    | <span data-ttu-id="b6551-112">Valore</span><span class="sxs-lookup"><span data-stu-id="b6551-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b6551-113">Scope</span><span class="sxs-lookup"><span data-stu-id="b6551-113">Scope</span></span>   |<span data-ttu-id="b6551-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b6551-114">Edge</span></span>|
|<span data-ttu-id="b6551-115">Version</span><span class="sxs-lookup"><span data-stu-id="b6551-115">Version</span></span>|<span data-ttu-id="b6551-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="b6551-116">4.7.2</span></span>|
|<span data-ttu-id="b6551-117">Type</span><span class="sxs-lookup"><span data-stu-id="b6551-117">Type</span></span>|<span data-ttu-id="b6551-118">Runtime</span><span class="sxs-lookup"><span data-stu-id="b6551-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b6551-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="b6551-119">Affected APIs</span></span>

-<xref:System.Uri?displayProperty=nameWithType></li></ul>|
