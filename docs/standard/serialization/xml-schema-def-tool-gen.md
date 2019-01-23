---
title: 'Procedura: Utilizzare lo strumento di definizione XML Schema per generare classi e documenti XML Schema.'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 645d6290ec16a772d8c188e8781097e1d67b14ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501541"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Procedura: Utilizzare lo strumento di definizione XML Schema per generare classi e documenti XML Schema.
Lo strumento XML Schema Definition (Xsd.exe) consente di generare un XML Schema che descrive una classe o di generare la classe definita da un XML Schema. Le procedure descritte di seguito mostrano come eseguire queste operazioni.  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>Per generare classi conformi a uno schema specifico  
  
1.  Aprire un prompt dei comandi.  
  
2.  Passare lo schema XML come argomento allo strumento XML Schema Definition, che crea un set di classi esattamente corrispondenti allo schema XML, ad esempio:  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     Lo strumento è in grado di elaborare solo schemi che fanno riferimento alla specifica XML del World Wide Web Consortium del 16 marzo 2001. In altre parole, deve essere lo spazio dei nomi XML Schema "http://www.w3.org/2001/XMLSchema" come illustrato nell'esempio seguente.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  Modificare le classi con metodi, proprietà o campi, in base alle necessità. Per altre informazioni sulla modifica di una classe con attributi, vedere [Controllo della serializzazione XML mediante attributi](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) e [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Spesso risulta utile esaminare lo schema del flusso XML generato quando vengono serializzate istanze di una classe (o di più classi). Ad esempio, è possibile pubblicare lo schema affinché venga utilizzato da altri o è possibile confrontarlo a uno schema con il quale si sta cercando di ottenere la compatibilità.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>Per generare un documento XML Schema da un set di classi  
  
1.  Compilare la classe o le classi in una DLL.  
  
2.  Aprire un prompt dei comandi.  
  
3.  Passare la DLL come argomento a Xsd.exe, ad esempio:  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     Lo schema (o gli schemi) sarà scritto, a partire dal nome "schema0.xsd."  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataSet>
- [Strumento XML Schema Definition e serializzazione XML](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Strumento XML Schema Definition (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procedura: Serializzare un oggetto](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
