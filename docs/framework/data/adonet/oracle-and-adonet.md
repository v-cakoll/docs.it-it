---
title: Oracle e ADO.NET
description: Informazioni sulle funzionalità e sui comportamenti della provider di dati .NET Framework per Oracle, che consente di accedere a un database Oracle tramite l'interfaccia di chiamata Oracle.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 8757352a7444fad802ea88ba58e0fe643c86cbb8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286689"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="00197-103">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00197-103">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="00197-104">I tipi in <xref:System.Data.OracleClient> sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="00197-104">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="00197-105">I tipi restano supportati nella versione corrente di .NET Framework, ma saranno rimossi in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="00197-105">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="00197-106">Microsoft consiglia di usare un provider Oracle di terze parti.</span><span class="sxs-lookup"><span data-stu-id="00197-106">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="00197-107">In questa sezione vengono descritte le caratteristiche e i comportamenti specifici del provider di dati .NET Framework per Oracle.</span><span class="sxs-lookup"><span data-stu-id="00197-107">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="00197-108">Il .NET Framework provider di dati per Oracle consente di accedere a un database Oracle utilizzando l'interfaccia OCI (Oracle Call Interface) fornita dal software client Oracle.</span><span class="sxs-lookup"><span data-stu-id="00197-108">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="00197-109">La funzionalità del provider di dati è progettata per essere simile a quella dei provider di dati .NET Framework per SQL Server, OLE DB e ODBC.</span><span class="sxs-lookup"><span data-stu-id="00197-109">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="00197-110">Per utilizzare la .NET Framework provider di dati per Oracle, un'applicazione deve fare riferimento allo <xref:System.Data.OracleClient> spazio dei nomi come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="00197-110">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="00197-111">Quando si compila il codice, inoltre, è necessario includere un riferimento alla DLL.</span><span class="sxs-lookup"><span data-stu-id="00197-111">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="00197-112">Ad esempio, se si compila un programma C#, la riga di comando deve includere:</span><span class="sxs-lookup"><span data-stu-id="00197-112">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="00197-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="00197-113">In This Section</span></span>  
 [<span data-ttu-id="00197-114">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="00197-114">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="00197-115">Vengono descritti i requisiti per l'utilizzo di .NET Framework provider di dati per Oracle e vengono descritti alcuni problemi che è necessario tenere presente quando si utilizza.</span><span class="sxs-lookup"><span data-stu-id="00197-115">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="00197-116">Oggetti BFILE Oracle</span><span class="sxs-lookup"><span data-stu-id="00197-116">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="00197-117">Viene descritta la classe <xref:System.Data.OracleClient.OracleBFile> usata per il tipo di dati BFILE Oracle.</span><span class="sxs-lookup"><span data-stu-id="00197-117">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="00197-118">Oggetti LOB Oracle</span><span class="sxs-lookup"><span data-stu-id="00197-118">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="00197-119">Viene descritta la classe <xref:System.Data.OracleClient.OracleLob> usata per il tipo di dati LOB Oracle.</span><span class="sxs-lookup"><span data-stu-id="00197-119">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="00197-120">Oggetti REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="00197-120">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="00197-121">Viene descritto il supporto del tipo di dati REF CURSOR Oracle.</span><span class="sxs-lookup"><span data-stu-id="00197-121">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="00197-122">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="00197-122">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="00197-123">Vengono descritte le strutture utilizzabili con i tipi di dati Oracle, inclusi tipi <xref:System.Data.OracleClient.OracleNumber> e <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="00197-123">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="00197-124">Sequenze Oracle</span><span class="sxs-lookup"><span data-stu-id="00197-124">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="00197-125">Viene descritto il supporto per il recupero dei valori chiave di sequenze di Oracle generati dal server.</span><span class="sxs-lookup"><span data-stu-id="00197-125">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="00197-126">Mapping dei tipi di dati Oracle</span><span class="sxs-lookup"><span data-stu-id="00197-126">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="00197-127">Vengono presentati i tipi di dati Oracle e i relativi mapping alla classe <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="00197-127">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="00197-128">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="00197-128">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="00197-129">Viene descritto come l'oggetto <xref:System.Data.OracleClient.OracleConnection>, in presenza di una transazione attiva, esegue l'inserimento automatico nella transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="00197-129">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="00197-130">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="00197-130">Related Sections</span></span>  
 [<span data-ttu-id="00197-131">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00197-131">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="00197-132">Vengono descritte le tecniche che consentono di scrivere codice sicuro quando si usa ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="00197-132">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="00197-133">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="00197-133">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="00197-134">Viene descritto come creare e usare `DataSets`, `DataSets` tipizzati, `DataTables` e `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="00197-134">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="00197-135">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00197-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="00197-136">Viene descritto come usare i dati in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="00197-136">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="00197-137">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00197-137">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="00197-138">Viene descritto come usare le funzionalità e le caratteristiche specifiche di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00197-138">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="00197-139">Oggetti DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="00197-139">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="00197-140">Vengono descritte le classi generiche che consentono di scrivere codice indipendente dal provider in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="00197-140">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00197-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00197-141">See also</span></span>

- [<span data-ttu-id="00197-142">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00197-142">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="00197-143">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00197-143">ADO.NET Overview</span></span>](ado-net-overview.md)
