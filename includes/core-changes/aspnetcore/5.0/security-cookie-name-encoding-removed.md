---
ms.openlocfilehash: 492d3e61acff31d3d6858a1c27cf353b04a05e36
ms.sourcegitcommit: d4f7ba08f2a45a9dbef53be597eed6d4a9410f29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401978"
---
### <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="3ed5a-101">Sicurezza: codifica del nome del cookie rimossa</span><span class="sxs-lookup"><span data-stu-id="3ed5a-101">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="3ed5a-102">Lo [standard di cookie http](https://tools.ietf.org/html/rfc6265#section-4.1.1) consente solo caratteri specifici nei nomi e valori dei cookie.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-102">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="3ed5a-103">Per supportare i caratteri non consentiti, ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="3ed5a-103">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="3ed5a-104">Codifica durante la creazione di un cookie di risposta.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-104">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="3ed5a-105">Decodifica durante la lettura di un cookie di richiesta.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-105">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="3ed5a-106">In ASP.NET Core 5,0 questo comportamento di codifica è stato modificato in risposta a un problema di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-106">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="3ed5a-107">Per informazioni, vedere il problema GitHub [DotNet/aspnetcore # 23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="3ed5a-107">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ed5a-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="3ed5a-108">Version introduced</span></span>

<span data-ttu-id="3ed5a-109">5,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="3ed5a-109">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3ed5a-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="3ed5a-110">Old behavior</span></span>

<span data-ttu-id="3ed5a-111">I nomi dei cookie di risposta sono codificati.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-111">Response cookie names are encoded.</span></span> <span data-ttu-id="3ed5a-112">I nomi dei cookie della richiesta sono decodificati.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-112">Request cookie names are decoded.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3ed5a-113">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="3ed5a-113">New behavior</span></span>

<span data-ttu-id="3ed5a-114">La codifica e la decodifica dei nomi di cookie sono state rimosse.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-114">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="3ed5a-115">Per le [versioni precedenti supportate](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) di ASP.NET Core, il team prevede di attenuare il problema di decodifica sul posto.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-115">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="3ed5a-116">Inoltre, <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> la chiamata a con un nome di cookie non valido genera un'eccezione di tipo <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="3ed5a-116">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="3ed5a-117">La codifica e la decodifica dei valori dei cookie rimangono invariate.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-117">Encoding and decoding of cookie values remains unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3ed5a-118">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="3ed5a-118">Reason for change</span></span>

<span data-ttu-id="3ed5a-119">È stato individuato un problema in [più framework Web](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span><span class="sxs-lookup"><span data-stu-id="3ed5a-119">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="3ed5a-120">La codifica e la decodifica potrebbero consentire a un utente malintenzionato di ignorare una funzionalità di sicurezza denominata [prefissi di cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) mediante lo spoofing dei prefissi riservati, `__Host-` ad esempio con valori codificati come `__%48ost-` .</span><span class="sxs-lookup"><span data-stu-id="3ed5a-120">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="3ed5a-121">L'attacco richiede un exploit secondario per inserire i cookie falsificati, ad esempio una vulnerabilità XSS (cross-site scripting) nel sito Web.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-121">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="3ed5a-122">Questi prefissi non vengono usati per impostazione predefinita nelle `Microsoft.Owin` librerie o nei modelli ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-122">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ed5a-123">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="3ed5a-123">Recommended action</span></span>

<span data-ttu-id="3ed5a-124">Se i progetti vengono spostati in ASP.NET Core 5,0 o versioni successive, assicurarsi che i relativi nomi di cookie siano conformi ai [requisiti di specifica del token](https://tools.ietf.org/html/rfc2616#section-2.2): caratteri ASCII che escludono i controlli e i separatori `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT` .</span><span class="sxs-lookup"><span data-stu-id="3ed5a-124">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="3ed5a-125">L'uso di caratteri non ASCII nei nomi di cookie o di altre intestazioni HTTP può causare un'eccezione dal server o essere sottoposti a round trip in modo errato dal client.</span><span class="sxs-lookup"><span data-stu-id="3ed5a-125">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

#### <a name="category"></a><span data-ttu-id="3ed5a-126">Category</span><span class="sxs-lookup"><span data-stu-id="3ed5a-126">Category</span></span>

<span data-ttu-id="3ed5a-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3ed5a-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ed5a-128">API interessate</span><span class="sxs-lookup"><span data-stu-id="3ed5a-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
