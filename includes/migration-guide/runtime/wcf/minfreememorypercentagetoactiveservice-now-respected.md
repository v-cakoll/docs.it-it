---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620364"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="5c298-101">L'impostazione MinFreeMemoryPercentageToActiveService viene ora rispettata</span><span class="sxs-lookup"><span data-stu-id="5c298-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="5c298-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5c298-102">Details</span></span>

<span data-ttu-id="5c298-103">Questa impostazione consente di stabilire la quantità minima di memoria che deve essere disponibile nel server per poter attivare un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="5c298-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="5c298-104">È progettata in modo da prevenire le eccezioni <xref:System.OutOfMemoryException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5c298-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="5c298-105">In .NET Framework 4.5 questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="5c298-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="5c298-106">In .NET Framework 4.5.1 questa impostazione viene applicata.</span><span class="sxs-lookup"><span data-stu-id="5c298-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5c298-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5c298-107">Suggestion</span></span>

<span data-ttu-id="5c298-108">Viene generata un'eccezione se la quantità di memoria libera disponibile sul server Web è inferiore alla percentuale definita dall'impostazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5c298-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="5c298-109">Alcuni servizi WCF correttamente avviati ed eseguiti in un ambiente di memoria limitato potrebbero avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5c298-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="5c298-110">Nome</span><span class="sxs-lookup"><span data-stu-id="5c298-110">Name</span></span>    | <span data-ttu-id="5c298-111">Valore</span><span class="sxs-lookup"><span data-stu-id="5c298-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5c298-112">Scope</span><span class="sxs-lookup"><span data-stu-id="5c298-112">Scope</span></span>   |<span data-ttu-id="5c298-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="5c298-113">Minor</span></span>|
|<span data-ttu-id="5c298-114">Version</span><span class="sxs-lookup"><span data-stu-id="5c298-114">Version</span></span>|<span data-ttu-id="5c298-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="5c298-115">4.5.1</span></span>|
|<span data-ttu-id="5c298-116">Type</span><span class="sxs-lookup"><span data-stu-id="5c298-116">Type</span></span>|<span data-ttu-id="5c298-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="5c298-117">Runtime</span></span>|
