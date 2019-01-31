---
title: Serializzazione di oggetti grafici contenenti oggetti XElement (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: db7354598fc84c6fa3f8ec4e5b53799030459387
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569141"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="9433b-102">Serializzazione di oggetti grafici contenenti oggetti XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="9433b-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="9433b-103">In questo argomento viene presentata la funzionalità di serializzazione di oggetti grafici contenenti riferimenti a oggetti di tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9433b-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="9433b-104">Per semplificare questo tipo di serializzazione, <xref:System.Xml.Linq.XElement> implementa l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="9433b-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="9433b-105">Si noti che solo la classe <xref:System.Xml.Linq.XElement> implementa la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="9433b-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9433b-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9433b-106">In This Section</span></span>  
  
|<span data-ttu-id="9433b-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="9433b-107">Topic</span></span>|<span data-ttu-id="9433b-108">Description</span><span class="sxs-lookup"><span data-stu-id="9433b-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9433b-109">Procedura: Serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="9433b-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="9433b-110">Viene illustrato come eseguire la serializzazione tramite <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9433b-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="9433b-111">Procedura: Serializzare tramite DataContractSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="9433b-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="9433b-112">Viene illustrato come eseguire la serializzazione tramite <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9433b-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9433b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9433b-113">See also</span></span>

- [<span data-ttu-id="9433b-114">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="9433b-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
