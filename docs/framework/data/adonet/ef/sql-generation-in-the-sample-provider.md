---
title: Generazione di comandi SQL nel provider di esempio
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: cba1cec6d7ef0fdf8d4d4cf6c8e44fb325cf6447
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556205"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="b6ee3-102">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="b6ee3-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="b6ee3-103">Il [Provider di esempio Entity Framework](https://go.microsoft.com/fwlink/?LinkId=180616) illustra i nuovi componenti dei provider di dati ADO.NET che supportano il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6ee3-103">The [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="b6ee3-104">Viene usato con database SQL Server 2005 e viene implementato come wrapper per il provider di dati ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="b6ee3-105">Il modulo di generazione SQL del Provider di esempio che, ad eccezione del file DmlSqlGenerator.cssi, si trova al di sotto della cartella di generazione SQL, produce una sola istruzione SQL SELECT usando un oggetto DbQueryCommandTree di input.</span><span class="sxs-lookup"><span data-stu-id="b6ee3-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6ee3-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b6ee3-106">In This Section</span></span>  
 <span data-ttu-id="b6ee3-107">Questa sezione presenta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b6ee3-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="b6ee3-108">Architettura e progettazione</span><span class="sxs-lookup"><span data-stu-id="b6ee3-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="b6ee3-109">Procedura dettagliata: Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="b6ee3-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6ee3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6ee3-110">See Also</span></span>  
 [<span data-ttu-id="b6ee3-111">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="b6ee3-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
