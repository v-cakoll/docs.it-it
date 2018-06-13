---
title: Generazione di comandi SQL nel provider di esempio
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 7275a67927d7692dc943e2555d65d1f7d6e4ba5a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762153"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="2b57e-102">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="2b57e-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="2b57e-103">Il [Provider di esempio Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) illustra i nuovi componenti dei provider di dati ADO.NET che supportano il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b57e-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="2b57e-104">Viene usato con database SQL Server 2005 e viene implementato come wrapper per il provider di dati ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="2b57e-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="2b57e-105">Il modulo di generazione SQL del Provider di esempio che, ad eccezione del file DmlSqlGenerator.cssi, si trova al di sotto della cartella di generazione SQL, produce una sola istruzione SQL SELECT usando un oggetto DbQueryCommandTree di input.</span><span class="sxs-lookup"><span data-stu-id="2b57e-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b57e-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2b57e-106">In This Section</span></span>  
 <span data-ttu-id="2b57e-107">Questa sezione presenta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="2b57e-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="2b57e-108">Architettura e progettazione</span><span class="sxs-lookup"><span data-stu-id="2b57e-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="2b57e-109">Procedura dettagliata: Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="2b57e-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b57e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b57e-110">See Also</span></span>  
 [<span data-ttu-id="2b57e-111">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="2b57e-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
