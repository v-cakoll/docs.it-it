---
title: Metodi System.DateTimeOffset
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: 7fc6502f899e953637d23c0d54cc5fe615c38eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363312"
---
# <a name="systemdatetimeoffset-methods"></a><span data-ttu-id="29d6b-102">Metodi System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="29d6b-102">System.DateTimeOffset Methods</span></span>
<span data-ttu-id="29d6b-103">Una volta eseguito il mapping nel modello a oggetti o nel file di mapping esterno, LINQ to SQL consente di chiamare la maggior parte degli operatori, delle proprietà e dei metodi <xref:System.DateTimeOffset?displayProperty=nameWithType> dalle query LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="29d6b-103">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call most of the <xref:System.DateTimeOffset?displayProperty=nameWithType> methods, operators, and properties from within your LINQ to SQL queries.</span></span>  
  
 <span data-ttu-id="29d6b-104">Gli unici metodi non supportati sono quelli ereditati da <xref:System.Object?displayProperty=nameWithType> che non hanno senso nel contesto delle query LINQ to SQL, ad esempio `Finalize`, `GetHashCode`, `GetType` e `MemberwiseClone`.</span><span class="sxs-lookup"><span data-stu-id="29d6b-104">The only methods not supported are those inherited from <xref:System.Object?displayProperty=nameWithType> that do not make sense in the context of LINQ to SQL queries, such as: `Finalize`, `GetHashCode`, `GetType`, and `MemberwiseClone`.</span></span> <span data-ttu-id="29d6b-105">Questi metodi non sono supportati in quanto LINQ to SQL non è in grado di convertirli per l'esecuzione in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="29d6b-105">These methods are not supported because LINQ to SQL cannot translate them for execution on the SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29d6b-106">La struttura di <xref:System.DateTimeOffset?displayProperty=nameWithType> CLR (Common Language Runtime) e la possibilità da eseguire il mapping a una colonna `DATETIMEOFFSET` SQL con LINQ to SQL richiedono .NET Framework 3.5 SP1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="29d6b-106">The common language runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> structure, and the ability to map it to a SQL `DATETIMEOFFSET` column with LINQ to SQL, requires the .NET Framework 3.5 SP1 or beyond.</span></span> <span data-ttu-id="29d6b-107">La colonna `DATETIMEOFFSET` SQL è disponibile solo in Microsoft SQL Server 2008 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="29d6b-107">The SQL `DATETIMEOFFSET` column is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="29d6b-108">Metodi SQLMethods relativi a data e ora</span><span class="sxs-lookup"><span data-stu-id="29d6b-108">SQLMethods Date and Time Methods</span></span>  
 <span data-ttu-id="29d6b-109">Oltre ai metodi offerti dalla struttura di <xref:System.DateTimeOffset>, LINQ to SQL offre i metodi della classe <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> elencati nella tabella seguente per l'uso di data e ora.</span><span class="sxs-lookup"><span data-stu-id="29d6b-109">In addition to the methods offered by the <xref:System.DateTimeOffset> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="29d6b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29d6b-110">See Also</span></span>  
 [<span data-ttu-id="29d6b-111">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="29d6b-111">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="29d6b-112">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="29d6b-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="29d6b-113">Mapping del tipo SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="29d6b-113">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
