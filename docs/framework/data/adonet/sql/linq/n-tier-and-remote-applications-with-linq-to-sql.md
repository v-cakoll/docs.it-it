---
title: "Applicazioni a più livelli e remote con LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 272c125096e08819a7f70b830e1f359a760f687f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="92543-102">Applicazioni a più livelli e remote con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="92543-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="92543-103">È possibile creare applicazioni a più livelli che usano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92543-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="92543-104">In genere, il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] contesto dei dati, le classi di entità e logica di costruzione delle query si trovano nel livello intermedio come livello di accesso ai dati (DAL).</span><span class="sxs-lookup"><span data-stu-id="92543-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="92543-105">La regola business e i dati non persistenti possono essere implementati completamente in classi e metodi parziali di entità e nel contesto dati oppure possono essere implementati in classi separate.</span><span class="sxs-lookup"><span data-stu-id="92543-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>  
  
 <span data-ttu-id="92543-106">Il livello client o di presentazione chiama i metodi nell'interfaccia remota del livello intermedio e il DAL di tale livello eseguirà le query o le stored procedure di cui è stato eseguito il mapping ai metodi <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="92543-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="92543-107">Il livello intermedio in genere restituisce i dati ai client come rappresentazioni XML di entità o oggetti proxy.</span><span class="sxs-lookup"><span data-stu-id="92543-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>  
  
 <span data-ttu-id="92543-108">Nel livello intermedio, le entità vengono create dal contesto dati che tiene traccia dello stato e gestisce il caricamento posticipato e l'invio delle modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="92543-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="92543-109">Queste entità sono "collegate" all'oggetto `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="92543-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="92543-110">Tuttavia, le entità vengono disconnesse dopo l'invio a un altro livello mediante la serializzazione, ovvero `DataContext` non tiene più traccia del relativo stato.</span><span class="sxs-lookup"><span data-stu-id="92543-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="92543-111">Le entità inviate dal client per gli aggiornamenti devono essere ricollegate al contesto dati prima che [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sia in grado di inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="92543-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="92543-112">Il client ha lo scopo di fornire al livello intermedio i valori originali e/o i timestamp se richiesti per i controlli di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="92543-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>  
  
 <span data-ttu-id="92543-113">Nelle applicazioni ASP.NET, <xref:System.Web.UI.WebControls.LinqDataSource> gestisce gran parte di questa complessità.</span><span class="sxs-lookup"><span data-stu-id="92543-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="92543-114">Per ulteriori informazioni, vedere [NIB: Panoramica del controllo Server Web LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).</span><span class="sxs-lookup"><span data-stu-id="92543-114">For more information, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="92543-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="92543-115">Additional Resources</span></span>  
 <span data-ttu-id="92543-116">Per altre informazioni sull'implementazione delle applicazioni a più livelli che usano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="92543-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>  
  
-   [<span data-ttu-id="92543-117">Più livelli di LINQ to SQL con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="92543-117">LINQ to SQL N-Tier with ASP.NET</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [<span data-ttu-id="92543-118">Più livelli di LINQ to SQL con Servizi Web</span><span class="sxs-lookup"><span data-stu-id="92543-118">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [<span data-ttu-id="92543-119">LINQ to SQL con applicazioni client/server strettamente accoppiate</span><span class="sxs-lookup"><span data-stu-id="92543-119">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [<span data-ttu-id="92543-120">Implementazione della logica di business a più livelli</span><span class="sxs-lookup"><span data-stu-id="92543-120">Implementing N-Tier Business Logic</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [<span data-ttu-id="92543-121">Recupero di dati e operazioni CUD in applicazioni a più livelli (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="92543-121">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 <span data-ttu-id="92543-122">Per ulteriori informazioni sulle applicazioni a più livelli che utilizzano i dataset ADO.NET, vedere [utilizzano set di dati nelle applicazioni a più livelli](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span><span class="sxs-lookup"><span data-stu-id="92543-122">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92543-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92543-123">See Also</span></span>  
 [<span data-ttu-id="92543-124">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="92543-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
