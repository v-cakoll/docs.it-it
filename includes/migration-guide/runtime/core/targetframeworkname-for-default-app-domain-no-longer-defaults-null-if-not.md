---
ms.openlocfilehash: f955e270f709ddf6eea2e44bbcf386e372b9f6e3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621316"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a><span data-ttu-id="b9781-101">L'impostazione predefinita di TargetFrameworkName per il dominio app predefinito non è più Null, se non impostata</span><span class="sxs-lookup"><span data-stu-id="b9781-101">TargetFrameworkName for default app domain no longer defaults to null if not set</span></span>

#### <a name="details"></a><span data-ttu-id="b9781-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b9781-102">Details</span></span>

<span data-ttu-id="b9781-103"><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> era precedentemente Null nel dominio app predefinito, se non impostata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="b9781-103">The <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> was previously null in the default app domain, unless it was explicitly set.</span></span> <span data-ttu-id="b9781-104">A partire dalla versione 4.6, la proprietà <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> per il dominio app predefinito avrà un valore predefinito derivato da TargetFrameworkAttribute, se presente.</span><span class="sxs-lookup"><span data-stu-id="b9781-104">Beginning in 4.6, the <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> property for the default app domain will have a default value derived from the TargetFrameworkAttribute (if one is present).</span></span> <span data-ttu-id="b9781-105">I domini app non predefiniti continueranno a ereditare la proprietà <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> dal dominio app predefinito (che non avrà per impostazione predefinita il valore Null nella versione 4.6), a meno che non sia sottoposta a override in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="b9781-105">Non-default app domains will continue to inherit their <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> from the default app domain (which will not default to null in 4.6) unless it is explicitly overridden.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b9781-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b9781-106">Suggestion</span></span>

<span data-ttu-id="b9781-107">Il codice deve essere aggiornato in modo che non dipenda dal fatto che l'impostazione predefinita di <xref:System.AppDomainSetup.TargetFrameworkName> sia null.</span><span class="sxs-lookup"><span data-stu-id="b9781-107">Code should be updated to not depend on <xref:System.AppDomainSetup.TargetFrameworkName> defaulting to null.</span></span> <span data-ttu-id="b9781-108">Se è necessario che questa proprietà continui a restituire null, è possibile impostarla in modo esplicito su tale valore.</span><span class="sxs-lookup"><span data-stu-id="b9781-108">If it is required that this property continue to evaluate to null, it can be explicitly set to that value.</span></span>

| <span data-ttu-id="b9781-109">Nome</span><span class="sxs-lookup"><span data-stu-id="b9781-109">Name</span></span>    | <span data-ttu-id="b9781-110">Valore</span><span class="sxs-lookup"><span data-stu-id="b9781-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b9781-111">Scope</span><span class="sxs-lookup"><span data-stu-id="b9781-111">Scope</span></span>   |<span data-ttu-id="b9781-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b9781-112">Edge</span></span>|
|<span data-ttu-id="b9781-113">Version</span><span class="sxs-lookup"><span data-stu-id="b9781-113">Version</span></span>|<span data-ttu-id="b9781-114">4.6</span><span class="sxs-lookup"><span data-stu-id="b9781-114">4.6</span></span>|
|<span data-ttu-id="b9781-115">Type</span><span class="sxs-lookup"><span data-stu-id="b9781-115">Type</span></span>|<span data-ttu-id="b9781-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="b9781-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b9781-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="b9781-117">Affected APIs</span></span>

-<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
