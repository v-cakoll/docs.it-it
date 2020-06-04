---
title: "La dichiarazione dell'operatore deve essere una delle seguenti: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, false"
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 3fb2cf392611e5ca83818e3bf173513be031085d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409335"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>La dichiarazione dell'operatore deve essere una delle seguenti: +,-, *, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...
È possibile dichiarare solo un operatore idoneo per l'overload. Nella tabella seguente sono elencati gli operatori che è possibile dichiarare.  
  
|Type|Operatori|  
|----------|---------------|  
|Unaria|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversione (unario)|`CType`|  
  
 Si noti che l'operatore `=` nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.  
  
 **ID errore:** BC33000  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Selezionare un operatore dal set di operatori che supportano l'overload.  
  
2. Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.  
  
## <a name="see-also"></a>Vedere anche

- [Operator Statement](../statements/operator-statement.md)
- [Routine di operatore](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Istruzione Function](../statements/function-statement.md)
