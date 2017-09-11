---
title: Serializzazione con una dichiarazione XML (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36ffb8ddd584785c660896ca77707d504638852f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="3dde2-102">Serializzazione con una dichiarazione XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3dde2-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="3dde2-103">In questo argomento viene descritto come controllare se la serializzazione genera una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="3dde2-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="3dde2-104">Generazione della dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="3dde2-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="3dde2-105">La serializzazione di <xref:System.IO.File> o <xref:System.IO.TextWriter> tramite il metodo <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> o il metodo <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> genera una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="3dde2-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="3dde2-106">Quando si serializza in <xref:System.Xml.XmlWriter>, le impostazioni del writer (specificate in un oggetto <xref:System.Xml.XmlWriterSettings>) determinano se una dichiarazione XML viene generata o meno.</span><span class="sxs-lookup"><span data-stu-id="3dde2-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="3dde2-107">Se si serializza in una stringa tramite il metodo `ToString`, l'XML risultante non includerà una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="3dde2-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="3dde2-108">Serializzazione con una dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="3dde2-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="3dde2-109">Nell'esempio seguente viene creato un oggetto <xref:System.Xml.Linq.XElement>, viene salvato il documento in un file e quindi stampato il file nella console.</span><span class="sxs-lookup"><span data-stu-id="3dde2-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="3dde2-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="3dde2-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="3dde2-111">Serializzazione senza una dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="3dde2-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="3dde2-112">Nell'esempio seguente viene illustrato come salvare <xref:System.Xml.Linq.XElement> in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="3dde2-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="3dde2-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="3dde2-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dde2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dde2-114">See Also</span></span>  
 [<span data-ttu-id="3dde2-115">Serializzazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3dde2-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

