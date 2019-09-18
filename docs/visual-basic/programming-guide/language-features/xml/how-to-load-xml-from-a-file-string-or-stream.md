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
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Procedura: Caricare XML da un file, da una stringa o da un flusso (Visual Basic)

È possibile creare [valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) e popolarli con il contenuto di un'origine esterna, ad esempio un file, una stringa o un flusso usando diversi metodi. Questi metodi sono illustrati negli esempi seguenti.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Per caricare XML da un file

Per popolare un valore letterale XML, <xref:System.Xml.Linq.XElement> ad <xref:System.Xml.Linq.XDocument> esempio un oggetto o da un file `Load` , usare il metodo. Questo metodo può assumere come input un percorso di file, un flusso di testo o un flusso XML.

Nell'esempio di codice seguente viene illustrato l'utilizzo <xref:System.Xml.Linq.XDocument.Load%28System.String%29> del metodo per popolare <xref:System.Xml.Linq.XDocument> un oggetto con XML da un file di testo.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Per caricare XML da una stringa

Per popolare un valore letterale XML, <xref:System.Xml.Linq.XElement> ad <xref:System.Xml.Linq.XDocument> esempio un oggetto o da una stringa, è `Parse` possibile usare il metodo.

Nell'esempio di codice seguente viene illustrato l'utilizzo <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> del metodo per popolare <xref:System.Xml.Linq.XDocument> un oggetto con XML da una stringa.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Per caricare XML da un flusso

Per popolare un valore letterale XML, <xref:System.Xml.Linq.XElement> ad <xref:System.Xml.Linq.XDocument> esempio un oggetto o da un flusso, è `Load` possibile <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> usare il metodo o.

Nell'esempio di codice seguente viene illustrato l'utilizzo <xref:System.Xml.Linq.XNode.ReadFrom%2A> del metodo per popolare <xref:System.Xml.Linq.XDocument> un oggetto con XML da un flusso XML.

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
