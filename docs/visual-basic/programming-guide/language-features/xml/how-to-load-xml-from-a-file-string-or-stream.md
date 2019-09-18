---
title: 'Procedura: Caricare XML da un file, da una stringa o da un flusso (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: ba88ae19abc216a318d6c2069ab0846d5db8a346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054170"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="0c5c5-102">Procedura: Caricare XML da un file, da una stringa o da un flusso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c5c5-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="0c5c5-103">È possibile creare [valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) e popolarli con il contenuto di un'origine esterna, ad esempio un file, una stringa o un flusso usando diversi metodi.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="0c5c5-104">Questi metodi sono illustrati negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="0c5c5-105">Per caricare XML da un file</span><span class="sxs-lookup"><span data-stu-id="0c5c5-105">To load XML from a file</span></span>

<span data-ttu-id="0c5c5-106">Per popolare un valore letterale XML, <xref:System.Xml.Linq.XElement> ad <xref:System.Xml.Linq.XDocument> esempio un oggetto o da un file `Load` , usare il metodo.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="0c5c5-107">Questo metodo può assumere come input un percorso di file, un flusso di testo o un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="0c5c5-108">Nell'esempio di codice seguente viene illustrato l'utilizzo <xref:System.Xml.Linq.XDocument.Load%28System.String%29> del metodo per popolare <xref:System.Xml.Linq.XDocument> un oggetto con XML da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="0c5c5-109">Per caricare XML da una stringa</span><span class="sxs-lookup"><span data-stu-id="0c5c5-109">To load XML from a string</span></span>

<span data-ttu-id="0c5c5-110">Per popolare un valore letterale XML, <xref:System.Xml.Linq.XElement> ad <xref:System.Xml.Linq.XDocument> esempio un oggetto o da una stringa, è `Parse` possibile usare il metodo.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="0c5c5-111">Nell'esempio di codice seguente viene illustrato l'utilizzo <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> del metodo per popolare <xref:System.Xml.Linq.XDocument> un oggetto con XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="0c5c5-112">Per caricare XML da un flusso</span><span class="sxs-lookup"><span data-stu-id="0c5c5-112">To load XML from a stream</span></span>

<span data-ttu-id="0c5c5-113">Per popolare un valore letterale XML, <xref:System.Xml.Linq.XElement> ad <xref:System.Xml.Linq.XDocument> esempio un oggetto o da un flusso, è `Load` possibile <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> usare il metodo o.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="0c5c5-114">Nell'esempio di codice seguente viene illustrato l'utilizzo <xref:System.Xml.Linq.XNode.ReadFrom%2A> del metodo per popolare <xref:System.Xml.Linq.XDocument> un oggetto con XML da un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="0c5c5-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="0c5c5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5c5-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0c5c5-116">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="0c5c5-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="0c5c5-117">XML</span><span class="sxs-lookup"><span data-stu-id="0c5c5-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="0c5c5-118">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c5c5-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
