---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235536"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="d77d9-101">I dati sql_variant usano regole di confronto sql_variant invece delle regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="d77d9-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d77d9-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d77d9-102">Details</span></span>|<span data-ttu-id="d77d9-103">I dati di <code>sql_variant</code> usano regole di confronto di <code>sql_variant</code> anziché regole di confronto di database.</span><span class="sxs-lookup"><span data-stu-id="d77d9-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="d77d9-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d77d9-104">Suggestion</span></span>|<span data-ttu-id="d77d9-105">Questa modifica risolve il possibile danneggiamento dei dati se le regole di confronto del database differiscono da quelle di <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="d77d9-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="d77d9-106">Le applicazioni basate su dati errati possono generare un errore.</span><span class="sxs-lookup"><span data-stu-id="d77d9-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="d77d9-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="d77d9-107">Scope</span></span>|<span data-ttu-id="d77d9-108">Trasparente</span><span class="sxs-lookup"><span data-stu-id="d77d9-108">Transparent</span></span>|
|<span data-ttu-id="d77d9-109">Versione</span><span class="sxs-lookup"><span data-stu-id="d77d9-109">Version</span></span>|<span data-ttu-id="d77d9-110">4.5</span><span class="sxs-lookup"><span data-stu-id="d77d9-110">4.5</span></span>|
|<span data-ttu-id="d77d9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d77d9-111">Type</span></span>|<span data-ttu-id="d77d9-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="d77d9-112">Runtime</span></span>|
