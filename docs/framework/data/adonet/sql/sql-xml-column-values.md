---
title: Valori di colonna SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 29e9ac5b95b62ef2a4467bf41484c3740d550abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964954"
---
# <a name="sql-xml-column-values"></a>Valori di colonna SQL XML
SQL Server supporta il `xml` tipo di dati e gli sviluppatori possono recuperare set di risultati che includono questo tipo utilizzando il <xref:System.Data.SqlClient.SqlCommand> comportamento standard della classe. È possibile recuperare una colonna `xml` come qualunque altra colonna (ad esempio, in un tipo <xref:System.Data.SqlClient.SqlDataReader>) ma se si desidera lavorare con il contenuto della colonna in formato XML, è necessario usare un tipo <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Esempio  
 Nell'applicazione console seguente vengono selezionate due righe, ciascuna contenente `xml` una colonna, dalla tabella **Sales. Store** del database **AdventureWorks** a un' <xref:System.Data.SqlClient.SqlDataReader> istanza di. Il valore della colonna `xml` per ciascuna riga viene letto usando il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> del tipo <xref:System.Data.SqlClient.SqlDataReader>. Il valore viene archiviato in un tipo <xref:System.Xml.XmlReader>. Notare che è necessario usare il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> invece del metodo <xref:System.Data.IDataRecord.GetValue%2A>, se si desidera impostare il contenuto su una variabile <xref:System.Data.SqlTypes.SqlXml>. Il metodo <xref:System.Data.IDataRecord.GetValue%2A> restituisce il valore della colonna `xml` sotto forma di stringa.  
  
> [!NOTE]
> Il database di esempio **AdventureWorks** non viene installato per impostazione predefinita quando si installa SQL Server. Per installarlo, è sufficiente eseguire il programma di installazione di SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.SqlTypes.SqlXml>
- [Dati XML in SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
