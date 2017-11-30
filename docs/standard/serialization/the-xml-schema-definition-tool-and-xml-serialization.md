---
title: Strumento XML Schema Definition e serializzazione XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b943251ff426d5557c4715a856ffdadd3013b9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="512ea-102">Strumento XML Schema Definition e serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="512ea-102">The XML Schema Definition Tool and XML Serialization</span></span>
<span data-ttu-id="512ea-103">Lo strumento XML Schema Definition ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) viene installato insieme agli strumenti .NET Framework come parte di Windows® Software Development Kit (SDK).</span><span class="sxs-lookup"><span data-stu-id="512ea-103">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows® Software Development Kit (SDK).</span></span> <span data-ttu-id="512ea-104">Lo strumento è progettato principalmente per due scopi:</span><span class="sxs-lookup"><span data-stu-id="512ea-104">The tool is designed primarily for two purposes:</span></span>  
  
-   <span data-ttu-id="512ea-105">Per generare file di classe C# o Visual Basic conformi a uno schema XML Schema Definition Language (XSD) specifico.</span><span class="sxs-lookup"><span data-stu-id="512ea-105">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="512ea-106">Lo strumento prende uno schema XML come argomento e restituisce un file contenente un numero di classi che, se serializzate con <xref:System.Xml.Serialization.XmlSerializer>, risultano conformi allo schema.</span><span class="sxs-lookup"><span data-stu-id="512ea-106">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="512ea-107">Per informazioni su come usare lo strumento per generare classi conformi a uno schema specifico, vedere [Procedura: Usare lo strumento XML Schema Definition per generare classi e documenti XML Schema](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="512ea-107">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
-   <span data-ttu-id="512ea-108">Per generare un documento XML Schema da un file con estensione dll o exe.</span><span class="sxs-lookup"><span data-stu-id="512ea-108">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="512ea-109">Per visualizzare lo schema di un set di file creati o di uno schema modificato con attributi, passare il file DLL o EXE come argomento allo strumento per generare l'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="512ea-109">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="512ea-110">Per informazioni su come usare lo strumento per generare un documento XML Schema da un set di classi, vedere [Procedura: Usare lo strumento XML Schema Definition per generare classi e documenti XML Schema](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="512ea-110">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
 <span data-ttu-id="512ea-111">Per altre informazioni su questo e altri strumenti, vedere [Strumenti](../../../docs/framework/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="512ea-111">For more information about this tool and others, see [Tools](../../../docs/framework/tools/index.md).</span></span> <span data-ttu-id="512ea-112">Per informazioni sulle opzioni dello strumento, vedere [Strumento XML Schema Definition (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="512ea-112">For information about the tool's options, see [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512ea-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="512ea-113">See Also</span></span>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="512ea-114">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="512ea-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="512ea-115">Strumento XML Schema Definition (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="512ea-115">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="512ea-116">Procedura: Serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="512ea-116">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="512ea-117">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="512ea-117">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 [<span data-ttu-id="512ea-118">Procedura: Usare lo strumento XML Schema Definition per generare classi e documenti XML Schema</span><span class="sxs-lookup"><span data-stu-id="512ea-118">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)  
 [<span data-ttu-id="512ea-119">Supporto dell'associazione all'XML Schema in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="512ea-119">XML Schema Binding Support in the .NET Framework</span></span>](http://msdn.microsoft.com/en-us/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)
