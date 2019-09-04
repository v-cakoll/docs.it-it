---
title: SqlClient per tipi Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: af3a4eea08dd3f4e1a134fcb66d92bc4a3b077c7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248373"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient per tipi Entity Framework
Il file manifesto del provider di dati .NET Framework per SQL Server (SqlClient) include l'elenco dei tipi primitivi del provider, facet per ogni tipo, mapping tra i tipi primitivi del modello concettuale e del modello di archiviazione e regole di promozione e conversione tra i tipi primitivi del modello concettuale e del modello di archiviazione.  
  
 Nella tabella seguente vengono descritti i tipi per i database SQL Server 2008, SQL Server 2005 e SQL Server 2000 e il modo in cui questi tipi vengono mappati ai tipi di modello concettuale. Alcuni nuovi tipi sono stati introdotti in versioni successive di SQL Server e non sono supportati nelle versioni precedente di SQL Server. Tali tipi sono segnalati nella tabella riportata di seguito.  
  
|Tipo di provider:<br /><br /> name|Tipo di provider:<br /><br /> attributi|`EDMSimpleType`<br /><br /> name|Facet|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|n/d|`Edm.Boolean`|n/d|  
|`tinyint`|n/d|`Edm.Byte`|n/d|  
|`smallint`|n/d|`Edm.Int16`|n/d|  
|`int`|n/d|`Edm.Int32`|n/d|  
|`bigint`|n/d|`Edm.Int64`|n/d|  
|`float`|n/d|`Edm.Double`|n/d|  
|`real`|n/d|`Edm.Double`|n/d|  
|`decimal`|n/d|`Edm.Decimal`|Precisione<br /><br /> Minimo 1<br /><br /> Massimo 38<br /><br /> Predefinita 18<br /><br /> Costante False<br /><br /> Scala<br /><br /> Minimo 0<br /><br /> Massimo 38<br /><br /> Predefinita 0<br /><br /> Costante False|  
|`numeric`|n/d|`Edm.Decimal`|Precisione<br /><br /> Minimo 1<br /><br /> Massimo 38<br /><br /> Predefinita 18<br /><br /> Costante False<br /><br /> Scala<br /><br /> Minimo 0<br /><br /> Massimo 38<br /><br /> Predefinita 0<br /><br /> Costante False|  
|`smallmoney`|n/d|`Edm.Decimal`|Precisione<br /><br /> Predefinita 10<br /><br /> Costante True<br /><br /> Scala<br /><br /> Predefinita 4<br /><br /> Costante True|  
|`money`|n/d|`Edm.Decimal`|Precisione<br /><br /> Predefinita 19<br /><br /> Costante True<br /><br /> Scala<br /><br /> Predefinita 4<br /><br /> Costante True|  
|`binary`|n/d|`Edm.Binary`|MaxLength<br /><br /> Minimo 1<br /><br /> Massimo 8000<br /><br /> Predefinita 8000<br /><br /> Costante False<br /><br /> FixedLength<br /><br /> Predefinita True<br /><br /> Costante True|  
|`varbinary`|n/d|`Edm.Binary`|MaxLength<br /><br /> Minimo 1<br /><br /> Massimo 8000<br /><br /> Predefinita 8000<br /><br /> Costante False<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`varbinary(max)`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2000.|n/d|`Edm.Binary`|MaxLength<br /><br /> Predefinita 214748364780<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`image`|n/d|`Edm.Binary`|MaxLength<br /><br /> Predefinita 2147483647<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`timestamp`|n/d|`Edm.Binary`|MaxLength<br /><br /> Predefinita 8<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita True<br /><br /> Costante True|  
|`rowversion`|n/d|`Edm.Binary`|MaxLength<br /><br /> Predefinita 8<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita True<br /><br /> Costante True|  
|`smalldatetime`|n/d|`Edm.DateTime`|Precisione<br /><br /> Predefinita 0<br /><br /> Costante True|  
|`datetime`|n/d|`Edm.DateTime`|Precisione<br /><br /> Predefinita 3<br /><br /> Costante True|  
|`date`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|n/d|`Edm.DateTime`|Precisione<br /><br /> Predefinita 0<br /><br /> Costante False|  
|`time`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|n/d|`Edm.Time`|Precisione<br /><br /> Predefinita 7<br /><br /> Costante False|  
|`datetime2`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|n/d|`Edm.DateTime`|Precisione<br /><br /> Predefinita 7<br /><br /> Costante False|  
|`datetimeoffset`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|n/d|`Edm.DateTimeOffset`|Precisione<br /><br /> Predefinita 7<br /><br /> Costante False|  
|`nvarchar`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2000.|n/d|`Edm.String`|MaxLength<br /><br /> Minimo 1<br /><br /> Massimo 4000<br /><br /> Predefinita 4000<br /><br /> Costante False<br /><br /> Unicode:<br /><br /> Predefinita True<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`varchar`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2000.|n/d|`Edm.String`|MaxLength<br /><br /> Minimo 1<br /><br /> Massimo 8000<br /><br /> Predefinita 8000<br /><br /> Costante False<br /><br /> Unicode:<br /><br /> Predefinita False<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`char`|n/d|`Edm.String`|MaxLength<br /><br /> Minimo 1<br /><br /> Massimo 8000<br /><br /> Predefinita 8000<br /><br /> Costante False<br /><br /> Unicode:<br /><br /> Predefinita False<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita True<br /><br /> Costante True|  
|`nchar`|n/d|`Edm.String`|MaxLength<br /><br /> Minimo 1<br /><br /> Massimo 4000<br /><br /> Predefinita 4000<br /><br /> Costante False<br /><br /> Unicode:<br /><br /> Predefinita True<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita True<br /><br /> Costante True|  
|`varchar`(`max`)|n/d|`Edm.String`|MaxLength<br /><br /> Predefinita 2147483647<br /><br /> Costante True<br /><br /> Unicode:<br /><br /> Predefinita False<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`nvarchar`(`max`)|n/d|`Edm.String`|MaxLength<br /><br /> Predefinita 1073741823<br /><br /> Costante True<br /><br /> Unicode:<br /><br /> Predefinita True<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`ntext`|Confrontabile uguale: False<br /><br /> Confronto tra ordini: False|`Edm.String`|MaxLength<br /><br /> Predefinita 1073741823<br /><br /> Costante True<br /><br /> Unicode:<br /><br /> Predefinita False<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`text`|Confrontabile uguale: False<br /><br /> Confronto tra ordini: False|`Edm.String`|MaxLength<br /><br /> Predefinita 2147483647<br /><br /> Costante True<br /><br /> Unicode:<br /><br /> Predefinita False<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
|`Unique`<br /><br /> `identifier`|Confrontabile uguale: True<br /><br /> Confronto tra ordini: True|`Edm.Guid`|n/d|  
|`xml`|Confrontabile uguale: False<br /><br /> Confronto tra ordini: False|`Edm.String`|MaxLength<br /><br /> Predefinita 1073741823<br /><br /> Costante True<br /><br /> Unicode:<br /><br /> Predefinita True<br /><br /> Costante True<br /><br /> FixedLength<br /><br /> Predefinita False<br /><br /> Costante True|  
  
## <a name="see-also"></a>Vedere anche

- [Specifiche CSDL, SSDL e MSL](./language-reference/csdl-ssdl-and-msl-specifications.md)
