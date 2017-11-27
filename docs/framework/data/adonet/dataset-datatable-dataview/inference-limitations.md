---
title: Limitazioni all'inferenza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98ea3d5fa4427b391ef06b3fc6ace9a05dfb819a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="inference-limitations"></a>Limitazioni all'inferenza
Il processo di inferenza di uno schema di un tipo <xref:System.Data.DataSet> da un documento XML può fornire come risultato diversi schemi a seconda degli elementi XML presenti in ogni documento. Si considerino ad esempio i seguenti documenti XML:  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Nel caso di "Document1", il processo di inferenza produce una **DataSet** denominato "DocumentElement" e una tabella denominata "Element1", poiché "Element1" è un elemento ripetuto.  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Tuttavia, per "Document2", il processo di inferenza produce una **DataSet** denominato "NewDataSet" e una tabella denominata "DocumentElement". "Element1" viene inferito come colonna in quanto privo di attributi o elementi figlio.  
  
 **Set di dati:** NewDataSet  
  
 **Tabella:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 È possibile che lo scopo di tali documenti XML fosse la creazione dello stesso schema, ma il processo di inferenza consente di produrre risultati molto diversi in base agli elementi contenuti in ogni documento.  
  
 Per evitare eventuali discrepanze nella generazione di schema da un documento XML, è consigliabile specificare in modo esplicito uno schema mediante il linguaggio XML Schema definition (XSD) o (XML-Data Reduced) durante il caricamento di un **DataSet** da XML. Per ulteriori informazioni su come specificare in modo esplicito un **DataSet** schema con uno Schema XML, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Inferenza della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Il caricamento delle informazioni dello Schema di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
