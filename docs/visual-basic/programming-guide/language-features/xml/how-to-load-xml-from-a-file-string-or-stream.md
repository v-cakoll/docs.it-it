---
title: 'Procedura: Caricare il documento XML da un File, stringa o Stream (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 36a7f23eed7f47e8c33958f96e8e3694fb958d11
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977695"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="f4b9f-102">Procedura: Caricare il documento XML da un File, stringa o Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4b9f-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="f4b9f-103">È possibile creare [valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) e popolarli con i contenuti da un'origine esterna, ad esempio un file, una stringa o un flusso usando diversi metodi.</span><span class="sxs-lookup"><span data-stu-id="f4b9f-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="f4b9f-104">Questi metodi sono illustrati negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f4b9f-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="f4b9f-105">Caricare il documento XML da un file</span><span class="sxs-lookup"><span data-stu-id="f4b9f-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="f4b9f-106">Per popolare un valore letterale, ad esempio XML un' <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XDocument> oggetto da un file, usare il `Load` (metodo).</span><span class="sxs-lookup"><span data-stu-id="f4b9f-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="f4b9f-107">Questo metodo può accettare un percorso del file, flusso di testo o flusso XML come input.</span><span class="sxs-lookup"><span data-stu-id="f4b9f-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="f4b9f-108">Esempio di codice seguente viene illustrato l'utilizzo dei <xref:System.Xml.Linq.XDocument.Load%28System.String%29> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con il codice XML da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="f4b9f-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="f4b9f-109">Caricare il documento XML da una stringa</span><span class="sxs-lookup"><span data-stu-id="f4b9f-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="f4b9f-110">Per popolare un valore letterale, ad esempio XML un' <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XDocument> dell'oggetto da una stringa, è possibile usare il `Parse` (metodo).</span><span class="sxs-lookup"><span data-stu-id="f4b9f-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="f4b9f-111">Esempio di codice seguente viene illustrato l'utilizzo dei <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con il codice XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="f4b9f-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="f4b9f-112">Caricare il documento XML da un flusso</span><span class="sxs-lookup"><span data-stu-id="f4b9f-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="f4b9f-113">Per popolare un valore letterale, ad esempio XML un' <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> dell'oggetto da un flusso, è possibile utilizzare il `Load` metodo o il <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f4b9f-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f4b9f-114">Esempio di codice seguente viene illustrato l'utilizzo dei <xref:System.Xml.Linq.XNode.ReadFrom%2A> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con il codice XML da un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="f4b9f-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="f4b9f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4b9f-115">See also</span></span>
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f4b9f-116">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="f4b9f-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="f4b9f-117">XML</span><span class="sxs-lookup"><span data-stu-id="f4b9f-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f4b9f-118">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f4b9f-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
