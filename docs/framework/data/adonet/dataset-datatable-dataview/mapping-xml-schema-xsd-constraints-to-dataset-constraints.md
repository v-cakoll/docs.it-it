---
title: Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: b0082b534b8df10ac5277cf2f5aa5b2d2e40c11b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204629"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
Lo schema XSD (XML Schema Definition Language) consente di specificare vincoli sugli elementi e sugli attributi in esso definiti. Quando si esegue il mapping di un XML Schema a uno <xref:System.Data.DataSet>schema relazionale in un, i vincoli XML schema vengono mappati ai vincoli relazionali appropriati sulle tabelle e sulle colonne all'interno del **set di dati**.  
  
 Contenuto della sezione viene illustrato il mapping dei seguenti vincoli di XML Schema:  
  
- Vincolo di univocità specificato utilizzando l'elemento **Unique** .  
  
- Vincolo di chiave specificato mediante l'elemento **Key** .  
  
- Vincolo keyref specificato utilizzando l'elemento **keyref** .  
  
 Usando un vincolo su un elemento o su un attributo, si specificano determinate restrizioni relative ai valori dell'elemento in qualsiasi istanza del documento. Un vincolo di chiave per un elemento figlio **CustomerID** di un elemento **Customer** nello schema, ad esempio, indica che i valori dell'elemento figlio **CustomerID** devono essere univoci in qualsiasi istanza del documento e che i valori null non sono consentiti.  
  
 È anche possibile specificare vincoli tra elementi e attributi in un documento, in modo da stabilire una relazione all'interno del documento. I vincoli key e keyref vengono usati nello schema per specificare i vincoli all'interno del documento, creando quindi una relazione tra gli elementi e gli attributi del documento.  
  
 Il processo di mapping converte questi vincoli dello schema in vincoli appropriati per le tabelle create all'interno del **set di dati**.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping tra vincoli XML Schema (XSD) univoci e vincoli di DataSet](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema usati per creare vincoli univoci in un **set di dati**.  
  
 [Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di DataSet](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema usati per creare vincoli di chiave (vincoli UNIQUE in cui i valori null non sono consentiti) in un **set di dati**.  
  
 [Mapping tra vincoli keyref XML Schema (XSD) e vincoli di DataSet](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli keyref (Foreign Key) in un **set di dati**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **set di dati** creato da uno schema XSD.  
  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un **set di dati**.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
