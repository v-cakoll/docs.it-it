---
title: Generazione di comandi SQL nel provider di esempio
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854313"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="8e389-102">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="8e389-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="8e389-103">Il [provider di esempio Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) illustra i nuovi componenti dei provider di dati ADO.NET che supportano l'Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8e389-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the Entity Framework.</span></span>  <span data-ttu-id="8e389-104">Viene usato con database SQL Server 2005 e viene implementato come wrapper per il provider di dati ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="8e389-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="8e389-105">Il modulo di generazione SQL del Provider di esempio che, ad eccezione del file DmlSqlGenerator.cssi, si trova al di sotto della cartella di generazione SQL, produce una sola istruzione SQL SELECT usando un oggetto DbQueryCommandTree di input.</span><span class="sxs-lookup"><span data-stu-id="8e389-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e389-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8e389-106">In This Section</span></span>  
 <span data-ttu-id="8e389-107">Questa sezione presenta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8e389-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="8e389-108">Architettura e progettazione</span><span class="sxs-lookup"><span data-stu-id="8e389-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="8e389-109">Procedura dettagliata: Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="8e389-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e389-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e389-110">See also</span></span>

- [<span data-ttu-id="8e389-111">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="8e389-111">SQL Generation</span></span>](sql-generation.md)
