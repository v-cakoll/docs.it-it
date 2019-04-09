---
title: Dati binari e con valori elevati SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4b7a3f16726d6363cd702fb912bb7be281a25000
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192966"
---
# <a name="sql-server-binary-and-large-value-data"></a>Dati binari e con valori elevati SQL Server
In SQL Server è disponibile l'identificatore `max`, che espande la capacità di archiviazione dei tipi di dati `varchar`, `nvarchar` e `varbinary`. `varchar(max)`, `nvarchar(max)`, e `varbinary(max)` collettivamente vengono chiamati *tipi di dati di valori di grandi dimensioni*. È possibile usare i tipi di dati con valori di grandi dimensioni per archiviare fino a 2^31-1 byte di dati.  
  
 In SQL Server 2008 viene introdotto l'attributo FILESTREAM, che non è un tipo di dati ma piuttosto un attributo che può essere definito in una colonna, per consentire l'archiviazione dei dati con valori di grandi dimensioni nel file system anziché nel database.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Modifica di dati con valori elevati (massimi) in ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni.  
  
 [Dati FILESTREAM](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni archiviati in SQL Server 2008 con l'attributo FILESTREAM.  
  
## <a name="see-also"></a>Vedere anche

- [Mapping dei tipi di dati SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Operazioni sui dati SQL Server in ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)
- [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
