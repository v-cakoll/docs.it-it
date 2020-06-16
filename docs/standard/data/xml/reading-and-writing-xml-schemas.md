---
title: Lettura e scrittura di schemi XML
description: Lettura e scrittura di schemi XSD (XML Schema Definition Language) da file o altre origini in .NET tramite l'API del modello SOM (Schema Object Model).
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 874b0bdb0e13d545cfff4c813881f1398a8f9487
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767663"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="7ce32-103">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-103">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="7ce32-104">È possibile usare l'API del modello SOM (Schema Object Model) per scrivere e leggere gli schemi XSD (XML Schema Definition Language) da file o altre origini e compilare schemi XML in memoria usando le classi nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType> associato alle strutture definite nella raccomandazione W3C (World Wide Web Consortium) "XML Schema".</span><span class="sxs-lookup"><span data-stu-id="7ce32-104">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="7ce32-105">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-105">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="7ce32-106">La classe <xref:System.Xml.Schema.XmlSchema> fornisce i metodi <xref:System.Xml.Schema.XmlSchema.Read%2A> e <xref:System.Xml.Schema.XmlSchema.Write%2A> per leggere e scrivere schemi XML.</span><span class="sxs-lookup"><span data-stu-id="7ce32-106">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="7ce32-107">Il metodo <xref:System.Xml.Schema.XmlSchema.Read%2A> restituisce un oggetto <xref:System.Xml.Schema.XmlSchema> che rappresenta lo schema XML e accetta un tipo <xref:System.Xml.Schema.ValidationEventHandler> facoltativo come parametro per gestire i messaggi di avviso e di errore della convalida dello rilevati durante la lettura di uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="7ce32-107">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="7ce32-108">Il metodo <xref:System.Xml.Schema.XmlSchema.Write%2A> scrive schemi XML negli oggetti <xref:System.IO.Stream>, <xref:System.IO.TextWriter> e <xref:System.Xml.XmlWriter> e può accettare un oggetto <xref:System.Xml.XmlNamespaceManager> facoltativo come parametro.</span><span class="sxs-lookup"><span data-stu-id="7ce32-108">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="7ce32-109">Un tipo <xref:System.Xml.XmlNamespaceManager> viene usato per la gestione degli spazi dei nomi rilevati in uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="7ce32-109">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="7ce32-110">Per altre informazioni sulla classe <xref:System.Xml.XmlNamespaceManager>, vedere [Gestione di spazi dei nomi in un documento XML](managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="7ce32-110">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="7ce32-111">Nell'esempio di codice seguente vengono mostrate la lettura da un file e la scrittura in un file di schemi XML.</span><span class="sxs-lookup"><span data-stu-id="7ce32-111">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="7ce32-112">Il codice di esempio legge il file `example.xsd` in un oggetto <xref:System.Xml.Schema.XmlSchema> mediante il metodo `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>, quindi scrive il file nella console e in un nuovo file `new.xsd`.</span><span class="sxs-lookup"><span data-stu-id="7ce32-112">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="7ce32-113">Inoltre, il codice di esempio fornisce un tipo <xref:System.Xml.Schema.ValidationEventHandler> come parametro per il metodo `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>, per gestire eventuali errori o avvisi di convalida dello schema rilevati durante la generazione di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7ce32-113">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="7ce32-114">Se il tipo <xref:System.Xml.Schema.ValidationEventHandler> non è specificato (`null`), non vengono riportati né avvisi né errori.</span><span class="sxs-lookup"><span data-stu-id="7ce32-114">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="7ce32-115">Nell'esempio il file `example.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="7ce32-115">The example takes the `example.xsd` as input.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7ce32-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ce32-116">See also</span></span>

- [<span data-ttu-id="7ce32-117">Cenni preliminari sul modello SOM XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-117">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="7ce32-118">Compilazione di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7ce32-118">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="7ce32-119">Attraversamento di schemi XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-119">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="7ce32-120">Modifica di schemi XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-120">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="7ce32-121">Inclusione o importazione di schemi XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-121">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="7ce32-122">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="7ce32-122">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="7ce32-123">Post-Schema Compilation Infoset (PSCI, infoset sulla compilazione post-schema)</span><span class="sxs-lookup"><span data-stu-id="7ce32-123">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
- [<span data-ttu-id="7ce32-124">Gestione di spazi dei nomi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="7ce32-124">Managing Namespaces in an XML Document</span></span>](managing-namespaces-in-an-xml-document.md)
