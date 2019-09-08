---
title: Dati binari e con valori elevati SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4d941ad6b7865112b45fd8c20ad89e9236e17b9d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791681"
---
# <a name="sql-server-binary-and-large-value-data"></a>Dati binari e con valori elevati SQL Server
In SQL Server è disponibile l'identificatore `max`, che espande la capacità di archiviazione dei tipi di dati `varchar`, `nvarchar` e `varbinary`. `varchar(max)`, `nvarchar(max)`e sono `varbinary(max)` chiamati collettivamente *tipi di dati con valori di grandi dimensioni*. È possibile usare i tipi di dati con valori di grandi dimensioni per archiviare fino a 2^31-1 byte di dati.  
  
 In SQL Server 2008 viene introdotto l'attributo FILESTREAM, che non è un tipo di dati ma piuttosto un attributo che può essere definito in una colonna, per consentire l'archiviazione dei dati con valori di grandi dimensioni nel file system anziché nel database.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Modifica di dati con valori elevati (massimi) in ADO.NET](modifying-large-value-max-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni.  
  
 [Dati FILESTREAM](filestream-data.md)  
 Viene descritto come usare tipi di dati con valori di grandi dimensioni archiviati in SQL Server 2008 con l'attributo FILESTREAM.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati SQL Server e ADO.NET](sql-server-data-types.md)
- [Operazioni sui dati SQL Server in ADO.NET](sql-server-data-operations.md)
- [Recupero e modifica di dati in ADO.NET](../retrieving-and-modifying-data.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
