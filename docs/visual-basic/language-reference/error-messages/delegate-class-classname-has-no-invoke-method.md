---
title: La classe delegata '<classname>' non contiene un metodo Invoke. Un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409712"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>La classe delegata '\<classname>' non contiene un metodo Invoke. Un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
Una chiamata a `Invoke` tramite un delegato non è riuscita perché `Invoke` non è implementato nella classe delegata.  
  
 **ID errore:** BC30220  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Assicurarsi che un'istanza della classe delegata sia stata creata con un' `Dim` istruzione e che una routine sia stata assegnata all'istanza del delegato con l' `AddressOf` operatore.  
  
2. Individuare il codice che implementa la classe delegata e assicurarsi che implementi la `Invoke` procedura.  
  
## <a name="see-also"></a>Vedere anche

- [Delegati](../../programming-guide/language-features/delegates/index.md)
- [Istruzione Delegate](../statements/delegate-statement.md)
- [Operatore AddressOf](../operators/addressof-operator.md)
- [Istruzione Dim](../statements/dim-statement.md)
