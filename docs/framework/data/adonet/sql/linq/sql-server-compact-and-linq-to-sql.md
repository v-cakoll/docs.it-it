---
title: SQL Server Compact e LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: b5a1a12018bd85cf313c1841e6b67ab2edf67b4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792541"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="4cf12-102">SQL Server Compact e LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4cf12-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="4cf12-103">SQL Server Compact è il database predefinito installato con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4cf12-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="4cf12-104">Per ulteriori informazioni, vedere [utilizzo di SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="4cf12-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="4cf12-105">In questo argomento vengono descritte le differenze principali relative all'utilizzo, alla configurazione, ai set di funzionalità [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e all'ambito del supporto.</span><span class="sxs-lookup"><span data-stu-id="4cf12-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="4cf12-106">Caratteristiche di SQL Server Compact in relazione a LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4cf12-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="4cf12-107">Per impostazione predefinita, SQL Server Compact viene installato per tutte le edizioni di Visual Studio ed è pertanto disponibile nel computer di sviluppo per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]l'uso con.</span><span class="sxs-lookup"><span data-stu-id="4cf12-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="4cf12-108">Ma la distribuzione di un'applicazione che usa SQL Server Compact [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e differisce da quella per un'applicazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cf12-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="4cf12-109">SQL Server Compact non fa parte di .NET Framework e pertanto deve essere fornito con l'applicazione o scaricato separatamente dal sito Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4cf12-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="4cf12-110">Tenere presente le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="4cf12-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="4cf12-111">SQL Server Compact viene fornito come una DLL che può essere usata direttamente sui file di database (con estensione sdf).</span><span class="sxs-lookup"><span data-stu-id="4cf12-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="4cf12-112">SQL Server Compact viene eseguito nello stesso processo dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="4cf12-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="4cf12-113">L'efficienza della comunicazione con SQL Server Compact può quindi essere significativamente più elevata rispetto alla comunicazione con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cf12-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="4cf12-114">D'altra parte, SQL Server Compact richiede l'interoperabilità tra codice gestito e non gestito con i costi di supervisore.</span><span class="sxs-lookup"><span data-stu-id="4cf12-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="4cf12-115">Le dimensioni della DLL SQL Server Compact sono limitate.</span><span class="sxs-lookup"><span data-stu-id="4cf12-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="4cf12-116">Questa funzionalità riduce le dimensioni complessive dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4cf12-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="4cf12-117">Il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e lo strumento della riga di comando SQLMetal supportano SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="4cf12-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="4cf12-118">Il Object Relational Designer non supporta SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="4cf12-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="4cf12-119">Set di funzionalità</span><span class="sxs-lookup"><span data-stu-id="4cf12-119">Feature Set</span></span>  
 <span data-ttu-id="4cf12-120">Il set di funzionalità SQL Server Compact è molto più semplice rispetto al set di funzionalità di SQL Server nei modi seguenti che possono [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] influire sulle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf12-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="4cf12-121">SQL Server Compact non supporta stored procedure o visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4cf12-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="4cf12-122">SQL Server Compact supporta solo un subset di tipi di dati e funzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="4cf12-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="4cf12-123">SQL Server Compact supporta solo un subset di costrutti SQL.</span><span class="sxs-lookup"><span data-stu-id="4cf12-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="4cf12-124">SQL Server Compact fornisce solo un'utilità di ottimizzazione con funzionalità minime.</span><span class="sxs-lookup"><span data-stu-id="4cf12-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="4cf12-125">Potrebbe verificarsi il timeout di alcune query.</span><span class="sxs-lookup"><span data-stu-id="4cf12-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="4cf12-126">SQL Server Compact non supporta il trust parziale.</span><span class="sxs-lookup"><span data-stu-id="4cf12-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf12-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cf12-127">See also</span></span>

- [<span data-ttu-id="4cf12-128">Riferimento</span><span class="sxs-lookup"><span data-stu-id="4cf12-128">Reference</span></span>](reference.md)
