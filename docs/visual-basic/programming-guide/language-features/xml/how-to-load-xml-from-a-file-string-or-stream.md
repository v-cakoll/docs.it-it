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
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Procedura: caricare XML da un file, da una stringa o da un flusso (Visual Basic)

È possibile creare [valori letterali XML](../../../language-reference/xml-literals/index.md) e popolarli con il contenuto di un'origine esterna, ad esempio un file, una stringa o un flusso usando diversi metodi. Questi metodi sono illustrati negli esempi seguenti.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Per caricare XML da un file

Per popolare un valore letterale XML, ad esempio un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetto o da un file, usare il `Load` metodo. Questo metodo può assumere come input un percorso di file, un flusso di testo o un flusso XML.

Nell'esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XDocument.Load%28System.String%29> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con XML da un file di testo.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Per caricare XML da una stringa

Per popolare un valore letterale XML, ad esempio un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetto o da una stringa, è possibile usare il `Parse` metodo.

Nell'esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con XML da una stringa.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Per caricare XML da un flusso

Per popolare un valore letterale XML, ad esempio un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetto o da un flusso, è possibile usare il `Load` metodo o <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> .

Nell'esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XNode.ReadFrom%2A> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con XML da un flusso XML.

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [Valori letterali XML](../../../language-reference/xml-literals/index.md)
- [XML](index.md)
- [Modifica di XML in Visual Basic](manipulating-xml.md)
