---
title: Compilazione dello schema XmlSchemaCollection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a>Compilazione dello schema XmlSchemaCollection
Il **XmlSchemaCollection** è una cache o una libreria in cui possono essere archiviati e convalidati gli schemi XML-Data Reduced (XDR) e XML Schema definition language (XSD). **XmlSchemaCollection** migliora le prestazioni memorizzando nella cache degli schemi nella cache anziché accedervi da un file o URL.  
  
> [!NOTE]
>  Sebbene il **XmlSchemaCollection** classe archivia sia schemi XDR e schemi XML, tutti i metodi e proprietà che accettano o restituiscono un **XmlSchema** oggetto supporta solo schemi XML.  
  
> [!IMPORTANT]
>  La classe <xref:System.Xml.Schema.XmlSchemaCollection> è obsoleta ed è stata sostituita dalla classe <xref:System.Xml.Schema.XmlSchemaSet>. Per ulteriori informazioni sul <xref:System.Xml.Schema.XmlSchemaSet> classe, vedere [XmlSchemaSet per la compilazione dello Schema](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## <a name="add-schemas-to-the-collection"></a>Aggiunta di schemi alla raccolta  
 Gli schemi vengono caricati nella raccolta usando il **Aggiungi** metodo **XmlSchemaCollection**, momento in cui è associato a un URI dello spazio dei nomi dello schema. In genere, per gli XML Schema l'URI dello spazio dei nomi è lo spazio dei nomi di destinazione per lo schema. Per gli schemi XDR, invece, l'URI dello spazio dei nomi è lo spazio dei nomi specificato quando lo schema è stato aggiunto alla raccolta.  
  
## <a name="check-for-a-schema-in-the-collection"></a>Verifica di uno schema nella raccolta  
 È possibile verificare se uno schema è nella raccolta usando il **Contains** metodo. Il **Contains** metodo accetta un **XmlSchema** oggetto (solo per schemi XML) o una stringa che rappresenta l'URI dello spazio dei nomi associato allo schema (per gli schemi XDR e schemi XML).  
  
## <a name="retrieve-a-schema-from-the-collection"></a>Recupero di uno schema dalla raccolta  
 È possibile recuperare uno schema dalla raccolta utilizzando la **elemento** proprietà. Il **elemento** proprietà accetta una stringa che rappresenta lo spazio dei nomi URI associato allo schema, in genere il relativo spazio dei nomi e restituisce un **XmlSchema** oggetto. Il **elemento** proprietà si applica solo a XML Schema. Per gli schemi XDR, il valore restituito è sempre un riferimento null poiché questi non dispongono di un modello a oggetti.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>Convalida di documenti XML mediante XmlSchemaCollection  
 È possibile convalidare un documento di istanza XML usando un **XmlSchemaCollection** creando il **XmlSchemaCollection** oggetto, aggiungendo gli schemi alla raccolta e l'impostazione di **schemi**  proprietà il **XmlValidatingReader** per assegnare l'oggetto creato **XmlSchemaCollection** per il **XmlValidatingReader**.  
  
### <a name="improved-performance"></a>Miglioramento delle prestazioni  
 È consigliabile, se si convalida più di un documento con lo stesso schema, utilizzare il **XmlSchemaCollection** poiché garantisce prestazioni migliori per la memorizzazione nella cache degli schemi in memoria.  
  
 L'esempio di codice seguente crea il **XmlSchemaCollection** oggetto, aggiunge alla raccolta di schemi e imposta il **schemi** proprietà.  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Convalida XDR con XmlSchemaCollection](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [Convalida di XML Schema (XSD) con XmlSchemaCollection](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
