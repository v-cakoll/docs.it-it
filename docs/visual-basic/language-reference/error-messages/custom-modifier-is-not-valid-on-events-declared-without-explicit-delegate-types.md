---
title: '&#39;Personalizzato&#39; modificatore non valido negli eventi dichiarati senza tipi delegati espliciti'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;Personalizzato&#39; modificatore non valido negli eventi dichiarati senza tipi delegati espliciti
A differenza di un evento non personalizzato, un `Custom Event` dichiarazione richiede un `As` clausola dopo il nome di evento che specifica in modo esplicito il tipo di delegato per l'evento.  
  
 Gli eventi non personalizzati possono essere definiti con un `As` clausola esplicita tipo delegato e con un parametro elenco immediatamente dopo il nome dell'evento.  
  
 **ID errore:** BC31122  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.  
  
     Ad esempio, se il `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, quindi il delegato corrispondente potrebbe essere la seguente.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Sostituire l'elenco di parametri dell'evento personalizzato con un `As` clausola che specifica il tipo delegato.  
  
     Continuando con l'esempio, `Custom Event` dichiarazione potrebbe essere riscritto come segue.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Esempio  
 In questo esempio dichiara un `Custom Event` e specifica la `As` clausola con un tipo delegato.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
