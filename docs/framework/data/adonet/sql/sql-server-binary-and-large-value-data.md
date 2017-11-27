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
# <a name="sql-server-binary-and-large-value-data"></a>Dati binari e con valori elevati SQL Server
In SQL Server è disponibile l'identificatore `max`, che espande la capacità di archiviazione dei tipi di dati `varchar`, `nvarchar` e `varbinary`. `varchar(max)`, `nvarchar(max)`, e `varbinary(max)` collettivamente denominati *tipi di dati di valori di grandi dimensioni*. È possibile usare i tipi di dati con valori di grandi dimensioni per archiviare fino a 2^31-1 byte di dati.  
  
 In SQL Server 2008 viene introdotto l'attributo FILESTREAM, che non è un tipo di dati ma piuttosto un attributo che può essere definito in una colonna, per consentire l'archiviazione dei dati con valori di grandi dimensioni nel file system anziché nel database.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Modifica dei dati (max) di valori di grandi dimensioni in ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni.  
  
 [Dati FILESTREAM](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni archiviati in SQL Server 2008 con l'attributo FILESTREAM.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Operazioni sui dati SQL Server in ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
