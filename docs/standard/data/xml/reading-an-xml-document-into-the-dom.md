---
title: Lettura di un documento XML nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
ms.openlocfilehash: 02338d72f51d3a7507c0dfa030383399b9e213f6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282402"
---
# <a name="reading-an-xml-document-into-the-dom"></a><span data-ttu-id="ab840-102">Lettura di un documento XML nel DOM</span><span class="sxs-lookup"><span data-stu-id="ab840-102">Reading an XML Document into the DOM</span></span>
<span data-ttu-id="ab840-103">Le informazioni relative a XML vengono lette in memoria da diversi formati.</span><span class="sxs-lookup"><span data-stu-id="ab840-103">XML information is read into memory from different formats.</span></span> <span data-ttu-id="ab840-104">Possono essere lette da una stringa, un flusso, un URL, un lettore di testo o una classe derivata dal tipo <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ab840-104">It can be read from a string, stream, URL, text reader, or a class derived from the <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="ab840-105">Il metodo <xref:System.Xml.XmlDocument.Load%2A> consente di portare il documento in memoria e di usufruire dei metodi di overload disponibili per prelevare dati da ognuno dei diversi formati.</span><span class="sxs-lookup"><span data-stu-id="ab840-105">The <xref:System.Xml.XmlDocument.Load%2A> method brings the document into memory and has overloaded methods available to take data from each of the different formats.</span></span> <span data-ttu-id="ab840-106">È disponibile anche un metodo <xref:System.Xml.XmlDocument.LoadXml%2A>, con il quale è possibile leggere dati XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="ab840-106">There is also a <xref:System.Xml.XmlDocument.LoadXml%2A> method that reads XML from a string.</span></span>  
  
 <span data-ttu-id="ab840-107">I diversi metodi <xref:System.Xml.XmlDocument.Load%2A> determinano il tipo di nodi creati quando il DOM XML viene caricato.</span><span class="sxs-lookup"><span data-stu-id="ab840-107">Different <xref:System.Xml.XmlDocument.Load%2A> methods affect which nodes are created when the XML Document Object Model (DOM) is loaded.</span></span> <span data-ttu-id="ab840-108">Nella tabella seguente vengono elencate le differenze tra alcuni dei metodi <xref:System.Xml.XmlDocument.Load%2A> e i relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="ab840-108">The following table lists the differences between some of the <xref:System.Xml.XmlDocument.Load%2A> methods and topics that address them.</span></span>  
  
|<span data-ttu-id="ab840-109">Subject</span><span class="sxs-lookup"><span data-stu-id="ab840-109">Subject</span></span>|<span data-ttu-id="ab840-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="ab840-110">Topic</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="ab840-111">Creazione di nodi con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="ab840-111">Creation of white space nodes</span></span>|<span data-ttu-id="ab840-112">L'oggetto usato per caricare il DOM influisce sui nodi con spazi vuoti e spazi vuoti significativi generati nel DOM.</span><span class="sxs-lookup"><span data-stu-id="ab840-112">The object used to load the DOM has an affect on the white space and significant white space nodes generated in the DOM.</span></span> <span data-ttu-id="ab840-113">Per altre informazioni, vedere [Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="ab840-113">For more information, see [White Space and Significant White Space Handling when Loading the DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>|  
|<span data-ttu-id="ab840-114">Caricamento di XML da un nodo specifico o caricamento dell'intero documento XML</span><span class="sxs-lookup"><span data-stu-id="ab840-114">Loading XML starting from a specific node or loading the entire XML document</span></span>|<span data-ttu-id="ab840-115">Tramite il metodo <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> è possibile caricare i dati da un nodo specifico nel DOM.</span><span class="sxs-lookup"><span data-stu-id="ab840-115">Using the <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> method data can be loaded from a specific node into the DOM.</span></span> <span data-ttu-id="ab840-116">Per altre informazioni, vedere [Caricare i dati da un lettore](load-data-from-a-reader.md).</span><span class="sxs-lookup"><span data-stu-id="ab840-116">For more information, see [Load Data from a Reader](load-data-from-a-reader.md).</span></span>|  
|<span data-ttu-id="ab840-117">Convalida di XML durante il caricamento</span><span class="sxs-lookup"><span data-stu-id="ab840-117">Validating the XML as it is loaded</span></span>|<span data-ttu-id="ab840-118">È possibile convalidare i dati XML quando vengono caricati nel DOM.</span><span class="sxs-lookup"><span data-stu-id="ab840-118">The XML data loaded into the DOM can be validated as it is loaded.</span></span> <span data-ttu-id="ab840-119">Per eseguire l'operazione si usa un tipo <xref:System.Xml.XmlReader> per la convalida.</span><span class="sxs-lookup"><span data-stu-id="ab840-119">This is accomplished using a validating <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="ab840-120">Per altre informazioni sulla convalida di XML durante il caricamento, vedere [Convalida di un documento XML nel DOM](validating-an-xml-document-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="ab840-120">For more information about validating XML as it is loaded, see [Validating an XML Document in the DOM](validating-an-xml-document-in-the-dom.md).</span></span>|  
  
 <span data-ttu-id="ab840-121">Nell'esempio seguente viene illustrato il caricamento di dati XML con il metodo <xref:System.Xml.XmlDocument.LoadXml%2A> e il successivo salvataggio dei dati in un file di testo denominato `data.xml`.</span><span class="sxs-lookup"><span data-stu-id="ab840-121">The following example shows XML being loaded with the <xref:System.Xml.XmlDocument.LoadXml%2A> method and the data subsequently saved to a text file called `data.xml`.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab840-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab840-122">See also</span></span>

- [<span data-ttu-id="ab840-123">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="ab840-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
