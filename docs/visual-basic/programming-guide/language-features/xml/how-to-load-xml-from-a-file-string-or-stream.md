---
title: 'Procedura: caricare XML da un file, da una stringa o da un flusso'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7f2a961ebb7ecd4fc0512e141b4a437be87bec0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392288"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="97790-102">Procedura: caricare XML da un file, da una stringa o da un flusso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97790-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="97790-103">È possibile creare [valori letterali XML](../../../language-reference/xml-literals/index.md) e popolarli con il contenuto di un'origine esterna, ad esempio un file, una stringa o un flusso usando diversi metodi.</span><span class="sxs-lookup"><span data-stu-id="97790-103">You can create [XML Literals](../../../language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="97790-104">Questi metodi sono illustrati negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="97790-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="97790-105">Per caricare XML da un file</span><span class="sxs-lookup"><span data-stu-id="97790-105">To load XML from a file</span></span>

<span data-ttu-id="97790-106">Per popolare un valore letterale XML, ad esempio un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetto o da un file, usare il `Load` metodo.</span><span class="sxs-lookup"><span data-stu-id="97790-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="97790-107">Questo metodo può assumere come input un percorso di file, un flusso di testo o un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="97790-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="97790-108">Nell'esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XDocument.Load%28System.String%29> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con XML da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="97790-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="97790-109">Per caricare XML da una stringa</span><span class="sxs-lookup"><span data-stu-id="97790-109">To load XML from a string</span></span>

<span data-ttu-id="97790-110">Per popolare un valore letterale XML, ad esempio un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetto o da una stringa, è possibile usare il `Parse` metodo.</span><span class="sxs-lookup"><span data-stu-id="97790-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="97790-111">Nell'esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="97790-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="97790-112">Per caricare XML da un flusso</span><span class="sxs-lookup"><span data-stu-id="97790-112">To load XML from a stream</span></span>

<span data-ttu-id="97790-113">Per popolare un valore letterale XML, ad esempio un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetto o da un flusso, è possibile usare il `Load` metodo o <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="97790-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="97790-114">Nell'esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XNode.ReadFrom%2A> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con XML da un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="97790-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="97790-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97790-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="97790-116">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="97790-116">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="97790-117">XML</span><span class="sxs-lookup"><span data-stu-id="97790-117">XML</span></span>](index.md)
- [<span data-ttu-id="97790-118">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97790-118">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
