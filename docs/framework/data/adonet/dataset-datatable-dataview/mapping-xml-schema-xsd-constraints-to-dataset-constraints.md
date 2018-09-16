---
title: Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: c9cd97535a0165b82f0823c1f17f621491d4255c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677480"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
Lo schema XSD (XML Schema Definition Language) consente di specificare vincoli sugli elementi e sugli attributi in esso definiti. Durante il mapping di un XML Schema allo schema relazionale in una <xref:System.Data.DataSet>, vengono eseguito il mapping di vincoli di XML Schema ai vincoli relazionali appropriati nelle tabelle e colonne all'interno di **set di dati**.  
  
 Contenuto della sezione viene illustrato il mapping dei seguenti vincoli di XML Schema:  
  
-   Il vincolo di univocità specificato mediante il **univoco** elemento.  
  
-   Il vincolo di chiave specificato utilizzando il **chiave** elemento.  
  
-   Il vincolo keyref specificato mediante il **keyref** elemento.  
  
 Usando un vincolo su un elemento o su un attributo, si specificano determinate restrizioni relative ai valori dell'elemento in qualsiasi istanza del documento. Ad esempio, un vincolo di chiave in un **CustomerID** elemento figlio di un **Customer** elemento nello schema indica che i valori del **CustomerID** elemento figlio deve essere univoco in qualsiasi istanza del documento, e che non sono consentiti valori null.  
  
 È anche possibile specificare vincoli tra elementi e attributi in un documento, in modo da stabilire una relazione all'interno del documento. I vincoli key e keyref vengono usati nello schema per specificare i vincoli all'interno del documento, creando quindi una relazione tra gli elementi e gli attributi del documento.  
  
 Il processo di mapping consente di convertire tali vincoli dello schema in vincoli appropriati per le tabelle create all'interno di **set di dati**.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping tra vincoli XML Schema (XSD) univoci e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli univoci in una **set di dati**.  
  
 [Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli key (vincoli univoci in cui non sono consentiti valori null) in un **set di dati**.  
  
 [Mapping tra vincoli keyref XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema usati per creare keyref vincoli (chiave esterna) in un **set di dati**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **set di dati** che viene creato da uno schema XSD.  
  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema usati per creare relazioni tra le colonne della tabella in un **set di dati**.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
