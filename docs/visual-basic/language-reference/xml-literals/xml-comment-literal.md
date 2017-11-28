---
title: Valore letterale di commento XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36be34ac22cfe926a2eea946f5e4c4eb534de696
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-literal-visual-basic"></a>Valore letterale di commento XML (Visual Basic)
Un valore letterale che rappresenta un <xref:System.Xml.Linq.XComment> oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`<!--`|Obbligatorio. Indica l'inizio del commento XML.|  
|`content`|Obbligatorio. Testo da visualizzare nel commento XML. Non può contenere una serie di due trattini (-) o terminare con un trattino adiacente al tag di chiusura.|  
|`-->`|Obbligatorio. Indica la fine del commento XML.|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Note  
 Valori letterali di commento XML non contengono il contenuto del documento; contengono informazioni sul documento. La sezione di commento XML termina con la sequenza "-->". Ciò implica quanto segue:  
  
-   È possibile utilizzare un'espressione incorporata in un valore letterale di commento XML perché i delimitatori di espressione incorporata sono contenuti di commento XML validi.  
  
-   Le sezioni di commento XML non possono essere annidate, perché `content` non può contenere il valore "-->".  
  
 È possibile assegnare un valore letterale del commento XML a una variabile oppure è possibile includerlo in un valore letterale elemento XML.  
  
> [!NOTE]
>  Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga. Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programma.  
  
 Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte il valore letterale del commento XML a una chiamata al <xref:System.Xml.Linq.XComment.%23ctor%2A> costruttore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un commento XML che contiene il testo "This is a un commento".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XComment>  
 [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
