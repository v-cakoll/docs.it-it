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
ms.openlocfilehash: b9cc830d27625f192d8f5e059bd3783d05d8ba3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400228"
---
# <a name="xml-cdata-literal-visual-basic"></a>Valore letterale CDATA XML (Visual Basic)
Valore letterale che rappresenta un <xref:System.Xml.Linq.XCData> oggetto.  
  
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
  
## <a name="remarks"></a>Commenti  
 Le sezioni CDATA XML contengono testo non elaborato che deve essere incluso, ma non analizzato, con il codice XML che lo contiene. Una sezione CDATA XML può contenere testo. Sono inclusi i caratteri XML riservati. La sezione CDATA XML termina con la sequenza "]] >". Questo implica i seguenti punti:  
  
- Non è possibile usare un'espressione incorporata in un valore letterale CDATA XML perché i delimitatori di espressioni incorporati sono contenuti CDATA XML validi.  
  
- Le sezioni CDATA XML non possono essere annidate, perché `content` non possono contenere il valore "]] >".  
  
 È possibile assegnare un valore letterale CDATA XML a una variabile o includerlo in un valore letterale elemento XML.  
  
> [!NOTE]
> Un valore letterale XML può estendersi su più righe, ma non utilizza caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale CDATA XML in una chiamata al <xref:System.Xml.Linq.XCData.%23ctor%2A> costruttore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una sezione CDATA che contiene il testo "può contenere \<XML> tag letterali".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XCData>
- [Valore letterale di elemento XML](xml-element-literal.md)
- [Valori letterali XML](index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
