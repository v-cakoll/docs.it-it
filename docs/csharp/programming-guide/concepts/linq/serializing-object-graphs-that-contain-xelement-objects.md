---
title: Serializzazione di oggetti grafici contenenti oggetti XElement (C#)
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
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
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
ms.openlocfilehash: 4e7b1d6365eb27596477de39577caa4144aa3501
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="68821-102">Serializzazione di oggetti grafici contenenti oggetti XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="68821-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="68821-103">In questo argomento viene presentata la funzionalità di serializzazione di oggetti grafici contenenti riferimenti a oggetti di tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="68821-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="68821-104">Per semplificare questo tipo di serializzazione, <xref:System.Xml.Linq.XElement> implementa l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="68821-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="68821-105">Si noti che solo la classe <xref:System.Xml.Linq.XElement> implementa la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="68821-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68821-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="68821-106">In This Section</span></span>  
  
|<span data-ttu-id="68821-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="68821-107">Topic</span></span>|<span data-ttu-id="68821-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68821-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="68821-109">Procedura: Serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="68821-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="68821-110">Viene illustrato come eseguire la serializzazione tramite <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="68821-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="68821-111">Procedura: Serializzare tramite DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="68821-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="68821-112">Viene illustrato come eseguire la serializzazione tramite <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="68821-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68821-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68821-113">See Also</span></span>  
 [<span data-ttu-id="68821-114">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="68821-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

