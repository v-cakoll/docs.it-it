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
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="e03c9-102">Compilazione dello schema XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e03c9-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="e03c9-103">Il **XmlSchemaCollection** è una cache o una libreria in cui possono essere archiviati e convalidati gli schemi XML-Data Reduced (XDR) e XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="e03c9-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="e03c9-104">**XmlSchemaCollection** migliora le prestazioni memorizzando nella cache degli schemi nella cache anziché accedervi da un file o URL.</span><span class="sxs-lookup"><span data-stu-id="e03c9-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e03c9-105">Sebbene il **XmlSchemaCollection** classe archivia sia schemi XDR e schemi XML, tutti i metodi e proprietà che accettano o restituiscono un **XmlSchema** oggetto supporta solo schemi XML.</span><span class="sxs-lookup"><span data-stu-id="e03c9-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e03c9-106">La classe <xref:System.Xml.Schema.XmlSchemaCollection> è obsoleta ed è stata sostituita dalla classe <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="e03c9-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="e03c9-107">Per ulteriori informazioni sul <xref:System.Xml.Schema.XmlSchemaSet> classe, vedere [XmlSchemaSet per la compilazione dello Schema](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="e03c9-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="e03c9-108">Aggiunta di schemi alla raccolta</span><span class="sxs-lookup"><span data-stu-id="e03c9-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="e03c9-109">Gli schemi vengono caricati nella raccolta usando il **Aggiungi** metodo **XmlSchemaCollection**, momento in cui è associato a un URI dello spazio dei nomi dello schema.</span><span class="sxs-lookup"><span data-stu-id="e03c9-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="e03c9-110">In genere, per gli XML Schema l'URI dello spazio dei nomi è lo spazio dei nomi di destinazione per lo schema.</span><span class="sxs-lookup"><span data-stu-id="e03c9-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="e03c9-111">Per gli schemi XDR, invece, l'URI dello spazio dei nomi è lo spazio dei nomi specificato quando lo schema è stato aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="e03c9-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="e03c9-112">Verifica di uno schema nella raccolta</span><span class="sxs-lookup"><span data-stu-id="e03c9-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="e03c9-113">È possibile verificare se uno schema è nella raccolta usando il **Contains** metodo.</span><span class="sxs-lookup"><span data-stu-id="e03c9-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="e03c9-114">Il **Contains** metodo accetta un **XmlSchema** oggetto (solo per schemi XML) o una stringa che rappresenta l'URI dello spazio dei nomi associato allo schema (per gli schemi XDR e schemi XML).</span><span class="sxs-lookup"><span data-stu-id="e03c9-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="e03c9-115">Recupero di uno schema dalla raccolta</span><span class="sxs-lookup"><span data-stu-id="e03c9-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="e03c9-116">È possibile recuperare uno schema dalla raccolta utilizzando la **elemento** proprietà.</span><span class="sxs-lookup"><span data-stu-id="e03c9-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="e03c9-117">Il **elemento** proprietà accetta una stringa che rappresenta lo spazio dei nomi URI associato allo schema, in genere il relativo spazio dei nomi e restituisce un **XmlSchema** oggetto.</span><span class="sxs-lookup"><span data-stu-id="e03c9-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="e03c9-118">Il **elemento** proprietà si applica solo a XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e03c9-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="e03c9-119">Per gli schemi XDR, il valore restituito è sempre un riferimento null poiché questi non dispongono di un modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="e03c9-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="e03c9-120">Convalida di documenti XML mediante XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e03c9-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="e03c9-121">È possibile convalidare un documento di istanza XML usando un **XmlSchemaCollection** creando il **XmlSchemaCollection** oggetto, aggiungendo gli schemi alla raccolta e l'impostazione di **schemi**  proprietà il **XmlValidatingReader** per assegnare l'oggetto creato **XmlSchemaCollection** per il **XmlValidatingReader**.</span><span class="sxs-lookup"><span data-stu-id="e03c9-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="e03c9-122">Miglioramento delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e03c9-122">Improved Performance</span></span>  
 <span data-ttu-id="e03c9-123">È consigliabile, se si convalida più di un documento con lo stesso schema, utilizzare il **XmlSchemaCollection** poiché garantisce prestazioni migliori per la memorizzazione nella cache degli schemi in memoria.</span><span class="sxs-lookup"><span data-stu-id="e03c9-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="e03c9-124">L'esempio di codice seguente crea il **XmlSchemaCollection** oggetto, aggiunge alla raccolta di schemi e imposta il **schemi** proprietà.</span><span class="sxs-lookup"><span data-stu-id="e03c9-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e03c9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e03c9-125">See Also</span></span>  
 [<span data-ttu-id="e03c9-126">Convalida XDR con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e03c9-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="e03c9-127">Convalida di XML Schema (XSD) con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e03c9-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
