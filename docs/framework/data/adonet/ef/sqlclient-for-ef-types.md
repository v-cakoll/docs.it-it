---
title: SqlClient per tipi Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: d132583bba2520d37693be6c4b085cfa514003e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737841"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient per tipi Entity Framework
Il file manifesto del provider di dati .NET Framework per SQL Server (SqlClient) include l'elenco dei tipi primitivi del provider, facet per ogni tipo, mapping tra i tipi primitivi del modello concettuale e del modello di archiviazione e regole di promozione e conversione tra i tipi primitivi del modello concettuale e del modello di archiviazione.  
  
 Nella tabella seguente vengono descritti i tipi per i database SQL Server 2008, SQL Server 2005 e SQL Server 2000 e il modo in cui questi tipi vengono mappati ai tipi di modello concettuale. Alcuni nuovi tipi sono stati introdotti in versioni successive di SQL Server e non sono supportati nelle versioni precedente di SQL Server. Tali tipi sono segnalati nella tabella riportata di seguito.  
  
|Tipo di provider:<br /><br /> name|Tipo di provider:<br /><br /> attributi|`EDMSimpleType`<br /><br /> name|Facet|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|N/D|`Edm.Boolean`|N/D|  
|`tinyint`|N/D|`Edm.Byte`|N/D|  
|`smallint`|N/D|`Edm.Int16`|N/D|  
|`int`|N/D|`Edm.Int32`|N/D|  
|`bigint`|N/D|`Edm.Int64`|N/D|  
|`float`|N/D|`Edm.Double`|N/D|  
|`real`|N/D|`Edm.Double`|N/D|  
|`decimal`|N/D|`Edm.Decimal`|Precisione<br /><br /> -Minimo: 1<br /><br /> -Massimo: 38<br /><br /> -Valore predefinito: 18<br /><br /> -Constant: false<br /><br /> Scala<br /><br /> -Minimo: 0<br /><br /> -Massimo: 38<br /><br /> -Valore predefinito: 0<br /><br /> -Constant: false|  
|`numeric`|N/D|`Edm.Decimal`|Precisione<br /><br /> -Minimo: 1<br /><br /> -Massimo: 38<br /><br /> -Valore predefinito: 18<br /><br /> -Constant: false<br /><br /> Scala<br /><br /> -Minimo: 0<br /><br /> -Massimo: 38<br /><br /> -Valore predefinito: 0<br /><br /> -Constant: false|  
|`smallmoney`|N/D|`Edm.Decimal`|Precisione<br /><br /> -Valore predefinito: 10<br /><br /> -Constant: true<br /><br /> Scala<br /><br /> -Valore predefinito: 4<br /><br /> -Constant: true|  
|`money`|N/D|`Edm.Decimal`|Precisione<br /><br /> -Valore predefinito: 19<br /><br /> -Constant: true<br /><br /> Scala<br /><br /> -Valore predefinito: 4<br /><br /> -Constant: true|  
|`binary`|N/D|`Edm.Binary`|MaxLength<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Valore predefinito: 8000<br /><br /> -Constant: false<br /><br /> FixedLength<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true|  
|`varbinary`|N/D|`Edm.Binary`|MaxLength<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Valore predefinito: 8000<br /><br /> -Constant: false<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`varbinary(max)`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2000.|N/D|`Edm.Binary`|MaxLength<br /><br /> -Valore predefinito: 214748364780<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`image`|N/D|`Edm.Binary`|MaxLength<br /><br /> -Valore predefinito: 2147483647<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`timestamp`|N/D|`Edm.Binary`|MaxLength<br /><br /> -Valore predefinito: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true|  
|`rowversion`|N/D|`Edm.Binary`|MaxLength<br /><br /> -Valore predefinito: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true|  
|`smalldatetime`|N/D|`Edm.DateTime`|Precisione<br /><br /> -Valore predefinito: 0<br /><br /> -Constant: true|  
|`datetime`|N/D|`Edm.DateTime`|Precisione<br /><br /> -Valore predefinito: 3<br /><br /> -Constant: true|  
|`date`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.DateTime`|Precisione<br /><br /> -Valore predefinito: 0<br /><br /> -Constant: false|  
|`time`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.Time`|Precisione<br /><br /> -Valore predefinito: 7<br /><br /> -Constant: false|  
|`datetime2`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.DateTime`|Precisione<br /><br /> -Valore predefinito: 7<br /><br /> -Constant: false|  
|`datetimeoffset`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.DateTimeOffset`|Precisione<br /><br /> -Valore predefinito: 7<br /><br /> -Constant: false|  
|`nvarchar`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2000.|N/D|`Edm.String`|MaxLength<br /><br /> -Minimo: 1<br /><br /> -Massimo: 4000<br /><br /> -Valore predefinito: 4000<br /><br /> -Constant: false<br /><br /> Unicode:<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`varchar`<br /><br /> Nota: questo tipo non è supportato in SQL Server 2000.|N/D|`Edm.String`|MaxLength<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Valore predefinito: 8000<br /><br /> -Constant: false<br /><br /> Unicode:<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`char`|N/D|`Edm.String`|MaxLength<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Valore predefinito: 8000<br /><br /> -Constant: false<br /><br /> Unicode:<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true|  
|`nchar`|N/D|`Edm.String`|MaxLength<br /><br /> -Minimo: 1<br /><br /> -Massimo: 4000<br /><br /> -Valore predefinito: 4000<br /><br /> -Constant: false<br /><br /> Unicode:<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true|  
|`varchar`(`max`)|N/D|`Edm.String`|MaxLength<br /><br /> -Valore predefinito: 2147483647<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`nvarchar`(`max`)|N/D|`Edm.String`|MaxLength<br /><br /> -Valore predefinito: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`ntext`|Confrontabile uguale: false<br /><br /> Paragonabile all'ordine: false|`Edm.String`|MaxLength<br /><br /> -Valore predefinito: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`text`|Confrontabile uguale: false<br /><br /> Paragonabile all'ordine: false|`Edm.String`|MaxLength<br /><br /> -Valore predefinito: 2147483647<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
|`Unique`<br /><br /> `identifier`|Confrontabile uguale: true<br /><br /> Confronto tra ordini: true|`Edm.Guid`|N/D|  
|`xml`|Confrontabile uguale: false<br /><br /> Paragonabile all'ordine: false|`Edm.String`|MaxLength<br /><br /> -Valore predefinito: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valore predefinito: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valore predefinito: false<br /><br /> -Constant: true|  
  
## <a name="see-also"></a>Vedere anche

- [Specifiche CSDL, SSDL e MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
