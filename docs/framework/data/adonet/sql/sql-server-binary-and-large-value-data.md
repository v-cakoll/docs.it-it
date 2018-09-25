---
title: Dati binari e con valori elevati SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 9ebbe23dfbcac7825ce449dd40f62b921d13ab4a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078175"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="a63e8-102">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="a63e8-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="a63e8-103">In SQL Server è disponibile l'identificatore `max`, che espande la capacità di archiviazione dei tipi di dati `varchar`, `nvarchar` e `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="a63e8-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="a63e8-104">`varchar(max)`, `nvarchar(max)`, e `varbinary(max)` collettivamente vengono chiamati *tipi di dati di valori di grandi dimensioni*.</span><span class="sxs-lookup"><span data-stu-id="a63e8-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="a63e8-105">È possibile usare i tipi di dati con valori di grandi dimensioni per archiviare fino a 2^31-1 byte di dati.</span><span class="sxs-lookup"><span data-stu-id="a63e8-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="a63e8-106">In SQL Server 2008 viene introdotto l'attributo FILESTREAM, che non è un tipo di dati ma piuttosto un attributo che può essere definito in una colonna, per consentire l'archiviazione dei dati con valori di grandi dimensioni nel file system anziché nel database.</span><span class="sxs-lookup"><span data-stu-id="a63e8-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a63e8-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a63e8-107">In This Section</span></span>  
 [<span data-ttu-id="a63e8-108">Modifica di dati con valori elevati (massimi) in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a63e8-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="a63e8-109">Viene descritto come usare tipi di dati con valori di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a63e8-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="a63e8-110">Dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a63e8-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="a63e8-111">Viene descritto come usare tipi di dati con valori di grandi dimensioni archiviati in SQL Server 2008 con l'attributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a63e8-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63e8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a63e8-112">See Also</span></span>  
 [<span data-ttu-id="a63e8-113">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a63e8-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="a63e8-114">Operazioni sui dati SQL Server in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a63e8-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="a63e8-115">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a63e8-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="a63e8-116">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a63e8-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
