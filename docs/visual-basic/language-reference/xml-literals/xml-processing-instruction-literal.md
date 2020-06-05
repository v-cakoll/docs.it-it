---
title: Valore letterale di istruzione di elaborazione XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 9bd1781e01bc4cbf1ce5da8c454ab2f5a679aead
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400176"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Valore letterale istruzione di elaborazione XML (Visual Basic)
Valore letterale che rappresenta un <xref:System.Xml.Linq.XProcessingInstruction> oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Parti  
 `<?`  
 Obbligatorio. Indica l'inizio del valore letterale di istruzione di elaborazione XML.  
  
 `piName`  
 Obbligatorio. Nome che indica l'applicazione di destinazione dell'istruzione di elaborazione. Impossibile iniziare con "XML" o "XML".  
  
 `piData`  
 Facoltativa. Stringa che indica il modo in cui l'applicazione di destinazione `piName` deve elaborare il documento XML.  
  
 `?>`  
 Obbligatorio. Indica la fine dell'istruzione di elaborazione.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Commenti  
 I valori letterali di istruzione di elaborazione XML indicano in che modo le applicazioni devono elaborare un documento XML. Quando un'applicazione carica un documento XML, l'applicazione è in grado di controllare le istruzioni di elaborazione XML per determinare la modalità di elaborazione del documento. L'applicazione interpreta il significato di `piName` e `piData` .  
  
 Il valore letterale del documento XML utilizza una sintassi simile a quella dell'istruzione di elaborazione XML. Per altre informazioni, vedere [valore letterale documento XML](xml-document-literal.md).  
  
> [!NOTE]
> L' `piName` elemento non può iniziare con le stringhe "XML" o "XML", perché la specifica xml 1,0 riserva tali identificatori.  
  
 È possibile assegnare un valore letterale di istruzione di elaborazione XML a una variabile o includerlo in un valore letterale di documento XML.  
  
> [!NOTE]
> Un valore letterale XML può estendersi su più righe senza dover utilizzare caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale di istruzione di elaborazione XML in una chiamata al <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> costruttore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata un'istruzione di elaborazione che identifica un foglio di stile per un documento XML.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XProcessingInstruction>
- [Valore letterale di documento XML](xml-document-literal.md)
- [Valori letterali XML](index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
