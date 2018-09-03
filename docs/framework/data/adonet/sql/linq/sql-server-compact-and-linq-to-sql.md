---
title: SQL Server Compact e LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 1229fcb285038875950776a924870c9be6bef13b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479877"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="f09a2-102">SQL Server Compact e LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f09a2-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="f09a2-103">SQL Server Compact è il database predefinito installato con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f09a2-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="f09a2-104">Per altre informazioni, vedere [PAVE su usando SQL Server Compact (Visual Studio)](https://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).</span><span class="sxs-lookup"><span data-stu-id="f09a2-104">For more information, see [PAVE OVER Using SQL Server Compact (Visual Studio)](https://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).</span></span>  
  
 <span data-ttu-id="f09a2-105">Questo argomento vengono illustrate le differenze principali in utilizzo, configurazione, set di funzionalità e ambito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supportano.</span><span class="sxs-lookup"><span data-stu-id="f09a2-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="f09a2-106">Caratteristiche di SQL Server Compact in relazione a LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f09a2-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="f09a2-107">Per impostazione predefinita, SQL Server Compact è installato per tutte le edizioni di Visual Studio ed è pertanto disponibile nel computer di sviluppo per l'uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f09a2-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="f09a2-108">Distribuzione di un'applicazione che Usa SQL Server Compact e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è diverso da quello per un'applicazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f09a2-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="f09a2-109">SQL Server Compact non fa parte di .NET Framework e pertanto deve essere fornito con l'applicazione o scaricato separatamente dal sito Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f09a2-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="f09a2-110">Tenere presente le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="f09a2-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="f09a2-111">SQL Server Compact viene fornito come una DLL che può essere usata direttamente sui file di database (con estensione sdf).</span><span class="sxs-lookup"><span data-stu-id="f09a2-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="f09a2-112">SQL Server Compact viene eseguito nello stesso processo come l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="f09a2-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="f09a2-113">L'efficienza della comunicazione con SQL Server Compact può quindi essere significativamente più elevata rispetto alla comunicazione con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f09a2-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="f09a2-114">D'altra parte, SQL Server Compact richiede l'interoperabilità fra codice gestito e con i relativi costi associati.</span><span class="sxs-lookup"><span data-stu-id="f09a2-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="f09a2-115">Le dimensioni della DLL SQL Server Compact sono piccola.</span><span class="sxs-lookup"><span data-stu-id="f09a2-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="f09a2-116">Questa funzionalità riduce le dimensioni complessive dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f09a2-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="f09a2-117">Il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e lo strumento della riga di comando SQLMetal supportano SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="f09a2-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="f09a2-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] non supporta SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="f09a2-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="f09a2-119">Set di funzionalità</span><span class="sxs-lookup"><span data-stu-id="f09a2-119">Feature Set</span></span>  
 <span data-ttu-id="f09a2-120">Il set di funzionalità di SQL Server Compact è molto più semplice rispetto al set di funzionalità di SQL Server nei modi seguenti che possono influire sulla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applicazioni:</span><span class="sxs-lookup"><span data-stu-id="f09a2-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="f09a2-121">SQL Server Compact non supporta stored procedure o visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f09a2-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="f09a2-122">SQL Server Compact supporta solo un subset di tipi di dati e funzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="f09a2-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="f09a2-123">SQL Server Compact supporta solo un subset di costrutti SQL.</span><span class="sxs-lookup"><span data-stu-id="f09a2-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="f09a2-124">SQL Server Compact fornisce solo un'utilità di ottimizzazione con funzionalità minime.</span><span class="sxs-lookup"><span data-stu-id="f09a2-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="f09a2-125">È possibile che alcune query potrebbero raggiungere il timeout.</span><span class="sxs-lookup"><span data-stu-id="f09a2-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="f09a2-126">SQL Server Compact non supporta il trust parziale.</span><span class="sxs-lookup"><span data-stu-id="f09a2-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f09a2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f09a2-127">See Also</span></span>  
 [<span data-ttu-id="f09a2-128">Riferimento</span><span class="sxs-lookup"><span data-stu-id="f09a2-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
