---
ms.openlocfilehash: 492d3e61acff31d3d6858a1c27cf353b04a05e36
ms.sourcegitcommit: d4f7ba08f2a45a9dbef53be597eed6d4a9410f29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401978"
---
### <a name="security-cookie-name-encoding-removed"></a>Sicurezza: codifica del nome del cookie rimossa

Lo [standard di cookie http](https://tools.ietf.org/html/rfc6265#section-4.1.1) consente solo caratteri specifici nei nomi e valori dei cookie. Per supportare i caratteri non consentiti, ASP.NET Core:

* Codifica durante la creazione di un cookie di risposta.
* Decodifica durante la lettura di un cookie di richiesta.

In ASP.NET Core 5,0 questo comportamento di codifica è stato modificato in risposta a un problema di sicurezza.

Per informazioni, vedere il problema GitHub [DotNet/aspnetcore # 23578](https://github.com/dotnet/aspnetcore/issues/23578).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 8

#### <a name="old-behavior"></a>Comportamento precedente

I nomi dei cookie di risposta sono codificati. I nomi dei cookie della richiesta sono decodificati.

#### <a name="new-behavior"></a>Nuovo comportamento

La codifica e la decodifica dei nomi di cookie sono state rimosse. Per le [versioni precedenti supportate](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) di ASP.NET Core, il team prevede di attenuare il problema di decodifica sul posto. Inoltre, <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> la chiamata a con un nome di cookie non valido genera un'eccezione di tipo <xref:System.ArgumentException> . La codifica e la decodifica dei valori dei cookie rimangono invariate.

#### <a name="reason-for-change"></a>Motivo della modifica

È stato individuato un problema in [più framework Web](https://github.com/advisories/GHSA-j6w9-fv6q-3q52). La codifica e la decodifica potrebbero consentire a un utente malintenzionato di ignorare una funzionalità di sicurezza denominata [prefissi di cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) mediante lo spoofing dei prefissi riservati, `__Host-` ad esempio con valori codificati come `__%48ost-` . L'attacco richiede un exploit secondario per inserire i cookie falsificati, ad esempio una vulnerabilità XSS (cross-site scripting) nel sito Web. Questi prefissi non vengono usati per impostazione predefinita nelle `Microsoft.Owin` librerie o nei modelli ASP.NET Core.

#### <a name="recommended-action"></a>Azione consigliata

Se i progetti vengono spostati in ASP.NET Core 5,0 o versioni successive, assicurarsi che i relativi nomi di cookie siano conformi ai [requisiti di specifica del token](https://tools.ietf.org/html/rfc2616#section-2.2): caratteri ASCII che escludono i controlli e i separatori `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT` . L'uso di caratteri non ASCII nei nomi di cookie o di altre intestazioni HTTP può causare un'eccezione dal server o essere sottoposti a round trip in modo errato dal client.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

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
