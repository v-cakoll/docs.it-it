---
title: Limitazioni all'inferenza
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 10347abc5b01edb4ec6fbf97221d44f4bfb88f54
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784586"
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
  
 Per "Document1", il processo di inferenza produce un **set di dati** denominato "DocumentElement" e una tabella denominata "Element1", perché "Element1" è un elemento ripetuto.  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Tuttavia, per "Document2", il processo di inferenza produce un **set di dati** denominato "NewDataSet" e una tabella denominata "DocumentElement". "Element1" viene inferito come colonna in quanto privo di attributi o elementi figlio.  
  
 **DataSet** NewDataSet  
  
 **tavolo:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 È possibile che lo scopo di tali documenti XML fosse la creazione dello stesso schema, ma il processo di inferenza consente di produrre risultati molto diversi in base agli elementi contenuti in ogni documento.  
  
 Per evitare le discrepanze che possono verificarsi durante la generazione dello schema da un documento XML, è consigliabile specificare in modo esplicito uno schema utilizzando il linguaggio XSD (XML Schema Definition Language) o XDR (XML-Data Reduced) durante il caricamento di un **DataSet** da XML. Per ulteriori informazioni su come specificare in modo esplicito uno schema del **set di dati** con XML Schema, vedere [derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
