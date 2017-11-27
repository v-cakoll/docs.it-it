---
title: Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9ac8e64c02d96450d41233cfbe65e1db839df9e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
Lo schema XSD (XML Schema Definition Language) consente di specificare vincoli sugli elementi e sugli attributi in esso definiti. Durante il mapping di uno Schema XML a uno schema relazionale in un <xref:System.Data.DataSet>, vincoli di XML Schema vengono mappati ai vincoli relazionali appropriati nelle tabelle e colonne all'interno di **set di dati**.  
  
 Contenuto della sezione viene illustrato il mapping dei seguenti vincoli di XML Schema:  
  
-   Il vincolo di univocità specificato mediante il **univoco** elemento.  
  
-   Il vincolo di chiave specificato utilizzando il **chiave** elemento.  
  
-   Il vincolo keyref specificato mediante il **keyref** elemento.  
  
 Usando un vincolo su un elemento o su un attributo, si specificano determinate restrizioni relative ai valori dell'elemento in qualsiasi istanza del documento. Ad esempio, un vincolo di chiave in un **CustomerID** elemento figlio di un **cliente** elemento nello schema indica che i valori del **CustomerID** deve essere l'elemento figlio univoco in qualsiasi istanza di documento, e che non sono consentiti valori null.  
  
 È anche possibile specificare vincoli tra elementi e attributi in un documento, in modo da stabilire una relazione all'interno del documento. I vincoli key e keyref vengono usati nello schema per specificare i vincoli all'interno del documento, creando quindi una relazione tra gli elementi e gli attributi del documento.  
  
 Il processo di mapping consente di convertire tali vincoli dello schema in vincoli appropriati per le tabelle create all'interno di **DataSet**.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Eseguire il mapping di vincoli di XML Schema (XSD) univoci e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli univoci in un **DataSet**.  
  
 [Chiave mappa i vincoli di XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli key (vincoli univoci in cui non sono consentiti valori null) in un **DataSet**.  
  
 [Eseguire il mapping di XML Schema (XSD) vincoli keyref e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare keyref vincoli (chiave esterna) in un **DataSet**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [La derivazione di struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **DataSet** creato dallo schema XSD.  
  
 [La generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un **DataSet**.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
