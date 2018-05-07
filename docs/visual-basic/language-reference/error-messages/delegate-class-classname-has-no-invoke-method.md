---
title: La classe delegata &#39; &lt;classname&gt; &#39; non contiene alcun metodo Invoke, un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>La classe delegata &#39; &lt;classname&gt; &#39; non contiene alcun metodo Invoke, un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
Una chiamata a `Invoke` tramite un delegato non è riuscita perché `Invoke` non è implementata nella classe delegata.  
  
 **ID errore:** BC30220  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che sia stata creata un'istanza della classe delegato con un `Dim` istruzione e una stored procedure è stata assegnata all'istanza del delegato con il `AddressOf` operatore.  
  
2.  Individuare il codice che implementa la classe delegata e assicurarsi che implementa il `Invoke` stored procedure.  
  
## <a name="see-also"></a>Vedere anche  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
