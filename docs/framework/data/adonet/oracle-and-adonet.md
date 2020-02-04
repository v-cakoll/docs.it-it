---
title: Oracle e ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 5683f2b4ba57021ff6dda3a51baca016f886b605
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980080"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="34972-102">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34972-102">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="34972-103">I tipi in <xref:System.Data.OracleClient> sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="34972-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="34972-104">I tipi restano supportati nella versione corrente di .NET Framework, ma saranno rimossi in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="34972-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="34972-105">Microsoft consiglia di usare un provider Oracle di terze parti.</span><span class="sxs-lookup"><span data-stu-id="34972-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="34972-106">In questa sezione vengono descritte le caratteristiche e i comportamenti specifici del provider di dati .NET Framework per Oracle.</span><span class="sxs-lookup"><span data-stu-id="34972-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="34972-107">Il .NET Framework provider di dati per Oracle consente di accedere a un database Oracle utilizzando l'interfaccia OCI (Oracle Call Interface) fornita dal software client Oracle.</span><span class="sxs-lookup"><span data-stu-id="34972-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="34972-108">La funzionalità del provider di dati è progettata per essere simile a quella dei provider di dati .NET Framework per SQL Server, OLE DB e ODBC.</span><span class="sxs-lookup"><span data-stu-id="34972-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="34972-109">Per usare il provider di dati .NET Framework per Oracle, un'applicazione deve fare riferimento allo spazio dei nomi <xref:System.Data.OracleClient> come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="34972-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="34972-110">Quando si compila il codice, inoltre, è necessario includere un riferimento alla DLL.</span><span class="sxs-lookup"><span data-stu-id="34972-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="34972-111">Ad esempio, se si compila un programma C#, la riga di comando deve includere:</span><span class="sxs-lookup"><span data-stu-id="34972-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="34972-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="34972-112">In This Section</span></span>  
 [<span data-ttu-id="34972-113">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="34972-113">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="34972-114">Vengono descritti i requisiti per l'utilizzo di .NET Framework provider di dati per Oracle e vengono descritti alcuni problemi che è necessario tenere presente quando si utilizza.</span><span class="sxs-lookup"><span data-stu-id="34972-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="34972-115">Oggetti BFILE Oracle</span><span class="sxs-lookup"><span data-stu-id="34972-115">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="34972-116">Viene descritta la classe <xref:System.Data.OracleClient.OracleBFile> usata per il tipo di dati BFILE Oracle.</span><span class="sxs-lookup"><span data-stu-id="34972-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="34972-117">Oggetti LOB Oracle</span><span class="sxs-lookup"><span data-stu-id="34972-117">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="34972-118">Viene descritta la classe <xref:System.Data.OracleClient.OracleLob> usata per il tipo di dati LOB Oracle.</span><span class="sxs-lookup"><span data-stu-id="34972-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="34972-119">Oggetti REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="34972-119">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="34972-120">Viene descritto il supporto del tipo di dati REF CURSOR Oracle.</span><span class="sxs-lookup"><span data-stu-id="34972-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="34972-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="34972-121">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="34972-122">Vengono descritte le strutture utilizzabili con i tipi di dati Oracle, inclusi tipi <xref:System.Data.OracleClient.OracleNumber> e <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="34972-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="34972-123">Sequenze Oracle</span><span class="sxs-lookup"><span data-stu-id="34972-123">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="34972-124">Viene descritto il supporto per il recupero dei valori chiave di sequenze di Oracle generati dal server.</span><span class="sxs-lookup"><span data-stu-id="34972-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="34972-125">Mapping dei tipi di dati Oracle</span><span class="sxs-lookup"><span data-stu-id="34972-125">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="34972-126">Vengono presentati i tipi di dati Oracle e i relativi mapping alla classe <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="34972-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="34972-127">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="34972-127">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="34972-128">Viene descritto come l'oggetto <xref:System.Data.OracleClient.OracleConnection>, in presenza di una transazione attiva, esegue l'inserimento automatico nella transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="34972-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="34972-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="34972-129">Related Sections</span></span>  
 [<span data-ttu-id="34972-130">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34972-130">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="34972-131">Vengono descritte le tecniche che consentono di scrivere codice sicuro quando si usa ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="34972-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="34972-132">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="34972-132">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="34972-133">Viene descritto come creare e usare `DataSets`, `DataSets` tipizzati, `DataTables` e `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="34972-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="34972-134">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34972-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="34972-135">Viene descritto come usare i dati in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="34972-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="34972-136">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34972-136">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="34972-137">Viene descritto come usare le funzionalità e le caratteristiche specifiche di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34972-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="34972-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="34972-138">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="34972-139">Vengono descritte le classi generiche che consentono di scrivere codice indipendente dal provider in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="34972-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34972-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34972-140">See also</span></span>

- [<span data-ttu-id="34972-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34972-141">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="34972-142">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34972-142">ADO.NET Overview</span></span>](ado-net-overview.md)
