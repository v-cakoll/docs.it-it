---
title: Valore letterale istruzione di elaborazione XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: c589d3f4ac6bbb9aa9b2b8f2535888bddbf9c934
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958472"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Valore letterale istruzione di elaborazione XML (Visual Basic)
Valore letterale che <xref:System.Xml.Linq.XProcessingInstruction> rappresenta un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Parti  
 `<?`  
 Richiesto. Indica l'inizio del valore letterale di istruzione di elaborazione XML.  
  
 `piName`  
 Richiesto. Nome che indica l'applicazione di destinazione dell'istruzione di elaborazione. Impossibile iniziare con "XML" o "XML".  
  
 `piData`  
 facoltativo. Stringa che indica il modo in cui `piName` l'applicazione di destinazione deve elaborare il documento XML.  
  
 `?>`  
 Richiesto. Indica la fine dell'istruzione di elaborazione.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Note  
 I valori letterali di istruzione di elaborazione XML indicano in che modo le applicazioni devono elaborare un documento XML. Quando un'applicazione carica un documento XML, l'applicazione è in grado di controllare le istruzioni di elaborazione XML per determinare la modalità di elaborazione del documento. L'applicazione interpreta il significato di `piName` e. `piData`  
  
 Il valore letterale del documento XML utilizza una sintassi simile a quella dell'istruzione di elaborazione XML. Per altre informazioni, vedere [valore letterale documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
> L' `piName` elemento non può iniziare con le stringhe "XML" o "XML", perché la specifica XML 1,0 riserva tali identificatori.  
  
 È possibile assegnare un valore letterale di istruzione di elaborazione XML a una variabile o includerlo in un valore letterale di documento XML.  
  
> [!NOTE]
> Un valore letterale XML può estendersi su più righe senza dover utilizzare caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale di istruzione di elaborazione XML in <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> una chiamata al costruttore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata un'istruzione di elaborazione che identifica un foglio di stile per un documento XML.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XProcessingInstruction>
- [Valore letterale di documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
