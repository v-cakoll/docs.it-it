---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615694"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a><span data-ttu-id="545d3-101">Solo i protocolli Tls 1.0, 1.1 e 1.2 sono supportati in System.Net.ServicePointManager e System.Net.Security.SslStream</span><span class="sxs-lookup"><span data-stu-id="545d3-101">Only Tls 1.0, 1.1 and 1.2 protocols supported in System.Net.ServicePointManager and System.Net.Security.SslStream</span></span>

#### <a name="details"></a><span data-ttu-id="545d3-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="545d3-102">Details</span></span>

<span data-ttu-id="545d3-103">A partire da .NET Framework 4.6, le classi <xref:System.Net.ServicePointManager> e <xref:System.Net.Security.SslStream> possono usare solo uno dei tre protocolli seguenti: Tls1.0, Tls1.1 o Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="545d3-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager> and <xref:System.Net.Security.SslStream> classes are only allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="545d3-104">Il protocollo SSL 3.0 e la crittografia RC4 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="545d3-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="545d3-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="545d3-105">Suggestion</span></span>

<span data-ttu-id="545d3-106">La mitigazione consigliata consiste nell'aggiornare l'app sul lato server a Tls1.0, Tls1.1 o Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="545d3-106">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="545d3-107">Se ciò non è fattibile o se le app client non funzionano, è possibile usare la classe <xref:System.AppContext?displayProperty=fullName> per rifiutare esplicitamente questa funzionalità in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="545d3-107">If this is not feasible, or if client apps are broken, the <xref:System.AppContext?displayProperty=fullName> class can be used to opt out of this feature in either of two ways:</span></span>

- <span data-ttu-id="545d3-108">Impostando a livello di codice le opzioni compat su <xref:System.AppContext?displayProperty=fullName> , come illustrato [qui](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="545d3-108">By programmatically setting compat switches on the <xref:System.AppContext?displayProperty=fullName>, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="545d3-109">Aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="545d3-109">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| <span data-ttu-id="545d3-110">Nome</span><span class="sxs-lookup"><span data-stu-id="545d3-110">Name</span></span>    | <span data-ttu-id="545d3-111">Valore</span><span class="sxs-lookup"><span data-stu-id="545d3-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="545d3-112">Scope</span><span class="sxs-lookup"><span data-stu-id="545d3-112">Scope</span></span>   | <span data-ttu-id="545d3-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="545d3-113">Minor</span></span>       |
| <span data-ttu-id="545d3-114">Version</span><span class="sxs-lookup"><span data-stu-id="545d3-114">Version</span></span> | <span data-ttu-id="545d3-115">4.6</span><span class="sxs-lookup"><span data-stu-id="545d3-115">4.6</span></span>         |
| <span data-ttu-id="545d3-116">Type</span><span class="sxs-lookup"><span data-stu-id="545d3-116">Type</span></span>    | <span data-ttu-id="545d3-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="545d3-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="545d3-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="545d3-118">Affected APIs</span></span>

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
