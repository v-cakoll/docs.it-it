---
title: Valore letterale CDATA XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349430"
---
# <a name="xml-cdata-literal-visual-basic"></a>Valore letterale CDATA XML (Visual Basic)
Valore letterale che rappresenta un oggetto <xref:System.Xml.Linq.XCData>.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Parti  
 `<![CDATA[`  
 Obbligatoria. Indica l'inizio della sezione CDATA XML.  
  
 `content`  
 Obbligatoria. Contenuto di testo da visualizzare nella sezione CDATA XML.  
  
 `]]>`  
 Obbligatoria. Indica la fine della sezione.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Note  
 Le sezioni CDATA XML contengono testo non elaborato che deve essere incluso, ma non analizzato, con il codice XML che lo contiene. Una sezione CDATA XML può contenere testo. Sono inclusi i caratteri XML riservati. La sezione CDATA XML termina con la sequenza "]] >". Questo implica i seguenti punti:  
  
- Non è possibile usare un'espressione incorporata in un valore letterale CDATA XML perché i delimitatori di espressioni incorporati sono contenuti CDATA XML validi.  
  
- Le sezioni CDATA XML non possono essere annidate, perché `content` non può contenere il valore "]] >".  
  
 È possibile assegnare un valore letterale CDATA XML a una variabile o includerlo in un valore letterale elemento XML.  
  
> [!NOTE]
> Un valore letterale XML può estendersi su più righe, ma non utilizza caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale CDATA XML in una chiamata al costruttore di <xref:System.Xml.Linq.XCData.%23ctor%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una sezione CDATA che contiene il testo "può contenere un valore letterale \<tag XML >".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XCData>
- [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
