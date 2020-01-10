---
title: Lettura e scrittura di schemi XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 889c5f85a2ea3fc08dadefda5509de0fcfab76ec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710414"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="8f8e1-102">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-102">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="8f8e1-103">È possibile usare l'API del modello SOM (Schema Object Model) per scrivere e leggere gli schemi XSD (XML Schema Definition Language) da file o altre origini e compilare schemi XML in memoria usando le classi nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType> associato alle strutture definite nella raccomandazione W3C (World Wide Web Consortium) "XML Schema".</span><span class="sxs-lookup"><span data-stu-id="8f8e1-103">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="8f8e1-104">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-104">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="8f8e1-105">La classe <xref:System.Xml.Schema.XmlSchema> fornisce i metodi <xref:System.Xml.Schema.XmlSchema.Read%2A> e <xref:System.Xml.Schema.XmlSchema.Write%2A> per leggere e scrivere schemi XML.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-105">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="8f8e1-106">Il metodo <xref:System.Xml.Schema.XmlSchema.Read%2A> restituisce un oggetto <xref:System.Xml.Schema.XmlSchema> che rappresenta lo schema XML e accetta un tipo <xref:System.Xml.Schema.ValidationEventHandler> facoltativo come parametro per gestire i messaggi di avviso e di errore della convalida dello rilevati durante la lettura di uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-106">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="8f8e1-107">Il metodo <xref:System.Xml.Schema.XmlSchema.Write%2A> scrive schemi XML negli oggetti <xref:System.IO.Stream>, <xref:System.IO.TextWriter> e <xref:System.Xml.XmlWriter> e può accettare un oggetto <xref:System.Xml.XmlNamespaceManager> facoltativo come parametro.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-107">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="8f8e1-108">Un tipo <xref:System.Xml.XmlNamespaceManager> viene usato per la gestione degli spazi dei nomi rilevati in uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-108">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="8f8e1-109">Per altre informazioni sulla classe <xref:System.Xml.XmlNamespaceManager>, vedere [Gestione di spazi dei nomi in un documento XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="8f8e1-109">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="8f8e1-110">Nell'esempio di codice seguente vengono mostrate la lettura da un file e la scrittura in un file di schemi XML.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-110">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="8f8e1-111">Il codice di esempio legge il file `example.xsd` in un oggetto <xref:System.Xml.Schema.XmlSchema> mediante il metodo `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>, quindi scrive il file nella console e in un nuovo file `new.xsd`.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-111">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="8f8e1-112">Inoltre, il codice di esempio fornisce un tipo <xref:System.Xml.Schema.ValidationEventHandler> come parametro per il metodo `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>, per gestire eventuali errori o avvisi di convalida dello schema rilevati durante la generazione di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-112">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="8f8e1-113">Se il tipo <xref:System.Xml.Schema.ValidationEventHandler> non è specificato (`null`), non vengono riportati né avvisi né errori.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-113">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="8f8e1-114">Nell'esempio il file `example.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8f8e1-114">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f8e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f8e1-115">See also</span></span>

- [<span data-ttu-id="8f8e1-116">Panoramica del modello SOM XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-116">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="8f8e1-117">Compilazione di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-117">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="8f8e1-118">Attraversamento di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-118">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="8f8e1-119">Modifica di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-119">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="8f8e1-120">Inclusione o importazione di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-120">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="8f8e1-121">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="8f8e1-121">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="8f8e1-122">Post-Schema-Validation Infoset (PSVI)</span><span class="sxs-lookup"><span data-stu-id="8f8e1-122">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
- [<span data-ttu-id="8f8e1-123">Gestione di spazi dei nomi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="8f8e1-123">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
