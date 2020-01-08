---
title: Esecuzione di query sul database
ms.date: 03/30/2017
ms.assetid: eefb8b0c-ff07-4e86-a3d3-567479523fe9
ms.openlocfilehash: 6ca402600d43eb84c31c499d3f93aca95d4ea1d9
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634313"
---
# <a name="querying-the-database"></a><span data-ttu-id="4ef33-102">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="4ef33-102">Querying the Database</span></span>
<span data-ttu-id="4ef33-103">In questo gruppo di argomenti viene descritto come sviluppare ed eseguire query nei progetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef33-103">This group of topics describes how to develop and execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ef33-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4ef33-104">In This Section</span></span>  
 [<span data-ttu-id="4ef33-105">Procedura: eseguire una query per ottenere informazioni</span><span class="sxs-lookup"><span data-stu-id="4ef33-105">How to: Query for Information</span></span>](how-to-query-for-information.md)  
 <span data-ttu-id="4ef33-106">Viene illustrato brevemente il modo in cui le query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono fondamentalmente le stesse delle query LINQ.</span><span class="sxs-lookup"><span data-stu-id="4ef33-106">Briefly shows how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are basically the same as LINQ queries generally.</span></span>  
  
 [<span data-ttu-id="4ef33-107">Procedura: recuperare informazioni in sola lettura</span><span class="sxs-lookup"><span data-stu-id="4ef33-107">How to: Retrieve Information As Read-Only</span></span>](how-to-retrieve-information-as-read-only.md)  
 <span data-ttu-id="4ef33-108">Viene descritto come migliorare le prestazioni di esecuzione delle query quando non sono pianificate modifiche dei dati.</span><span class="sxs-lookup"><span data-stu-id="4ef33-108">Describes how to increase query performance when no change to the data is planned.</span></span>  
  
 [<span data-ttu-id="4ef33-109">Procedura: controllare la quantità di dati correlati recuperata</span><span class="sxs-lookup"><span data-stu-id="4ef33-109">How to: Control How Much Related Data Is Retrieved</span></span>](how-to-control-how-much-related-data-is-retrieved.md)  
 <span data-ttu-id="4ef33-110">Viene descritto come controllare quali dati correlati vengono recuperati insieme con la destinazione principale.</span><span class="sxs-lookup"><span data-stu-id="4ef33-110">Describes how to control which related data is retrieved together with the main target.</span></span>  
  
 [<span data-ttu-id="4ef33-111">Procedura: filtrare dati correlati</span><span class="sxs-lookup"><span data-stu-id="4ef33-111">How to: Filter Related Data</span></span>](how-to-filter-related-data.md)  
 <span data-ttu-id="4ef33-112">Viene descritto come recuperare dati correlati usando una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="4ef33-112">Describes how to retrieve related data by using a sub-query.</span></span>  
  
 [<span data-ttu-id="4ef33-113">Procedura: disattivare il caricamento posticipato</span><span class="sxs-lookup"><span data-stu-id="4ef33-113">How to: Turn Off Deferred Loading</span></span>](how-to-turn-off-deferred-loading.md)  
 <span data-ttu-id="4ef33-114">Viene descritto come disattivare il caricamento posticipato (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="4ef33-114">Describes how to turn off deferred loading.</span></span>  
  
 [<span data-ttu-id="4ef33-115">Procedura: eseguire direttamente query SQL</span><span class="sxs-lookup"><span data-stu-id="4ef33-115">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)  
 <span data-ttu-id="4ef33-116">Viene descritto come inviare query usando il linguaggio SQL.</span><span class="sxs-lookup"><span data-stu-id="4ef33-116">Describes how to submit queries by using SQL language.</span></span>  
  
 [<span data-ttu-id="4ef33-117">Procedura: archiviare e riutilizzare query</span><span class="sxs-lookup"><span data-stu-id="4ef33-117">How to: Store and Reuse Queries</span></span>](how-to-store-and-reuse-queries.md)  
 <span data-ttu-id="4ef33-118">Viene descritto come compilare una query una volta e usarla quindi più volte con parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="4ef33-118">Describes how to compile a query one time but use it multiple times with different parameters.</span></span>  
  
 [<span data-ttu-id="4ef33-119">Procedura: gestire le chiavi composite nelle query</span><span class="sxs-lookup"><span data-stu-id="4ef33-119">How to: Handle Composite Keys in Queries</span></span>](how-to-handle-composite-keys-in-queries.md)  
 <span data-ttu-id="4ef33-120">Viene descritto come includere più di una colonna in una query in cui l'operatore accetta un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="4ef33-120">Describes how to include more than one column in a query where the operator takes only a single argument.</span></span>  
  
 [<span data-ttu-id="4ef33-121">Procedura: recuperare molti oggetti contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="4ef33-121">How to: Retrieve Many Objects At Once</span></span>](how-to-retrieve-many-objects-at-once.md)  
 <span data-ttu-id="4ef33-122">Viene descritto come usare <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ef33-122">Describes how to use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="4ef33-123">Procedura: filtrare a livello di DataContext</span><span class="sxs-lookup"><span data-stu-id="4ef33-123">How to: Filter at the DataContext Level</span></span>](how-to-filter-at-the-datacontext-level.md)  
 <span data-ttu-id="4ef33-124">Viene descritto un diverso utilizzo di <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ef33-124">Describes another use of <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="4ef33-125">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="4ef33-125">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="4ef33-126">Vengono forniti molti esempi di query.</span><span class="sxs-lookup"><span data-stu-id="4ef33-126">Provides many examples of queries.</span></span>
