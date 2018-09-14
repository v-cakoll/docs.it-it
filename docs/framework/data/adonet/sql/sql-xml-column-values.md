---
title: Valori di colonna SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: b46c763e7cddfc7617c9a6a23428f83a54955ba0
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45516324"
---
# <a name="sql-xml-column-values"></a>Valori di colonna SQL XML
SQL Server supporta il `xml` tipo di dati, gli sviluppatori possono recuperare set di risultati includono questo tipo usando il comportamento standard del <xref:System.Data.SqlClient.SqlCommand> classe. È possibile recuperare una colonna `xml` come qualunque altra colonna (ad esempio, in un tipo <xref:System.Data.SqlClient.SqlDataReader>) ma se si desidera lavorare con il contenuto della colonna in formato XML, è necessario usare un tipo <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Esempio  
 L'applicazione console seguente seleziona due righe, ognuna delle quali contiene un `xml` colonna, dal **Demographics** nella tabella il **AdventureWorks** database un <xref:System.Data.SqlClient.SqlDataReader> istanza. Il valore della colonna `xml` per ciascuna riga viene letto usando il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> del tipo <xref:System.Data.SqlClient.SqlDataReader>. Il valore viene archiviato in un tipo <xref:System.Xml.XmlReader>. Notare che è necessario usare il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> invece del metodo <xref:System.Data.IDataRecord.GetValue%2A>, se si desidera impostare il contenuto su una variabile <xref:System.Data.SqlTypes.SqlXml>. Il metodo <xref:System.Data.IDataRecord.GetValue%2A> restituisce il valore della colonna `xml` sotto forma di stringa.  
  
> [!NOTE]
>  Il **AdventureWorks** database di esempio non è installato per impostazione predefinita quando si installa SQL Server. Per installarlo, è sufficiente eseguire il programma di installazione di SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.SqlTypes.SqlXml>  
 [Dati XML in SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
