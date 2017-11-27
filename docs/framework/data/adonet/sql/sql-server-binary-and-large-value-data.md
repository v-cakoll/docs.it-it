---
title: Dati binari e con valori elevati SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9065f467cd353c17471db2c0d67001a188459819
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="55a51-102">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="55a51-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="55a51-103">In SQL Server è disponibile l'identificatore `max`, che espande la capacità di archiviazione dei tipi di dati `varchar`, `nvarchar` e `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="55a51-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="55a51-104">`varchar(max)`, `nvarchar(max)`, e `varbinary(max)` collettivamente denominati *tipi di dati di valori di grandi dimensioni*.</span><span class="sxs-lookup"><span data-stu-id="55a51-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="55a51-105">È possibile usare i tipi di dati con valori di grandi dimensioni per archiviare fino a 2^31-1 byte di dati.</span><span class="sxs-lookup"><span data-stu-id="55a51-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="55a51-106">In SQL Server 2008 viene introdotto l'attributo FILESTREAM, che non è un tipo di dati ma piuttosto un attributo che può essere definito in una colonna, per consentire l'archiviazione dei dati con valori di grandi dimensioni nel file system anziché nel database.</span><span class="sxs-lookup"><span data-stu-id="55a51-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55a51-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="55a51-107">In This Section</span></span>  
 [<span data-ttu-id="55a51-108">Modifica dei dati (max) di valori di grandi dimensioni in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55a51-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="55a51-109">Viene descritto come usare tipi di dati con valori di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="55a51-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="55a51-110">Dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="55a51-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="55a51-111">Viene descritto come usare tipi di dati con valori di grandi dimensioni archiviati in SQL Server 2008 con l'attributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="55a51-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a51-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55a51-112">See Also</span></span>  
 [<span data-ttu-id="55a51-113">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55a51-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="55a51-114">Operazioni sui dati SQL Server in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55a51-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="55a51-115">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55a51-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="55a51-116">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="55a51-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
