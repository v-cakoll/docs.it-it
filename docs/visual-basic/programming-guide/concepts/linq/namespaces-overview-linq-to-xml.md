---
title: Panoramica di spazi dei nomi (LINQ to XML) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e9536615871b83099a11e46125ed85b44d9335d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="namespaces-overview-linq-to-xml"></a><span data-ttu-id="e4cac-102">Panoramica degli spazi dei nomi (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="e4cac-102">Namespaces Overview (LINQ to XML)</span></span>
<span data-ttu-id="e4cac-103">Questo argomento vengono presentati gli spazi dei nomi, <xref:System.Xml.Linq.XName>classe e la <xref:System.Xml.Linq.XNamespace>classe.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e4cac-103">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>  
  
## <a name="xml-names"></a><span data-ttu-id="e4cac-104">Nomi XML</span><span class="sxs-lookup"><span data-stu-id="e4cac-104">XML Names</span></span>  
 <span data-ttu-id="e4cac-105">I nomi XML sono spesso causa di complessità nella programmazione XML.</span><span class="sxs-lookup"><span data-stu-id="e4cac-105">XML names are often a source of complexity in XML programming.</span></span> <span data-ttu-id="e4cac-106">Un nome XML è composto da uno spazio dei nomi XML (detto anche URI dello spazio dei nomi XML) e da un nome locale.</span><span class="sxs-lookup"><span data-stu-id="e4cac-106">An XML name consists of an XML namespace (also called an XML namespace URI) and a local name.</span></span> <span data-ttu-id="e4cac-107">Uno spazio dei nomi XML è simile a uno spazio di nomi in un'applicazione basata su [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4cac-107">An XML namespace is similar to a namespace in a [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-based program.</span></span> <span data-ttu-id="e4cac-108">Consente infatti di qualificare in modo univoco i nomi di elementi e attributi</span><span class="sxs-lookup"><span data-stu-id="e4cac-108">It enables you to uniquely qualify the names of elements and attributes.</span></span> <span data-ttu-id="e4cac-109">e quindi di evitare conflitti di nomi tra le diverse parti di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="e4cac-109">This helps avoid name conflicts between various parts of an XML document.</span></span> <span data-ttu-id="e4cac-110">Dopo aver dichiarato uno spazio dei nomi XML, è possibile selezionare un nome locale che deve essere univoco all'interno di tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e4cac-110">When you have declared an XML namespace, you can select a local name that only has to be unique within that namespace.</span></span>  
  
 <span data-ttu-id="e4cac-111">Un'altra peculiarità dei nomi XML in formato XML *i prefissi dello spazio dei nomi*.</span><span class="sxs-lookup"><span data-stu-id="e4cac-111">Another aspect of XML names is XML *namespace prefixes*.</span></span> <span data-ttu-id="e4cac-112">Sono i prefissi XML a costituire la causa di maggior complessità dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="e4cac-112">XML prefixes cause most of the complexity of XML names.</span></span> <span data-ttu-id="e4cac-113">I prefissi consentono di creare un collegamento per uno spazio dei nomi XML al fine di rendere il documento XML più conciso e comprensibile.</span><span class="sxs-lookup"><span data-stu-id="e4cac-113">These prefixes enable you to create a shortcut for an XML namespace, which makes the XML document more concise and understandable.</span></span> <span data-ttu-id="e4cac-114">Tuttavia, il significato dei prefissi XML dipende dal contesto ed è proprio questo aspetto a renderli complessi.</span><span class="sxs-lookup"><span data-stu-id="e4cac-114">However, XML prefixes depend on their context to have meaning, which adds complexity.</span></span> <span data-ttu-id="e4cac-115">Ad esempio, è possibile associare il prefisso XML `aw` a un unico spazio dei nomi XML in un'unica parte di un albero XML e a uno spazio dei nomi XML diverso in una parte diversa dell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="e4cac-115">For example, the XML prefix `aw` could be associated with one XML namespace in one part of an XML tree, and with a different XML namespace in a different part of the XML tree.</span></span>  
  
 <span data-ttu-id="e4cac-116">Quando si utilizza [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] con i valori letterali XML e Visual Basic, è necessario utilizzare i prefissi dello spazio dei nomi quando si lavora con documenti negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e4cac-116">When using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] with Visual Basic and XML literals, you must use namespace prefixes when working with documents in namespaces.</span></span>  
  
 <span data-ttu-id="e4cac-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], la classe che rappresenta i nomi XML è <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e4cac-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the class that represents XML names is <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="e4cac-118">I nomi XML vengono frequentemente in tutta la [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API, in cui è necessario un nome XML, è possibile trovare un <xref:System.Xml.Linq.XName>parametro.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e4cac-118">XML names appear frequently throughout the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API, and wherever an XML name is required, you will find an <xref:System.Xml.Linq.XName> parameter.</span></span> <span data-ttu-id="e4cac-119">Tuttavia, raramente lavorare direttamente con un <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e4cac-119">However, you rarely work directly with an <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="e4cac-120"><xref:System.Xml.Linq.XName>contiene una conversione implicita da stringa.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e4cac-120"><xref:System.Xml.Linq.XName> contains an implicit conversion from string.</span></span>  
  
 <span data-ttu-id="e4cac-121">Per ulteriori informazioni, vedere <xref:System.Xml.Linq.XNamespace>e <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="e4cac-121">For more information, see <xref:System.Xml.Linq.XNamespace> and <xref:System.Xml.Linq.XName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cac-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4cac-122">See Also</span></span>  
 [<span data-ttu-id="e4cac-123">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4cac-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
