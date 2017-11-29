---
title: Serializzazione di oggetti grafici contenenti oggetti XElement (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b7da4429360beb20fa304b592020d48666fe732
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="05389-102">Serializzazione di oggetti grafici contenenti oggetti XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="05389-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="05389-103">In questo argomento viene presentata la funzionalità di serializzazione di oggetti grafici contenenti riferimenti a oggetti di tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="05389-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="05389-104">Per semplificare questo tipo di serializzazione, <xref:System.Xml.Linq.XElement> implementa l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="05389-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="05389-105">Si noti che solo la classe <xref:System.Xml.Linq.XElement> implementa la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="05389-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05389-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="05389-106">In This Section</span></span>  
  
|<span data-ttu-id="05389-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="05389-107">Topic</span></span>|<span data-ttu-id="05389-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05389-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="05389-109">Procedura: Serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="05389-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="05389-110">Viene illustrato come eseguire la serializzazione tramite <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="05389-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="05389-111">Procedura: Serializzare tramite DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="05389-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="05389-112">Viene illustrato come eseguire la serializzazione tramite <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="05389-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05389-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05389-113">See Also</span></span>  
 [<span data-ttu-id="05389-114">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="05389-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
