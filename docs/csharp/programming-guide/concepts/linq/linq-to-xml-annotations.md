---
title: Annotazioni LINQ to XML
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 8b8e03b0174ad2bf044c21eb9a9d3391da37fb7f
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960699"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="1553c-102">Annotazioni LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1553c-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="1553c-103">Le annotazioni in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono di associare qualsiasi oggetto arbitrario di qualsiasi tipo arbitrario a qualsiasi componente XML di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="1553c-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="1553c-104">Per aggiungere un'annotazione a un componente XML, ad esempio <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, viene chiamato il metodo <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="1553c-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="1553c-105">Le annotazioni vengono recuperate in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="1553c-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="1553c-106">Si noti che le annotazioni non fanno parte dell'infoset XML; non sono serializzate né deserializzate.</span><span class="sxs-lookup"><span data-stu-id="1553c-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1553c-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="1553c-107">Methods</span></span>  
 <span data-ttu-id="1553c-108">Con le annotazioni è possibile usare i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1553c-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="1553c-109">Metodo</span><span class="sxs-lookup"><span data-stu-id="1553c-109">Method</span></span>|<span data-ttu-id="1553c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1553c-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="1553c-111">Consente di aggiungere un oggetto all'elenco di annotazioni di un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1553c-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="1553c-112">Consente di ottenere il primo oggetto annotazione del tipo specificato da un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1553c-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="1553c-113">Consente di ottenere una raccolta di annotazioni del tipo specificato per un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1553c-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="1553c-114">Consente di rimuove le annotazioni del tipo specificato da un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1553c-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1553c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1553c-115">See Also</span></span>  
 [<span data-ttu-id="1553c-116">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="1553c-116">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
