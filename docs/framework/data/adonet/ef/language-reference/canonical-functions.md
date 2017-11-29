---
title: Funzioni canoniche
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b80eeedc67678d703664eb705408a72b7e4a2274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="canonical-functions"></a><span data-ttu-id="fad27-102">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-102">Canonical Functions</span></span>
<span data-ttu-id="fad27-103">Contenuto della sezione vengono illustrate le funzioni canoniche supportate da tutti i provider di dati e che possono essere usate da tutte le tecnologie di query.</span><span class="sxs-lookup"><span data-stu-id="fad27-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="fad27-104">Le funzioni canoniche non possono essere estese da un provider.</span><span class="sxs-lookup"><span data-stu-id="fad27-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="fad27-105">Queste funzioni canoniche vengono convertite nella funzionalità dell'origine dati corrispondente per il provider.</span><span class="sxs-lookup"><span data-stu-id="fad27-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="fad27-106">In questo modo è possibile esprimere le chiamate alle funzioni con un formato comune per tutte le origini dati.</span><span class="sxs-lookup"><span data-stu-id="fad27-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="fad27-107">Poiché queste funzioni canoniche sono indipendenti dalle origini dati, i relativi tipi di argomento e tipi restituiti sono definiti in termini di tipi nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="fad27-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="fad27-108">Alcune origini dati potrebbero tuttavia non supportare tutti i tipi nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="fad27-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="fad27-109">Quando si usano funzioni canoniche in una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)], la funzione appropriata viene chiamata nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fad27-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="fad27-110">Per tutte le funzioni canoniche sono specificati in modo esplicito sia il comportamento in caso di input null che le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="fad27-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="fad27-111">I provider dell'archivio devono essere conformi a tale comportamento, ma questo comportamento non viene applicato da [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fad27-111">Store providers should comply with that behavior, but [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="fad27-112">Per gli scenari LINQ, le query eseguite sul [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] comportano il mapping di metodi CLR ai metodi nell'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="fad27-112">For LINQ scenarios, queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="fad27-113">I metodi CLR sono mappati alle funzioni canoniche, pertanto un set di metodi specifico può essere mappato correttamente indipendentemente dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fad27-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="fad27-114">Spazio dei nomi delle funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-114">Canonical Functions Namespace</span></span>  
 <span data-ttu-id="fad27-115">Lo spazio dei nomi per le funzioni canoniche è <xref:System.Data.Metadata.Edm>.</span><span class="sxs-lookup"><span data-stu-id="fad27-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="fad27-116">Lo spazio dei nomi <xref:System.Data.Metadata.Edm> viene incluso automaticamente in tutte le query.</span><span class="sxs-lookup"><span data-stu-id="fad27-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="fad27-117">Se tuttavia viene importato un altro spazio dei nomi contenente una funzione con lo stesso nome di una funzione canonica (nello spazio dei nomi <xref:System.Data.Metadata.Edm>), è necessario specificare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fad27-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fad27-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fad27-118">In This Section</span></span>  
 [<span data-ttu-id="fad27-119">Funzioni canoniche di aggregazione</span><span class="sxs-lookup"><span data-stu-id="fad27-119">Aggregate Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 <span data-ttu-id="fad27-120">Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="fad27-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="fad27-121">Funzioni matematiche canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-121">Math Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 <span data-ttu-id="fad27-122">Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] matematiche.</span><span class="sxs-lookup"><span data-stu-id="fad27-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="fad27-123">Funzioni stringa canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-123">String Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 <span data-ttu-id="fad27-124">Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="fad27-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="fad27-125">Funzioni data e ora canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-125">Date and Time Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 <span data-ttu-id="fad27-126">Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] di data e ora.</span><span class="sxs-lookup"><span data-stu-id="fad27-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="fad27-127">Bit per bit funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-127">Bitwise Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 <span data-ttu-id="fad27-128">Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bit per bit.</span><span class="sxs-lookup"><span data-stu-id="fad27-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="fad27-129">Funzioni spaziali</span><span class="sxs-lookup"><span data-stu-id="fad27-129">Spatial Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 <span data-ttu-id="fad27-130">Vengono illustrate le funzioni canoniche spaziali di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fad27-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="fad27-131">Altre funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="fad27-131">Other Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 <span data-ttu-id="fad27-132">Vengono illustrate le funzioni non classificate come bit per bit, di data e ora, per i valori stringa, matematiche o di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="fad27-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad27-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad27-133">See Also</span></span>  
 [<span data-ttu-id="fad27-134">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fad27-134">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="fad27-135">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fad27-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="fad27-136">Modello concettuale canonico per i Mapping delle funzioni di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fad27-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [<span data-ttu-id="fad27-137">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="fad27-137">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
