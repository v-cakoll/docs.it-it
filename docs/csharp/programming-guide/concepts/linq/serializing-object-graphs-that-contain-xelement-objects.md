---
title: Serializzazione di oggetti grafici contenenti oggetti XElement (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: 2e82165421d31ec234de4806b59565fa675217ef
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45618448"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="1b1cf-102">Serializzazione di oggetti grafici contenenti oggetti XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="1b1cf-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="1b1cf-103">In questo argomento viene presentata la funzionalità di serializzazione di oggetti grafici contenenti riferimenti a oggetti di tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="1b1cf-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="1b1cf-104">Per semplificare questo tipo di serializzazione, <xref:System.Xml.Linq.XElement> implementa l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="1b1cf-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="1b1cf-105">Si noti che solo la classe <xref:System.Xml.Linq.XElement> implementa la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="1b1cf-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b1cf-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1b1cf-106">In This Section</span></span>  
  
|<span data-ttu-id="1b1cf-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="1b1cf-107">Topic</span></span>|<span data-ttu-id="1b1cf-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b1cf-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1b1cf-109">Procedura: Serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="1b1cf-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="1b1cf-110">Viene illustrato come eseguire la serializzazione tramite <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1b1cf-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="1b1cf-111">Procedura: Serializzare tramite DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="1b1cf-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="1b1cf-112">Viene illustrato come eseguire la serializzazione tramite <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1b1cf-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b1cf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1cf-113">See Also</span></span>

- [<span data-ttu-id="1b1cf-114">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="1b1cf-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
