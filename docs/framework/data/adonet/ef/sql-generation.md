---
title: Generazione SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6b2d4ba925af61f89b47c494f5fb17f5f9f0d995
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="sql-generation"></a><span data-ttu-id="3279a-102">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="3279a-102">SQL Generation</span></span>
<span data-ttu-id="3279a-103">Quando si scrive un provider per [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], è necessario convertire gli alberi dei comandi di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] in codice SQL comprensibile per un determinato database, ad esempio Transact-SQL per SQL Server o PL/SQL per Oracle.</span><span class="sxs-lookup"><span data-stu-id="3279a-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="3279a-104">Contenuto della sezione viene illustrato come sviluppare un componente di generazione SQL (per le query SELECT) per un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3279a-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="3279a-105">Per informazioni sull'inserimento, aggiornamento, eliminazione di query, vedere [generazione SQL di modifica](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="3279a-105">For information about insert, update, and delete queries, see [Modification SQL Generation](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="3279a-106">Per comprendere questa sezione è necessario avere familiarità con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e il modello di provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="3279a-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="3279a-107">È inoltre necessario conoscere gli alberi dei comandi e <xref:System.Data.Common.CommandTrees.DbExpression>.</span><span class="sxs-lookup"><span data-stu-id="3279a-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="3279a-108">Ruolo del modulo di generazione SQL</span><span class="sxs-lookup"><span data-stu-id="3279a-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="3279a-109">Il modulo di generazione SQL di un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] converte un determinato albero dei comandi di query in una singola istruzione SQL SELECT destinata a un database conforme a SQL:1999.</span><span class="sxs-lookup"><span data-stu-id="3279a-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="3279a-110">Se possibile, il codice SQL generato deve contenere alcune query annidate.</span><span class="sxs-lookup"><span data-stu-id="3279a-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="3279a-111">Il modulo di generazione SQL non semplifica l'albero dei comandi di query di output.</span><span class="sxs-lookup"><span data-stu-id="3279a-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="3279a-112">Tale semplificazione viene garantita da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] mediante, ad esempio, l'eliminazione di join e la compressione di nodi di filtro consecutivi.</span><span class="sxs-lookup"><span data-stu-id="3279a-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="3279a-113">La classe <xref:System.Data.Common.DbProviderServices> è il punto di partenza per l'accesso al livello di generazione SQL per convertire gli alberi dei comandi in <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="3279a-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3279a-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3279a-114">In This Section</span></span>  
 [<span data-ttu-id="3279a-115">Forma degli alberi dei comandi</span><span class="sxs-lookup"><span data-stu-id="3279a-115">The Shape of the Command Trees</span></span>](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="3279a-116">Procedure consigliate per la generazione di SQL dagli alberi dei comandi</span><span class="sxs-lookup"><span data-stu-id="3279a-116">Generating SQL from Command Trees - Best Practices</span></span>](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="3279a-117">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="3279a-117">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="3279a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3279a-118">See Also</span></span>  
 [<span data-ttu-id="3279a-119">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="3279a-119">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
