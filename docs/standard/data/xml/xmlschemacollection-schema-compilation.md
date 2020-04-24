---
title: Compilazione dello schema XmlSchemaCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
ms.openlocfilehash: af6df3729f1bd926e9a47cc5b9d9bf460c8e1225
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159286"
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="a3a13-102">Compilazione dello schema XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="a3a13-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="a3a13-103">**XmlSchemaCollection** è una cache o una libreria in cui è possibile archiviare e convalidare gli schemi XDR (XML-Data Reduced) e XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="a3a13-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="a3a13-104">**XmlSchemaCollection** migliora le prestazioni memorizzando nella cache gli schemi anziché accedervi da un file o un URL.</span><span class="sxs-lookup"><span data-stu-id="a3a13-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3a13-105">Sebbene la classe **XmlSchemaCollection** archivi sia schemi XDR che XML Schema, tutti i metodi e le proprietà che accettano o restituiscono un oggetto **XmlSchema** supportano solo gli XML Schema.</span><span class="sxs-lookup"><span data-stu-id="a3a13-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a3a13-106">La classe <xref:System.Xml.Schema.XmlSchemaCollection> è obsoleta ed è stata sostituita dalla classe <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="a3a13-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="a3a13-107">Per altre informazioni sulla classe <xref:System.Xml.Schema.XmlSchemaSet>, vedere [XmlSchemaSet per la compilazione di schemi](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="a3a13-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="a3a13-108">Aggiunta di schemi alla raccolta</span><span class="sxs-lookup"><span data-stu-id="a3a13-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="a3a13-109">Gli schemi vengono caricati nella raccolta usando il metodo **Add** di **XmlSchemaCollection** e a ogni schema viene associato un URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a3a13-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="a3a13-110">In genere, per gli XML Schema l'URI dello spazio dei nomi è lo spazio dei nomi di destinazione per lo schema.</span><span class="sxs-lookup"><span data-stu-id="a3a13-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="a3a13-111">Per gli schemi XDR, invece, l'URI dello spazio dei nomi è lo spazio dei nomi specificato quando lo schema è stato aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="a3a13-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="a3a13-112">Verifica di uno schema nella raccolta</span><span class="sxs-lookup"><span data-stu-id="a3a13-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="a3a13-113">È possibile verificare se uno schema è presente nella raccolta usando il metodo **Contains**,</span><span class="sxs-lookup"><span data-stu-id="a3a13-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="a3a13-114">che **accetta** un oggetto **XmlSchema** (solo per XML Schema) o una stringa che rappresenta l'URI dello spazio dei nomi associato allo schema (per gli schemi XDR e XML Schema).</span><span class="sxs-lookup"><span data-stu-id="a3a13-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="a3a13-115">Recupero di uno schema dalla raccolta</span><span class="sxs-lookup"><span data-stu-id="a3a13-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="a3a13-116">È possibile recuperare uno schema dalla raccolta usando la proprietà **Item**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="a3a13-117">Tale **proprietà** accetta una stringa che rappresenta l'URI dello spazio dei nomi associato allo schema, in genere lo spazio dei nomi di destinazione corrispondente, e restituisce un oggetto **XmlSchema**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="a3a13-118">La proprietà **Item** si applica solo a XML Schema.</span><span class="sxs-lookup"><span data-stu-id="a3a13-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="a3a13-119">Per gli schemi XDR, il valore restituito è sempre un riferimento null poiché questi non dispongono di un modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="a3a13-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="a3a13-120">Convalida di documenti XML mediante XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="a3a13-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="a3a13-121">È possibile convalidare un documento di istanza XML tramite **XmlSchemaCollection** creando l'oggetto **XmlSchemaCollection**, aggiungendo gli schemi alla raccolta e impostando la proprietà **Schemas** su **XmlValidatingReader** per assegnare l'oggetto **XmlSchemaCollection** creato a **XmlValidatingReader**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="a3a13-122">Prestazioni migliorate</span><span class="sxs-lookup"><span data-stu-id="a3a13-122">Improved Performance</span></span>  
 <span data-ttu-id="a3a13-123">Si consiglia, se si convalida più di un documento rispetto allo stesso schema, di usare **XmlSchemaCollection** in quanto la memorizzazione degli schemi nella cache garantisce prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="a3a13-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="a3a13-124">Nel seguente codice di esempio viene creato un oggetto **XmlSchemaCollection**, vengono aggiunti schemi alla raccolta e viene impostata la proprietà **Schemas**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a3a13-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a3a13-125">See also</span></span>

- [<span data-ttu-id="a3a13-126">Convalida XDR con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="a3a13-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)
- [<span data-ttu-id="a3a13-127">Convalida XSD (XML Schema) con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="a3a13-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
