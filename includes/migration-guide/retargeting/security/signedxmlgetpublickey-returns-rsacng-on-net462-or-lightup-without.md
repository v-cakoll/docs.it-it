---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616092"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a><span data-ttu-id="dc71d-101">SignedXml.GetPublicKey restituisce RSACng per net462 (o lightup) senza reindirizzamento della modifica</span><span class="sxs-lookup"><span data-stu-id="dc71d-101">SignedXml.GetPublicKey returns RSACng on net462 (or lightup) without retargeting change</span></span>

#### <a name="details"></a><span data-ttu-id="dc71d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc71d-102">Details</span></span>

<span data-ttu-id="dc71d-103">A partire da .NET Framework 4.6.2, il tipo concreto dell'oggetto restituito dal metodo <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> modificato (senza dettaglio) da un'implementazione CryptoServiceProvider a un'implementazione Cng.</span><span class="sxs-lookup"><span data-stu-id="dc71d-103">Starting with the .NET Framework 4.6.2, the concrete type of the object returned by the <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> method changed (without a quirk) from a CryptoServiceProvider implementation to a Cng implementation.</span></span> <span data-ttu-id="dc71d-104">Questo avviene perché l'implementazione è stata modificata dall'uso di `certificate.PublicKey.Key` all'uso dell'oggetto `certificate.GetAnyPublicKey` interno che inoltra a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dc71d-104">This is because the implementation changed from using `certificate.PublicKey.Key` to using the internal `certificate.GetAnyPublicKey` which forwards to <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dc71d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dc71d-105">Suggestion</span></span>

<span data-ttu-id="dc71d-106">A partire dalle applicazioni eseguite in .NET Framework 4.7.1 è possibile usare l'implementazione CryptoServiceProvider usata per impostazione predefinita in .NET Framework 4.6.1 e versioni precedenti, aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="dc71d-106">Starting with apps running on the .NET Framework 4.7.1, you can use the CryptoServiceProvider implementation used by default in the .NET Framework 4.6.1 and earlier versions by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| <span data-ttu-id="dc71d-107">Nome</span><span class="sxs-lookup"><span data-stu-id="dc71d-107">Name</span></span>    | <span data-ttu-id="dc71d-108">Valore</span><span class="sxs-lookup"><span data-stu-id="dc71d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dc71d-109">Scope</span><span class="sxs-lookup"><span data-stu-id="dc71d-109">Scope</span></span>   | <span data-ttu-id="dc71d-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dc71d-110">Edge</span></span>        |
| <span data-ttu-id="dc71d-111">Version</span><span class="sxs-lookup"><span data-stu-id="dc71d-111">Version</span></span> | <span data-ttu-id="dc71d-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="dc71d-112">4.6.2</span></span>       |
| <span data-ttu-id="dc71d-113">Type</span><span class="sxs-lookup"><span data-stu-id="dc71d-113">Type</span></span>    | <span data-ttu-id="dc71d-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="dc71d-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="dc71d-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="dc71d-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
