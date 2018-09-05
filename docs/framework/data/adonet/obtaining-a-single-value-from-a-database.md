---
title: Recupero di un valore singolo da un database
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 1a0d92c7acad58d3618c3f50b7463022352cf542
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741961"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="74d40-102">Recupero di un valore singolo da un database</span><span class="sxs-lookup"><span data-stu-id="74d40-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="74d40-103">Può essere necessario restituire informazioni del database costituite semplicemente da un singolo valore anziché da una tabella o da un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="74d40-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="74d40-104">Ad esempio, è possibile restituire il risultato di una funzione di aggregazione, ad esempio COUNT (\*), SUM (price) o AVG (Quantity).</span><span class="sxs-lookup"><span data-stu-id="74d40-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="74d40-105">Il **comandi** oggetto offre la possibilità di restituire singoli valori usando la **ExecuteScalar** (metodo).</span><span class="sxs-lookup"><span data-stu-id="74d40-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="74d40-106">Il **ExecuteScalar** restituisce come un valore scalare, il valore della prima colonna della prima riga del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="74d40-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="74d40-107">Nell'esempio di codice seguente viene inserito un nuovo valore nel database usando un <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="74d40-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="74d40-108">Per restituire il valore della colonna Identity per il record inserito, viene usato il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>.</span><span class="sxs-lookup"><span data-stu-id="74d40-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="74d40-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d40-109">See Also</span></span>  
 [<span data-ttu-id="74d40-110">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="74d40-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="74d40-111">Esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="74d40-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="74d40-112">DbConnection, DbCommand e DbException</span><span class="sxs-lookup"><span data-stu-id="74d40-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="74d40-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="74d40-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
