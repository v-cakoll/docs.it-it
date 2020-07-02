---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617238"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="00ad7-101">La convalida di XML Schema è più rigida</span><span class="sxs-lookup"><span data-stu-id="00ad7-101">XML schema validation is stricter</span></span>

#### <a name="details"></a><span data-ttu-id="00ad7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="00ad7-102">Details</span></span>

<span data-ttu-id="00ad7-103">In .NET Framework 4.5 la convalida XML Schema è più rigida.</span><span class="sxs-lookup"><span data-stu-id="00ad7-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="00ad7-104">Se si usa xsd:anyURI per convalidare un URI, come un protocollo mailto, la convalida ha esito negativo se sono presenti spazi nell'URI.</span><span class="sxs-lookup"><span data-stu-id="00ad7-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="00ad7-105">Nelle versioni precedenti di .NET Framework la convalida aveva esito positivo.</span><span class="sxs-lookup"><span data-stu-id="00ad7-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="00ad7-106">La modifica influisce solo sulle applicazioni destinate a .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="00ad7-106">The change affects only applications that target the .NET Framework 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="00ad7-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="00ad7-107">Suggestion</span></span>

<span data-ttu-id="00ad7-108">Se è necessario usare la convalida .NET Framework 4.0 meno restrittiva, l'applicazione da convalidare può essere destinata alla versione 4.0 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00ad7-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="00ad7-109">In caso di ridestinazione a .NET Framework 4.5, tuttavia, è necessario rivedere il codice per assicurarsi che gli URI non validi (con spazi) non siano previsti come valori di attributo con il tipo di dati anyURI.</span><span class="sxs-lookup"><span data-stu-id="00ad7-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>

| <span data-ttu-id="00ad7-110">Nome</span><span class="sxs-lookup"><span data-stu-id="00ad7-110">Name</span></span>    | <span data-ttu-id="00ad7-111">Valore</span><span class="sxs-lookup"><span data-stu-id="00ad7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="00ad7-112">Scope</span><span class="sxs-lookup"><span data-stu-id="00ad7-112">Scope</span></span>   | <span data-ttu-id="00ad7-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="00ad7-113">Minor</span></span>       |
| <span data-ttu-id="00ad7-114">Version</span><span class="sxs-lookup"><span data-stu-id="00ad7-114">Version</span></span> | <span data-ttu-id="00ad7-115">4.5</span><span class="sxs-lookup"><span data-stu-id="00ad7-115">4.5</span></span>         |
| <span data-ttu-id="00ad7-116">Type</span><span class="sxs-lookup"><span data-stu-id="00ad7-116">Type</span></span>    | <span data-ttu-id="00ad7-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="00ad7-117">Retargeting</span></span> |
