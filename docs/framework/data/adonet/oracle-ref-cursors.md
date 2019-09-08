---
title: Oggetti REF CURSOR Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 7cd29a6a20015c7ce4475b0211cb07f7ee78b530
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794880"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="772f3-102">Oggetti REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="772f3-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="772f3-103">Il .NET Framework provider di dati per Oracle supporta il tipo di dati **ref CURSOR** di Oracle.</span><span class="sxs-lookup"><span data-stu-id="772f3-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="772f3-104">Quando si usa il provider di dati per usare il tipo di dati REF CURSOR Oracle, considerare i seguenti comportamenti.</span><span class="sxs-lookup"><span data-stu-id="772f3-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="772f3-105">Alcuni comportamenti si differenziano da quelli del provider Microsoft OLE DB per Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="772f3-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="772f3-106">Per motivi di prestazioni, il provider di dati per Oracle non associa automaticamente i tipi di dati **ref CURSOR** , come avviene in MSDAORA, a meno che non vengano specificati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="772f3-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="772f3-107">Il provider di dati non supporta alcuna sequenza di escape ODBC, incluso il carattere di escape {resultset} usato per specificare i parametri REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="772f3-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="772f3-108">Per eseguire un stored procedure che restituisce Ref cursors, è <xref:System.Data.OracleClient.OracleParameterCollection> necessario definire i parametri in con un oggetto <xref:System.Data.OracleClient.OracleType> di **Cursor** e un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> oggetto di **output**.</span><span class="sxs-lookup"><span data-stu-id="772f3-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="772f3-109">Il provider di dati supporta l'associazione dei REF CURSOR solo come parametri di output.</span><span class="sxs-lookup"><span data-stu-id="772f3-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="772f3-110">I REF CURSOR come parametri di input non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="772f3-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="772f3-111">Il recupero di un tipo <xref:System.Data.OracleClient.OracleDataReader> dal valore del parametro non è supportato.</span><span class="sxs-lookup"><span data-stu-id="772f3-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="772f3-112">I valori sono di tipo <xref:System.DBNull> dopo l'esecuzione del comando.</span><span class="sxs-lookup"><span data-stu-id="772f3-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="772f3-113">L'unico valore di enumerazione **CommandBehavior** che funziona con i REF CURSOR, ad esempio quando si <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>chiama, è **CloseConnection**. tutti gli altri vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="772f3-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="772f3-114">L'ordine dei CURSORi REF in **OracleDataReader** dipende dall'ordine dei parametri in **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="772f3-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="772f3-115">La proprietà <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="772f3-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="772f3-116">Il tipo di dati della **tabella** PL/SQL non è supportato.</span><span class="sxs-lookup"><span data-stu-id="772f3-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="772f3-117">I REF CURSOR, tuttavia, sono più efficaci.</span><span class="sxs-lookup"><span data-stu-id="772f3-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="772f3-118">Se è necessario utilizzare un tipo di dati **Table** , utilizzare il OLE DB .NET provider di dati con MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="772f3-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="772f3-119">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="772f3-119">In This Section</span></span>  
 [<span data-ttu-id="772f3-120">Esempi di REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="772f3-120">REF CURSOR Examples</span></span>](ref-cursor-examples.md)  
 <span data-ttu-id="772f3-121">Vengono presentati tre esempi che illustrano l'uso del tipo di dati REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="772f3-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="772f3-122">Parametri REF CURSOR in un oggetto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="772f3-122">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="772f3-123">Viene illustrato come eseguire un stored procedure PL/SQL che restituisce un parametro REF CURSOR e legge il valore come **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="772f3-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="772f3-124">Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="772f3-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="772f3-125">Viene illustrato come eseguire un stored procedure PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="772f3-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="772f3-126">Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="772f3-126">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="772f3-127">Viene illustrato come eseguire una stored procedure PL/SQL che restituisce due parametri REF CURSOR e la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.</span><span class="sxs-lookup"><span data-stu-id="772f3-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772f3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="772f3-128">See also</span></span>

- [<span data-ttu-id="772f3-129">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="772f3-129">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="772f3-130">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="772f3-130">ADO.NET Overview</span></span>](ado-net-overview.md)
