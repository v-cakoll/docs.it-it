---
title: Valore letterale istruzione di elaborazione XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d2df93a46d426358988b3ad7f3161c7ae0c7b9e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Valore letterale istruzione di elaborazione XML (Visual Basic)
Un valore letterale che rappresenta un <xref:System.Xml.Linq.XProcessingInstruction> oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Parti  
 `<?`  
 Obbligatorio. Indica l'inizio dell'istruzione di elaborazione XML letterale.  
  
 `piName`  
 Obbligatorio. Assegnare un nome che indica l'applicazione le destinazioni di istruzione di elaborazione. Non può iniziare con "xml" o "XML".  
  
 `piData`  
 Facoltativo. Stringa che indica come l'applicazione di destinazione da `piName` deve elaborare il documento XML.  
  
 `?>`  
 Obbligatorio. Indica la fine dell'istruzione di elaborazione.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Note  
 Valori letterali di istruzione di elaborazione XML indicano quali applicazioni devono elaborare un documento XML. Quando un'applicazione viene caricato un documento XML, l'applicazione può controllare le istruzioni di elaborazione per determinare come elaborare il documento XML. L'applicazione interpreta il significato di `piName` e `piData`.  
  
 Il valore letterale documento XML utilizza una sintassi simile a quello dell'istruzione di elaborazione XML. Per ulteriori informazioni, vedere [valore letterale di documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  Il `piName` elemento non può iniziare con le stringhe "xml" o "XML", perché la specifica XML 1.0 tali identificatori sono riservati.  
  
 È possibile assegnare una valore letterale istruzione di elaborazione di XML a una variabile o includerlo in un valore letterale documento XML.  
  
> [!NOTE]
>  Un valore letterale XML può estendersi su più righe senza caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale istruzione di elaborazione di XML in una chiamata al <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> costruttore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un'istruzione di elaborazione che identifica un foglio di stile per un documento XML.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [Valore letterale di documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
