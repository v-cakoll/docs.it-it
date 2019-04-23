---
title: Oggetti REF CURSOR Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: b23b0f07d7755fed820481a3ad1fe831ae3f5224
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213168"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="0ec50-102">Oggetti REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="0ec50-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="0ec50-103">Il Provider di dati .NET Framework per Oracle supporta Oracle **REF CURSOR** tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0ec50-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="0ec50-104">Quando si usa il provider di dati per usare il tipo di dati REF CURSOR Oracle, considerare i seguenti comportamenti.</span><span class="sxs-lookup"><span data-stu-id="0ec50-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec50-105">Alcuni comportamenti si differenziano da quelli del provider Microsoft OLE DB per Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="0ec50-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
-   <span data-ttu-id="0ec50-106">Per motivi di prestazioni, il Provider di dati per Oracle non associa automaticamente **REF CURSOR** i tipi di dati, come MSDAORA, a meno che non specificati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="0ec50-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
-   <span data-ttu-id="0ec50-107">Il provider di dati non supporta alcuna sequenza di escape ODBC, incluso il carattere di escape {resultset} usato per specificare i parametri REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="0ec50-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
-   <span data-ttu-id="0ec50-108">Per eseguire una stored procedure che restituisce i REF CURSOR, è necessario definire i parametri in di <xref:System.Data.OracleClient.OracleParameterCollection> con un <xref:System.Data.OracleClient.OracleType> dei **cursore** e un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> di **Output**.</span><span class="sxs-lookup"><span data-stu-id="0ec50-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="0ec50-109">Il provider di dati supporta l'associazione dei REF CURSOR solo come parametri di output.</span><span class="sxs-lookup"><span data-stu-id="0ec50-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="0ec50-110">I REF CURSOR come parametri di input non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0ec50-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
-   <span data-ttu-id="0ec50-111">Il recupero di un tipo <xref:System.Data.OracleClient.OracleDataReader> dal valore del parametro non è supportato.</span><span class="sxs-lookup"><span data-stu-id="0ec50-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="0ec50-112">I valori sono di tipo <xref:System.DBNull> dopo l'esecuzione del comando.</span><span class="sxs-lookup"><span data-stu-id="0ec50-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
-   <span data-ttu-id="0ec50-113">Gli unici **CommandBehavior** valore dell'enumerazione che funziona con oggetti REF CURSOR (ad esempio, quando si chiama <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) viene **CloseConnection**; tutti gli altri vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="0ec50-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
-   <span data-ttu-id="0ec50-114">L'ordine dei REF CURSOR nel **OracleDataReader** dipende dall'ordine i parametri nel **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="0ec50-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="0ec50-115">La proprietà <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="0ec50-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
-   <span data-ttu-id="0ec50-116">Il codice PL/SQL **tabella** tipo di dati non è supportato.</span><span class="sxs-lookup"><span data-stu-id="0ec50-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="0ec50-117">I REF CURSOR, tuttavia, sono più efficaci.</span><span class="sxs-lookup"><span data-stu-id="0ec50-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="0ec50-118">Se è necessario usare una **tabella** tipo di dati, usare il Provider di dati OLE DB .NET con MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="0ec50-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ec50-119">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0ec50-119">In This Section</span></span>  
 [<span data-ttu-id="0ec50-120">Esempi di REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="0ec50-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="0ec50-121">Vengono presentati tre esempi che illustrano l'uso del tipo di dati REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="0ec50-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="0ec50-122">Parametri REF CURSOR in un oggetto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="0ec50-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="0ec50-123">Viene illustrato come eseguire una procedura stored PL/SQL che restituisce un parametro REF CURSOR e legge il valore come un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="0ec50-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="0ec50-124">Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="0ec50-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="0ec50-125">Viene illustrato come eseguire una procedura stored PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="0ec50-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="0ec50-126">Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="0ec50-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="0ec50-127">Viene illustrato come eseguire una stored procedure PL/SQL che restituisce due parametri REF CURSOR e la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.</span><span class="sxs-lookup"><span data-stu-id="0ec50-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec50-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ec50-128">See also</span></span>

- [<span data-ttu-id="0ec50-129">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0ec50-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="0ec50-130">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="0ec50-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
