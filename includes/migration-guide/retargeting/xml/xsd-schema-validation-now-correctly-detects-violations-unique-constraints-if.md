---
ms.openlocfilehash: 349854b0dec5a585990b9c5e7c0b575df5bf70f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615729"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a><span data-ttu-id="d082f-101">La convalida di XSD Schema ora rileva correttamente le violazioni dei vincoli univoci se vengono usate chiavi composte e una chiave è vuota</span><span class="sxs-lookup"><span data-stu-id="d082f-101">XSD Schema validation now correctly detects violations of unique constraints if compound keys are used and one key is empty</span></span>

#### <a name="details"></a><span data-ttu-id="d082f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d082f-102">Details</span></span>

<span data-ttu-id="d082f-103">Le versioni di .NET Framework precedenti alla 4.6 includono un bug a causa del quale la convalida XSD non rileva vincoli univoci per le chiavi composte se una delle chiavi è vuota.</span><span class="sxs-lookup"><span data-stu-id="d082f-103">Versions of the .NET Framework prior to 4.6 had a bug that caused XSD validation to not detect unique constraints on compound keys if one of the keys was empty.</span></span> <span data-ttu-id="d082f-104">Questo problema è stato corretto in .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="d082f-104">In the .NET Framework 4.6, this issue is corrected.</span></span> <span data-ttu-id="d082f-105">La convalida sarà più corretta, ma è possibile che la convalida di alcuni file XML abbia esito negativo, diversamente da quanto accadeva in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d082f-105">This will result in more correct validation, but it may also result in some XML not validating which previously would have.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d082f-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d082f-106">Suggestion</span></span>

<span data-ttu-id="d082f-107">Se è necessario usare la convalida .NET Framework 4.0 meno restrittiva, l'applicazione da convalidare può essere destinata alla versione 4.5 (o versioni precedenti) di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d082f-107">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.5 (or earlier) of the .NET Framework.</span></span> <span data-ttu-id="d082f-108">In caso di ridestinazione a .NET Framework 4.6, tuttavia, è necessario rivedere il codice per assicurarsi che non sia prevista la convalida per le chiavi composte duplicate, come descritto nella descrizione di questo problema.</span><span class="sxs-lookup"><span data-stu-id="d082f-108">When retargeting to .NET Framework 4.6, however, code review should be done to be sure that duplicate compound keys (as described in this issue's description) are not expected to validate.</span></span>

| <span data-ttu-id="d082f-109">Nome</span><span class="sxs-lookup"><span data-stu-id="d082f-109">Name</span></span>    | <span data-ttu-id="d082f-110">Valore</span><span class="sxs-lookup"><span data-stu-id="d082f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d082f-111">Scope</span><span class="sxs-lookup"><span data-stu-id="d082f-111">Scope</span></span>   | <span data-ttu-id="d082f-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d082f-112">Edge</span></span>        |
| <span data-ttu-id="d082f-113">Version</span><span class="sxs-lookup"><span data-stu-id="d082f-113">Version</span></span> | <span data-ttu-id="d082f-114">4.6</span><span class="sxs-lookup"><span data-stu-id="d082f-114">4.6</span></span>         |
| <span data-ttu-id="d082f-115">Type</span><span class="sxs-lookup"><span data-stu-id="d082f-115">Type</span></span>    | <span data-ttu-id="d082f-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d082f-116">Retargeting</span></span> |
