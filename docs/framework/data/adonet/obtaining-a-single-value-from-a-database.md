---
title: Recupero di un valore singolo da un database
description: Informazioni su come restituire un singolo valore in ADO.NET. Questo codice di esempio restituisce il valore della colonna Identity per un record inserito.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286702"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="ea40d-104">Recupero di un valore singolo da un database</span><span class="sxs-lookup"><span data-stu-id="ea40d-104">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="ea40d-105">Può essere necessario restituire informazioni del database costituite semplicemente da un singolo valore anziché da una tabella o da un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="ea40d-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="ea40d-106">È ad esempio possibile che si desideri restituire il risultato di una funzione di aggregazione, ad esempio COUNT ( \* ), Sum (price) o AVG (Quantity).</span><span class="sxs-lookup"><span data-stu-id="ea40d-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="ea40d-107">L'oggetto **Command** fornisce la possibilità di restituire valori singoli usando il metodo **ExecuteScalar** .</span><span class="sxs-lookup"><span data-stu-id="ea40d-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="ea40d-108">Il metodo **ExecuteScalar** restituisce, come valore scalare, il valore della prima colonna della prima riga del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="ea40d-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="ea40d-109">Nell'esempio di codice seguente viene inserito un nuovo valore nel database usando un <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="ea40d-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="ea40d-110">Per restituire il valore della colonna Identity per il record inserito, viene usato il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea40d-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ea40d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea40d-111">See also</span></span>

- [<span data-ttu-id="ea40d-112">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="ea40d-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="ea40d-113">Esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="ea40d-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="ea40d-114">DbConnection, DbCommand e DbException</span><span class="sxs-lookup"><span data-stu-id="ea40d-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="ea40d-115">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea40d-115">ADO.NET Overview</span></span>](ado-net-overview.md)
