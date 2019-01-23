---
title: '&#39;Personalizzato&#39; modificatore non valido negli eventi dichiarati senza tipi delegati espliciti'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c909973ef1c00cb01179b0e5527dfecd6f41e577
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574781"
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;Personalizzato&#39; modificatore non valido negli eventi dichiarati senza tipi delegati espliciti
A differenza di un evento non personalizzato, un `Custom Event` dichiarazione richiede un `As` clausola dopo il nome dell'evento che specifichi esplicitamente il tipo di delegato per l'evento.  
  
 Gli eventi personalizzati non possono essere definite con un `As` clausola ed esplicita tipo delegato o con un parametro di elenco immediatamente dopo il nome dell'evento.  
  
 **ID errore:** BC31122  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.  
  
     Ad esempio, se il `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, quindi il delegato corrispondente sarebbe il seguente.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Sostituire l'elenco di parametri dell'evento personalizzato con un `As` clausola che specifica il tipo delegato.  
  
     Continuando con l'esempio `Custom Event` dichiarazione potrebbe essere riscritto come segue.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene dichiarata una `Custom Event` e specifica la necessaria `As` clausola con un tipo delegato.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
