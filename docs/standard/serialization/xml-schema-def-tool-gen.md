---
title: 'Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 2bbdced0f984b653a58afba9685683e8c0891271
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389792"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="09ad8-102">Procedura: utilizzare lo strumento XML Schema Definition per generare classi e documenti di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="09ad8-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="09ad8-103">Lo strumento XML Schema Definition (Xsd.exe) consente di generare un XML Schema che descrive una classe o di generare la classe definita da un XML Schema.</span><span class="sxs-lookup"><span data-stu-id="09ad8-103">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="09ad8-104">Le procedure descritte di seguito mostrano come eseguire queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="09ad8-104">The following procedures show how to perform these operations.</span></span>

<span data-ttu-id="09ad8-105">Lo strumento XML Schema Definition (XSD. exe) si trova in genere nel percorso seguente: </span><span class="sxs-lookup"><span data-stu-id="09ad8-105">The XML Schema Definition tool (Xsd.exe) usually can be found in the following path:</span></span>\
<span data-ttu-id="09ad8-106">_C:\\programmi (x86)\\Microsoft SDK\\Windows\\{Version}\\bin\\NetFx {Version} Tools\\_</span><span class="sxs-lookup"><span data-stu-id="09ad8-106">_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span></span>

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="09ad8-107">Per generare classi conformi a uno schema specifico</span><span class="sxs-lookup"><span data-stu-id="09ad8-107">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="09ad8-108">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="09ad8-108">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="09ad8-109">Passare lo schema XML come argomento allo strumento XML Schema Definition, che crea un set di classi esattamente corrispondenti allo schema XML, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09ad8-109">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="09ad8-110">Lo strumento è in grado di elaborare solo schemi che fanno riferimento alla specifica XML del World Wide Web Consortium del 16 marzo 2001.</span><span class="sxs-lookup"><span data-stu-id="09ad8-110">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="09ad8-111">In altre parole, lo spazio dei nomi dello schema XMLhttp://www.w3.org/2001/XMLSchemadeve essere "", come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="09ad8-111">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. <span data-ttu-id="09ad8-112">Modificare le classi con metodi, proprietà o campi, in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="09ad8-112">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="09ad8-113">Per altre informazioni sulla modifica di una classe con attributi, vedere [Controllo della serializzazione XML mediante attributi](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) e [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="09ad8-113">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="09ad8-114">Spesso risulta utile esaminare lo schema del flusso XML generato quando vengono serializzate istanze di una classe (o di più classi).</span><span class="sxs-lookup"><span data-stu-id="09ad8-114">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="09ad8-115">Ad esempio, è possibile pubblicare lo schema affinché venga utilizzato da altri o è possibile confrontarlo a uno schema con il quale si sta cercando di ottenere la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="09ad8-115">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="09ad8-116">Per generare un documento XML Schema da un set di classi</span><span class="sxs-lookup"><span data-stu-id="09ad8-116">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="09ad8-117">Compilare la classe o le classi in una DLL.</span><span class="sxs-lookup"><span data-stu-id="09ad8-117">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="09ad8-118">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="09ad8-118">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="09ad8-119">Passare la DLL come argomento a Xsd.exe, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09ad8-119">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="09ad8-120">Lo schema (o gli schemi) sarà scritto, a partire dal nome "schema0.xsd."</span><span class="sxs-lookup"><span data-stu-id="09ad8-120">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ad8-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="09ad8-121">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="09ad8-122">Strumento XML Schema Definition e serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="09ad8-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="09ad8-123">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="09ad8-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="09ad8-124">Strumento XML Schema Definition (XSD. exe)</span><span class="sxs-lookup"><span data-stu-id="09ad8-124">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="09ad8-125">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="09ad8-125">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="09ad8-126">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="09ad8-126">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
