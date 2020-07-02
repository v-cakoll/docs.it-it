---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620214"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="54fd6-101">La deserializzazione di oggetti tra domini app può non riuscire</span><span class="sxs-lookup"><span data-stu-id="54fd6-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="54fd6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="54fd6-102">Details</span></span>

<span data-ttu-id="54fd6-103">In alcuni casi, quando un'app usa due o più domini di app con diverse basi dell'applicazione, il tentativo di deserializzare gli oggetti nel contesto di una chiamata logica tra domini di app genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="54fd6-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="54fd6-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="54fd6-104">Suggestion</span></span>

<span data-ttu-id="54fd6-105">Vedere [Mitigazione: deserializzazione di oggetti tra domini app](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="54fd6-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="54fd6-106">Nome</span><span class="sxs-lookup"><span data-stu-id="54fd6-106">Name</span></span>    | <span data-ttu-id="54fd6-107">Valore</span><span class="sxs-lookup"><span data-stu-id="54fd6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="54fd6-108">Scope</span><span class="sxs-lookup"><span data-stu-id="54fd6-108">Scope</span></span>   |<span data-ttu-id="54fd6-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="54fd6-109">Edge</span></span>|
|<span data-ttu-id="54fd6-110">Version</span><span class="sxs-lookup"><span data-stu-id="54fd6-110">Version</span></span>|<span data-ttu-id="54fd6-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="54fd6-111">4.5.1</span></span>|
|<span data-ttu-id="54fd6-112">Type</span><span class="sxs-lookup"><span data-stu-id="54fd6-112">Type</span></span>|<span data-ttu-id="54fd6-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="54fd6-113">Runtime</span></span>|
