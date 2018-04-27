---
title: Oracle e ADO.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 40b81df158dbad0247df76124201decae41e3267
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="c93ad-102">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c93ad-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="c93ad-103">I tipi in <xref:System.Data.OracleClient> sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="c93ad-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="c93ad-104">I tipi restano supportati nella versione corrente di .NET Framework, ma saranno rimossi in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="c93ad-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="c93ad-105">Microsoft consiglia di usare un provider Oracle di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c93ad-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="c93ad-106">Contenuto della sezione vengono descritte le caratteristiche e i comportamenti specifici del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle.</span><span class="sxs-lookup"><span data-stu-id="c93ad-106">This section describes features and behaviors that are specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="c93ad-107">Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle fornisce l'accesso a un database Oracle mediante l'interfaccia OCI (Oracle Call Interface) del software client Oracle.</span><span class="sxs-lookup"><span data-stu-id="c93ad-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="c93ad-108">La funzionalità del provider di dati è progettata per essere simile a quello del [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provider di dati per SQL Server, OLE DB e ODBC.</span><span class="sxs-lookup"><span data-stu-id="c93ad-108">The functionality of the data provider is designed to be similar to that of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="c93ad-109">Per usare il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle, è necessario che l'applicazione faccia riferimento allo spazio dei nomi <xref:System.Data.OracleClient> come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c93ad-109">To use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="c93ad-110">Quando si compila il codice, inoltre, è necessario includere un riferimento alla DLL.</span><span class="sxs-lookup"><span data-stu-id="c93ad-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="c93ad-111">Ad esempio, se si compila un programma C#, la riga di comando deve includere:</span><span class="sxs-lookup"><span data-stu-id="c93ad-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="c93ad-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c93ad-112">In This Section</span></span>  
 [<span data-ttu-id="c93ad-113">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="c93ad-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="c93ad-114">Vengono descritti i requisiti e i problemi relativi all'utilizzo del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle.</span><span class="sxs-lookup"><span data-stu-id="c93ad-114">Describes requirements for using the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="c93ad-115">Oggetti BFILE Oracle</span><span class="sxs-lookup"><span data-stu-id="c93ad-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="c93ad-116">Viene descritta la classe <xref:System.Data.OracleClient.OracleBFile> usata per il tipo di dati BFILE Oracle.</span><span class="sxs-lookup"><span data-stu-id="c93ad-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="c93ad-117">Oggetti LOB Oracle</span><span class="sxs-lookup"><span data-stu-id="c93ad-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="c93ad-118">Viene descritta la classe <xref:System.Data.OracleClient.OracleLob> usata per il tipo di dati LOB Oracle.</span><span class="sxs-lookup"><span data-stu-id="c93ad-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="c93ad-119">Oggetti REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="c93ad-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="c93ad-120">Viene descritto il supporto del tipo di dati REF CURSOR Oracle.</span><span class="sxs-lookup"><span data-stu-id="c93ad-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="c93ad-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="c93ad-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="c93ad-122">Vengono descritte le strutture utilizzabili con i tipi di dati Oracle, inclusi tipi <xref:System.Data.OracleClient.OracleNumber> e <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="c93ad-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="c93ad-123">Sequenze Oracle</span><span class="sxs-lookup"><span data-stu-id="c93ad-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="c93ad-124">Viene descritto il supporto per il recupero dei valori chiave di sequenze di Oracle generati dal server.</span><span class="sxs-lookup"><span data-stu-id="c93ad-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="c93ad-125">Mapping dei tipi di dati Oracle</span><span class="sxs-lookup"><span data-stu-id="c93ad-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="c93ad-126">Vengono presentati i tipi di dati Oracle e i relativi mapping alla classe <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="c93ad-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="c93ad-127">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="c93ad-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="c93ad-128">Viene descritto come l'oggetto <xref:System.Data.OracleClient.OracleConnection>, in presenza di una transazione attiva, esegue l'inserimento automatico nella transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="c93ad-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c93ad-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c93ad-129">Related Sections</span></span>  
 [<span data-ttu-id="c93ad-130">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c93ad-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="c93ad-131">Vengono descritte le tecniche che consentono di scrivere codice protetto quando si usa [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c93ad-131">Describes secure coding practices when using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="c93ad-132">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="c93ad-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="c93ad-133">Viene descritto come creare e usare `DataSets`, `DataSets` tipizzati, `DataTables` e `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="c93ad-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="c93ad-134">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c93ad-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="c93ad-135">Viene descritto come usare i dati in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c93ad-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="c93ad-136">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c93ad-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="c93ad-137">Viene descritto come usare le funzionalità specifiche di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c93ad-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="c93ad-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="c93ad-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="c93ad-139">Vengono descritte le classi generiche che consentono di scrivere codice indipendente dal provider in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c93ad-139">Describes generic classes that allow you to write provider-independent code in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93ad-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c93ad-140">See Also</span></span>  
 [<span data-ttu-id="c93ad-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c93ad-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="c93ad-142">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c93ad-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
