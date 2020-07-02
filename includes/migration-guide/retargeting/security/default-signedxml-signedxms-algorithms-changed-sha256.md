---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614812"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a><span data-ttu-id="b506b-101">Algoritmi predefiniti SignedXML e SignedXMS modificati in SHA256</span><span class="sxs-lookup"><span data-stu-id="b506b-101">Default SignedXML and SignedXMS algorithms changed to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b506b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b506b-102">Details</span></span>

<span data-ttu-id="b506b-103">In .NET Framework 4.7 e versioni precedenti l'impostazione predefinita per SignedXML e SignedCMS era SHA1 per alcune operazioni. A partire da .NET Framework 4.7.1, per queste operazioni SHA256 è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b506b-103">In the .NET Framework 4.7 and earlier, SignedXML and SignedCMS default to SHA1 for some operations.Starting with the .NET Framework 4.7.1, SHA256 is enabled by default for these operations.</span></span> <span data-ttu-id="b506b-104">Questa modifica è necessaria perché SHA1 non è più considerato sicuro.</span><span class="sxs-lookup"><span data-stu-id="b506b-104">This change is necessary because SHA1 is no longer considered to be secure.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b506b-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b506b-105">Suggestion</span></span>

<span data-ttu-id="b506b-106">Esistono due nuovi valori di cambio di contesto per controllare se per impostazione predefinita viene usato SHA1 (non sicuro) o SHA256:</span><span class="sxs-lookup"><span data-stu-id="b506b-106">There are two new context switch values to control whether SHA1 (insecure) or SHA256 is used by default:</span></span>

- <span data-ttu-id="b506b-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span><span class="sxs-lookup"><span data-stu-id="b506b-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span></span>
- <span data-ttu-id="b506b-108">Switch.System. Security. Cryptography. Pkcs. UseInsecureHashAlgorithms per le applicazioni destinate a .NET Framework 4.7.1 e versioni successive, se l'uso di SHA256 è indesiderato, è possibile ripristinare il valore predefinito di SHA1 aggiungendo l'opzione di configurazione seguente alla sezione [Runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="b506b-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms For applications that target the .NET Framework 4.7.1 and later versions, if the use of SHA256 is undesirable, you can restore the default to SHA1 by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

<span data-ttu-id="b506b-109">Per le applicazioni destinate a .NET Framework 4.7.1 e versioni precedenti, è possibile scegliere esplicitamente questa modifica aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="b506b-109">For applications that target the .NET Framework 4.7 and earlier versions, you can opt into this change by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| <span data-ttu-id="b506b-110">Nome</span><span class="sxs-lookup"><span data-stu-id="b506b-110">Name</span></span>    | <span data-ttu-id="b506b-111">Valore</span><span class="sxs-lookup"><span data-stu-id="b506b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b506b-112">Scope</span><span class="sxs-lookup"><span data-stu-id="b506b-112">Scope</span></span>   | <span data-ttu-id="b506b-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="b506b-113">Minor</span></span>       |
| <span data-ttu-id="b506b-114">Version</span><span class="sxs-lookup"><span data-stu-id="b506b-114">Version</span></span> | <span data-ttu-id="b506b-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b506b-115">4.7.1</span></span>       |
| <span data-ttu-id="b506b-116">Type</span><span class="sxs-lookup"><span data-stu-id="b506b-116">Type</span></span>    | <span data-ttu-id="b506b-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="b506b-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b506b-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="b506b-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
