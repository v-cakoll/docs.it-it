---
title: 'Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.'
description: Viene illustrato come utilizzare lo strumento XML Schema Definition per generare un XML Schema che descrive una classe o per generare la classe definita da un XML Schema.
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 0e4e84ea7e11b2e7a00c852d4a2075747c71267e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288966"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.
Lo strumento XML Schema Definition (Xsd.exe) consente di generare un XML Schema che descrive una classe o di generare la classe definita da un XML Schema. Le procedure descritte di seguito mostrano come eseguire queste operazioni.

Lo strumento XML Schema Definition (XSD. exe) si trova in genere nel percorso seguente: \
_C: \\ programmi (x86) \\ Microsoft SDK \\ Windows \\ {version} \\ bin \\ NetFx {Version} Tools\\_

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>Per generare classi conformi a uno schema specifico  
  
1. Aprire un prompt dei comandi.  
  
2. Passare lo schema XML come argomento allo strumento XML Schema Definition, che crea un set di classi esattamente corrispondenti allo schema XML, ad esempio:  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     Lo strumento è in grado di elaborare solo schemi che fanno riferimento alla specifica XML del World Wide Web Consortium del 16 marzo 2001. In altre parole, lo spazio dei nomi dello schema XML deve essere " http://www.w3.org/2001/XMLSchema ", come illustrato nell'esempio seguente.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. Modificare le classi con metodi, proprietà o campi, in base alle necessità. Per altre informazioni sulla modifica di una classe con attributi, vedere [Controllo della serializzazione XML mediante attributi](controlling-xml-serialization-using-attributes.md) e [Attributi per il controllo della serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md).  
  
 Spesso risulta utile esaminare lo schema del flusso XML generato quando vengono serializzate istanze di una classe (o di più classi). Ad esempio, è possibile pubblicare lo schema affinché venga utilizzato da altri o è possibile confrontarlo a uno schema con il quale si sta cercando di ottenere la compatibilità.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>Per generare un documento XML Schema da un set di classi  
  
1. Compilare la classe o le classi in una DLL.  
  
2. Aprire un prompt dei comandi.  
  
3. Passare la DLL come argomento a Xsd.exe, ad esempio:  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     Lo schema (o gli schemi) sarà scritto, a partire dal nome "schema0.xsd."  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataSet>
- [Strumento XML Schema Definition e serializzazione XML](the-xml-schema-definition-tool-and-xml-serialization.md)
- [Introduzione alla serializzazione XML](introducing-xml-serialization.md)
- [Strumento XML Schema Definition (XSD. exe)](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
