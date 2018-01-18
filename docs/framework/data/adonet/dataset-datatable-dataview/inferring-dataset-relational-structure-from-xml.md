---
title: Deduzione della struttura relazionale di dataset da XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bae6e82eaf0f01847c304e094d98fe420e6f8b65
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Deduzione della struttura relazionale di dataset da XML
La struttura relazionale, o schema, di un tipo <xref:System.Data.DataSet> è costituita da tabelle, colonne, vincoli e relazioni. Quando si carica un tipo <xref:System.Data.DataSet> dall'XML, lo schema può essere predefinito oppure creato, implicitamente o tramite inferenza, dall'XML caricato. Per ulteriori informazioni sul caricamento di schema e il contenuto di un <xref:System.Data.DataSet> da XML, vedere [durante il caricamento di un set di dati da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) e [durante il caricamento di informazioni sullo Schema di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
 Se lo schema di un <xref:System.Data.DataSet> viene creata da XML, il metodo preferito consiste nel specificare in modo esplicito lo schema utilizzando entrambi il linguaggio XML Schema definition (XSD) (come descritto in [derivazione struttura relazionale di DataSet da XML Schema (XSD) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) o il XML-Data Reduced (XDR). Se nell'XML non è disponibile un XML Schema o uno schema XDR, è possibile inferire lo schema del tipo <xref:System.Data.DataSet> dalla struttura degli elementi e degli attributi XML.  
  
 Contenuto della sezione vengono descritte le regole relative all'inferenza dello schema del tipo <xref:System.Data.DataSet> mediante l'illustrazione degli elementi e degli attributi XML, delle relative strutture e dello schema inferito del tipo <xref:System.Data.DataSet> risultante.  
  
 Non è necessario includere in un processo di inferenza tutti gli attributi presenti in un documento XML. È possibile che negli attributi qualificati dallo spazio dei nomi siano inclusi metadati importanti per il documento XML ma non per lo schema del tipo <xref:System.Data.DataSet>. Il metodo <xref:System.Data.DataSet.InferXmlSchema%2A> consente di specificare degli spazi dei nomi da ignorare durante il processo di inferenza. Per ulteriori informazioni, vedere [durante il caricamento di informazioni sullo Schema di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Riepilogo del processo di inferenza dello schema DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 Viene fornito un riepilogo estremamente dettagliato delle regole per l'inferenza dello schema di un tipo <xref:System.Data.DataSet> dall'XML.  
  
 [Deduzione di tabelle](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 Vengono descritti gli elementi XML inferiti come tabelle in un tipo <xref:System.Data.DataSet>.  
  
 [Deduzione di colonne](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 Vengono descritti gli elementi e gli attributi XML inferiti come colonne di tabelle.  
  
 [Deduzione di relazioni](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 Vengono descritti gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> creati per le tabelle annidate inferite.  
  
 [Deduzione del testo dell'elemento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 Vengono descritte le colonne create per il testo negli elementi XML e vengono illustrati i casi in cui tale testo viene ignorato.  
  
 [Limitazioni all'inferenza](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 Vengono illustrate le limitazioni dell'inferenza dello schema.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Viene descritta l'interazione dell'oggetto <xref:System.Data.DataSet> con i dati XML.  
  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un tipo <xref:System.Data.DataSet> creato da uno schema XSD (XML Schema Definition Language).  
  
 [Panoramica di ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET, nonché il relativo uso per accedere alle origini dati esistenti e per gestire i dati dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
