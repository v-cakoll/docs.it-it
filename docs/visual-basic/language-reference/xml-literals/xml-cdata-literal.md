---
title: Valore letterale CDATA XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 999531d8146748fe491255663f0d2d17d056bcd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603834"
---
# <a name="xml-cdata-literal-visual-basic"></a>Valore letterale CDATA XML (Visual Basic)
Un valore letterale che rappresenta un <xref:System.Xml.Linq.XCData> oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Parti  
 `<![CDATA[`  
 Obbligatorio. Indica l'inizio della sezione CDATA XML.  
  
 `content`  
 Obbligatorio. Contenuto di testo da visualizzare nella sezione CDATA XML.  
  
 `]]>`  
 Obbligatorio. Indica la fine della sezione.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Note  
 Le sezioni CDATA XML contengono testo non elaborato che deve essere inclusa, ma non analizzato, con il codice XML che lo contiene. Una sezione CDATA XML può contenere qualsiasi testo. Sono inclusi caratteri XML riservati. La sezione CDATA XML termina con la sequenza "]] >". Ciò implica quanto segue:  
  
-   È possibile utilizzare un'espressione incorporata in un valore letterale CDATA XML perché i delimitatori di espressione incorporata sono contenuti CDATA XML validi.  
  
-   Le sezioni CDATA XML non possono essere annidate, perché `content` non può contenere il valore "]] >".  
  
 È possibile assegnare un valore letterale CDATA XML a una variabile o includerlo in un valore letterale elemento XML.  
  
> [!NOTE]
>  Un valore letterale XML può estendersi su più righe ma non utilizza caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale CDATA XML a una chiamata al <xref:System.Xml.Linq.XCData.%23ctor%2A> costruttore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una sezione CDATA che contiene il testo "può contenere un valore letterale \<XML > tag".  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XCData>  
 [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
