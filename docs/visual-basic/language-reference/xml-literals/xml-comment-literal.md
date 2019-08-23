---
title: Valore letterale di commento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 91369392f33f2a86a7a4cb5ffb3faa668c113348
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965405"
---
# <a name="xml-comment-literal-visual-basic"></a>Valore letterale di commento XML (Visual Basic)
Valore letterale che <xref:System.Xml.Linq.XComment> rappresenta un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`<!--`|Richiesto. Indica l'inizio del commento XML.|  
|`content`|Richiesto. Testo da visualizzare nel commento XML. Non può contenere una serie di due trattini (--) o terminare con un trattino adiacente al tag di chiusura.|  
|`-->`|Richiesto. Indica la fine del commento XML.|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Note  
 I valori letterali del commento XML non contengono contenuto del documento; contengono informazioni sul documento. La sezione del commento XML termina con la sequenza "-->". Questo implica i seguenti punti:  
  
- Non è possibile usare un'espressione incorporata in un valore letterale di commento XML perché i delimitatori di espressioni incorporati sono contenuti di commenti XML validi.  
  
- Le sezioni di commento XML non possono essere `content` annidate, perché non possono contenere il valore "-->".  
  
 È possibile assegnare un valore letterale di commento XML a una variabile oppure è possibile includerlo in un valore letterale elemento XML.  
  
> [!NOTE]
> Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga. Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale del commento XML in una <xref:System.Xml.Linq.XComment.%23ctor%2A> chiamata al costruttore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un commento XML che contiene il testo "questo è un commento".  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XComment>
- [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
