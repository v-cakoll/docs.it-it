---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614915"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="1389b-101">L'algoritmo hash predefinito per WPF PackageDigitalSignatureManager è ora SHA256</span><span class="sxs-lookup"><span data-stu-id="1389b-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="1389b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1389b-102">Details</span></span>

<span data-ttu-id="1389b-103">`System.IO.Packaging.PackageDigitalSignatureManager` offre funzionalità per le firme digitali in relazione ai pacchetti WPF.</span><span class="sxs-lookup"><span data-stu-id="1389b-103">The `System.IO.Packaging.PackageDigitalSignatureManager` provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="1389b-104">In .NET Framework 4.7 e versioni precedenti, l'algoritmo predefinito (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) usato per firmare le parti di un pacchetto era SHA1.</span><span class="sxs-lookup"><span data-stu-id="1389b-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="1389b-105">A causa di problemi di sicurezza recenti con SHA1, questa impostazione predefinita è stata cambiata in SHA256 a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="1389b-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="1389b-106">Questa modifica interessa la firma di tutti i pacchetti, inclusi i documenti XPS.</span><span class="sxs-lookup"><span data-stu-id="1389b-106">This change affects all package signing, including XPS documents.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1389b-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1389b-107">Suggestion</span></span>

<span data-ttu-id="1389b-108">Uno sviluppatore che vuole usare questa modifica per una versione del framework precedente a .NET Framework 4.7.1 o uno sviluppatore che richiede la funzionalità precedente per il framework .NET Framework 4.7.1 o versione successiva può impostare nel modo appropriato il flag AppContext seguente.</span><span class="sxs-lookup"><span data-stu-id="1389b-108">A developer who wants to utilize this change while targeting a framework version below .NET Framework 4.7.1 or a developer who requires the previous functionality while targeting .NET Framework 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="1389b-109">Se il valore è true viene usato come algoritmo predefinito SHA1; se è false viene usato SHA256.</span><span class="sxs-lookup"><span data-stu-id="1389b-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1389b-110">Nome</span><span class="sxs-lookup"><span data-stu-id="1389b-110">Name</span></span>    | <span data-ttu-id="1389b-111">Valore</span><span class="sxs-lookup"><span data-stu-id="1389b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1389b-112">Scope</span><span class="sxs-lookup"><span data-stu-id="1389b-112">Scope</span></span>   | <span data-ttu-id="1389b-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1389b-113">Edge</span></span>        |
| <span data-ttu-id="1389b-114">Version</span><span class="sxs-lookup"><span data-stu-id="1389b-114">Version</span></span> | <span data-ttu-id="1389b-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="1389b-115">4.7.1</span></span>       |
| <span data-ttu-id="1389b-116">Type</span><span class="sxs-lookup"><span data-stu-id="1389b-116">Type</span></span>    | <span data-ttu-id="1389b-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="1389b-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1389b-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="1389b-118">Affected APIs</span></span>

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
