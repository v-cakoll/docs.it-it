---
title: La classe delegata '<classname>' non contiene un metodo Invoke. Un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 3fe164d868ee7bde0e687e1d592f4d5a17565aea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321302"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Classe delegata\<NomeClasse >' non contiene alcun metodo Invoke, in modo che un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
Una chiamata a `Invoke` attraverso un delegato non è riuscita perché `Invoke` non è implementato nella classe delegata.  
  
 **ID errore:** BC30220  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che sia stata creata un'istanza della classe delegata con un `Dim` istruzione e che una routine è stata assegnata all'istanza del delegato con il `AddressOf` operatore.  
  
2. Individuare il codice che implementa la classe delegate e assicurarsi che implementa il `Invoke` procedure.  
  
## <a name="see-also"></a>Vedere anche

- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
