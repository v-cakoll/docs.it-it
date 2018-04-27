---
title: '&#39;Come qualsiasi&#39; non è supportato in &#39;Declare&#39; istruzioni'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8146e339ac5cb005b99c9a1e02f1cd248c4558b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;Come qualsiasi&#39; non è supportato in &#39;Declare&#39; istruzioni
Il `Any` tipo di dati è stato utilizzato con `Declare` istruzioni in Visual Basic 6.0 e versioni precedenti per consentire l'utilizzo di argomenti che può contenere qualsiasi tipo di dati. Visual Basic supporta l'overload, tuttavia e la imposta come in questo caso il `Any` del tipo di dati obsoleta.  
  
 **ID errore:** BC30828  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiarare i parametri del tipo specifico che si desidera utilizzare. Per esempio.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Utilizzare il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo per specificare `As Any` quando `Void*` è prevista dalla routine chiamata.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Creazione di prototipi nel codice gestito](../../../framework/interop/creating-prototypes-in-managed-code.md)
