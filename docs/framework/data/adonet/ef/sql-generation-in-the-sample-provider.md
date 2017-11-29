---
title: Generazione di comandi SQL nel provider di esempio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 58a49f7bf5d385466810a3c59bda748ef66d5840
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="b6a9f-102">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="b6a9f-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="b6a9f-103">Il [Provider di esempio Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) illustra i nuovi componenti dei provider di dati ADO.NET che supportano il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6a9f-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="b6a9f-104">Viene usato con database SQL Server 2005 e viene implementato come wrapper per il provider di dati ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="b6a9f-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="b6a9f-105">Il modulo di generazione SQL del Provider di esempio che, ad eccezione del file DmlSqlGenerator.cssi, si trova al di sotto della cartella di generazione SQL, produce una sola istruzione SQL SELECT usando un oggetto DbQueryCommandTree di input.</span><span class="sxs-lookup"><span data-stu-id="b6a9f-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6a9f-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b6a9f-106">In This Section</span></span>  
 <span data-ttu-id="b6a9f-107">Questa sezione presenta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b6a9f-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="b6a9f-108">Architettura e progettazione</span><span class="sxs-lookup"><span data-stu-id="b6a9f-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="b6a9f-109">Procedura dettagliata: Generazione di SQL</span><span class="sxs-lookup"><span data-stu-id="b6a9f-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6a9f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6a9f-110">See Also</span></span>  
 [<span data-ttu-id="b6a9f-111">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="b6a9f-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
