---
title: Generazione SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854361"
---
# <a name="sql-generation"></a><span data-ttu-id="dffb4-102">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="dffb4-102">SQL Generation</span></span>
<span data-ttu-id="dffb4-103">Quando si scrive un provider per la Entity Framework, è necessario tradurre Entity Framework alberi dei comandi in SQL che possono essere riconoscibili da un database specifico, ad esempio Transact-SQL per SQL Server o PL/SQL per Oracle.</span><span class="sxs-lookup"><span data-stu-id="dffb4-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="dffb4-104">In questa sezione verrà illustrato come sviluppare un componente di generazione SQL (per le query SELECT) per un provider di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="dffb4-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="dffb4-105">Per informazioni sulle query di inserimento, aggiornamento ed eliminazione, vedere la pagina relativa alla [modifica della generazione SQL](modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="dffb4-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="dffb4-106">Per comprendere questa sezione, è necessario avere familiarità con il Entity Framework e il modello di provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dffb4-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="dffb4-107">È inoltre necessario conoscere gli alberi dei comandi e <xref:System.Data.Common.CommandTrees.DbExpression>.</span><span class="sxs-lookup"><span data-stu-id="dffb4-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="dffb4-108">Ruolo del modulo di generazione SQL</span><span class="sxs-lookup"><span data-stu-id="dffb4-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="dffb4-109">Il modulo di generazione SQL di un provider di Entity Framework converte una struttura ad albero dei comandi di query specifica in un'unica istruzione SQL SELECT destinata a un database conforme a SQL: 1999.</span><span class="sxs-lookup"><span data-stu-id="dffb4-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="dffb4-110">Se possibile, il codice SQL generato deve contenere alcune query annidate.</span><span class="sxs-lookup"><span data-stu-id="dffb4-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="dffb4-111">Il modulo di generazione SQL non semplifica l'albero dei comandi di query di output.</span><span class="sxs-lookup"><span data-stu-id="dffb4-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="dffb4-112">Il Entity Framework esegue questa operazione, ad esempio eliminando i join e comprimendo i nodi di filtro consecutivi.</span><span class="sxs-lookup"><span data-stu-id="dffb4-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="dffb4-113">La classe <xref:System.Data.Common.DbProviderServices> è il punto di partenza per l'accesso al livello di generazione SQL per convertire gli alberi dei comandi in <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="dffb4-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dffb4-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="dffb4-114">In This Section</span></span>  
 [<span data-ttu-id="dffb4-115">Forma degli alberi dei comandi</span><span class="sxs-lookup"><span data-stu-id="dffb4-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="dffb4-116">Procedure consigliate per la generazione di SQL dagli alberi dei comandi</span><span class="sxs-lookup"><span data-stu-id="dffb4-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="dffb4-117">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="dffb4-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="dffb4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dffb4-118">See also</span></span>

- [<span data-ttu-id="dffb4-119">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="dffb4-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
