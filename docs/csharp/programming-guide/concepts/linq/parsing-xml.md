---
title: Analisi di codice XML (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d262fd2177ac77ab5109362f94cc51d03c9563c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-xml-c"></a><span data-ttu-id="4c55a-102">Analisi di codice XML (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-102">Parsing XML (C#)</span></span>
<span data-ttu-id="4c55a-103">Negli argomenti di questa sezione viene descritto come analizzare documenti XML.</span><span class="sxs-lookup"><span data-stu-id="4c55a-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c55a-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4c55a-104">In This Section</span></span>  
  
|<span data-ttu-id="4c55a-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="4c55a-105">Topic</span></span>|<span data-ttu-id="4c55a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c55a-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4c55a-107">Procedura: Analizzare una stringa (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-107">How to: Parse a String (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="4c55a-108">Viene illustrato come analizzare una stringa per creare una struttura ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="4c55a-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="4c55a-109">Procedura: Caricare XML da un file (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-109">How to: Load XML from a File (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="4c55a-110">Viene illustrato come caricare XML da un URI usando il metodo <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c55a-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="4c55a-111">Conservazione di spazi vuoti durante il caricamento o l'analisi di dati XML</span><span class="sxs-lookup"><span data-stu-id="4c55a-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="4c55a-112">Viene descritto come controllare il comportamento dello spazio vuoto di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] durante il caricamento di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="4c55a-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="4c55a-113">Procedura: Intercettare gli errori di analisi (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-113">How to: Catch Parsing Errors (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="4c55a-114">Viene illustrato come rilevare XML non corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="4c55a-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="4c55a-115">Procedura: Creare una struttura ad albero da un XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-115">How to: Create a Tree from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="4c55a-116">Viene illustrato come creare un albero XML direttamente da un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="4c55a-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="4c55a-117">Procedura: flusso di frammenti XML da un XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-117">How to: Stream XML Fragments from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="4c55a-118">Viene illustrato come eseguire il flusso di frammenti XML usando un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="4c55a-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="4c55a-119">Quando è necessario elaborare file XML grandi in modo arbitrario, potrebbe risultare impossibile caricare in memoria l'intero albero XML.</span><span class="sxs-lookup"><span data-stu-id="4c55a-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="4c55a-120">In tali casi, è possibile eseguire il flusso di frammenti XML.</span><span class="sxs-lookup"><span data-stu-id="4c55a-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c55a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c55a-121">See Also</span></span>  
 [<span data-ttu-id="4c55a-122">Creazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="4c55a-122">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
