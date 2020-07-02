---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620291"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="db3e7-101">I dati sql_variant usano regole di confronto sql_variant invece delle regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="db3e7-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="db3e7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="db3e7-102">Details</span></span>

<span data-ttu-id="db3e7-103">I dati di <code>sql_variant</code> usano regole di confronto di <code>sql_variant</code> anziché regole di confronto di database.</span><span class="sxs-lookup"><span data-stu-id="db3e7-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="db3e7-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="db3e7-104">Suggestion</span></span>

<span data-ttu-id="db3e7-105">Questa modifica risolve il possibile danneggiamento dei dati se le regole di confronto del database differiscono da quelle di <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="db3e7-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="db3e7-106">Le applicazioni basate su dati errati possono generare un errore.</span><span class="sxs-lookup"><span data-stu-id="db3e7-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="db3e7-107">Nome</span><span class="sxs-lookup"><span data-stu-id="db3e7-107">Name</span></span>    | <span data-ttu-id="db3e7-108">Valore</span><span class="sxs-lookup"><span data-stu-id="db3e7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="db3e7-109">Scope</span><span class="sxs-lookup"><span data-stu-id="db3e7-109">Scope</span></span>   |<span data-ttu-id="db3e7-110">Modalità trasparente</span><span class="sxs-lookup"><span data-stu-id="db3e7-110">Transparent</span></span>|
|<span data-ttu-id="db3e7-111">Version</span><span class="sxs-lookup"><span data-stu-id="db3e7-111">Version</span></span>|<span data-ttu-id="db3e7-112">4.5</span><span class="sxs-lookup"><span data-stu-id="db3e7-112">4.5</span></span>|
|<span data-ttu-id="db3e7-113">Type</span><span class="sxs-lookup"><span data-stu-id="db3e7-113">Type</span></span>|<span data-ttu-id="db3e7-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="db3e7-114">Runtime</span></span>|
