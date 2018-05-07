---
title: Dati binari e con valori elevati SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: c0202f6dc17d36fafb28206e17b71fc6d68d88c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="sql-server-binary-and-large-value-data"></a>Dati binari e con valori elevati SQL Server
In SQL Server è disponibile l'identificatore `max`, che espande la capacità di archiviazione dei tipi di dati `varchar`, `nvarchar` e `varbinary`. `varchar(max)`, `nvarchar(max)`, e `varbinary(max)` collettivamente denominati *tipi di dati di valori di grandi dimensioni*. È possibile usare i tipi di dati con valori di grandi dimensioni per archiviare fino a 2^31-1 byte di dati.  
  
 In SQL Server 2008 viene introdotto l'attributo FILESTREAM, che non è un tipo di dati ma piuttosto un attributo che può essere definito in una colonna, per consentire l'archiviazione dei dati con valori di grandi dimensioni nel file system anziché nel database.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Modifica di dati con valori elevati (massimi) in ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni.  
  
 [Dati FILESTREAM](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni archiviati in SQL Server 2008 con l'attributo FILESTREAM.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Operazioni sui dati SQL Server in ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
