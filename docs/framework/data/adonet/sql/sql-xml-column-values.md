---
title: Valori di colonna SQL XML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c4eecbe66df3224e6dc3f118be474f25712afe8a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="411f2-102">Valori di colonna SQL XML</span><span class="sxs-lookup"><span data-stu-id="411f2-102">SQL XML Column Values</span></span>
<span data-ttu-id="411f2-103">SQL Server supporta il `xml` tipo di dati, gli sviluppatori possono recuperare set di risultati includono questo tipo usando il comportamento standard del <xref:System.Data.SqlClient.SqlCommand> classe.</span><span class="sxs-lookup"><span data-stu-id="411f2-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="411f2-104">È possibile recuperare una colonna `xml` come qualunque altra colonna (ad esempio, in un tipo <xref:System.Data.SqlClient.SqlDataReader>) ma se si desidera lavorare con il contenuto della colonna in formato XML, è necessario usare un tipo <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="411f2-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="411f2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="411f2-105">Example</span></span>  
 <span data-ttu-id="411f2-106">L'applicazione console seguente seleziona due righe, ognuna delle quali contiene un `xml` colonna, dal **Demographics** tabella il **AdventureWorks** database a un <xref:System.Data.SqlClient.SqlDataReader> istanza.</span><span class="sxs-lookup"><span data-stu-id="411f2-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="411f2-107">Il valore della colonna `xml` per ciascuna riga viene letto usando il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> del tipo <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="411f2-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="411f2-108">Il valore viene archiviato in un tipo <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="411f2-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="411f2-109">Notare che è necessario usare il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> invece del metodo <xref:System.Data.IDataRecord.GetValue%2A>, se si desidera impostare il contenuto su una variabile <xref:System.Data.SqlTypes.SqlXml>. Il metodo <xref:System.Data.IDataRecord.GetValue%2A> restituisce il valore della colonna `xml` sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="411f2-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="411f2-110">Il **AdventureWorks** database di esempio non è installato per impostazione predefinita quando si installa SQL Server.</span><span class="sxs-lookup"><span data-stu-id="411f2-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="411f2-111">Per installarlo, è sufficiente eseguire il programma di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="411f2-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="411f2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="411f2-112">See Also</span></span>  
 <xref:System.Data.SqlTypes.SqlXml>  
 [<span data-ttu-id="411f2-113">Dati XML in SQL Server</span><span class="sxs-lookup"><span data-stu-id="411f2-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [<span data-ttu-id="411f2-114">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="411f2-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
