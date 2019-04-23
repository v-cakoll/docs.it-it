---
title: "La dichiarazione dell'operatore deve essere uno di: +,-, *,-, -, ^, &amp;, Like, Mod e, Or, Xor, non, <<>>,, <>, <, < =, >, > =, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 4283547109ec312cc4fe07a054bbb8db3bff660f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299189"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>La dichiarazione dell'operatore deve essere uno di: +,-, *,\,/, ^, &amp;, Like, Mod e, Or, Xor, non \< \<, >>...
È possibile dichiarare solo gli operatori che sono idoneo per l'overload. Nella tabella seguente vengono elencati gli operatori che è possibile dichiarare.  
  
|Tipo|Operatori|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversione (unario)|`CType`|  
  
 Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.  
  
 **ID errore:** BC33000  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Selezionare un operatore dal set di operatori che supportano l'overload.  
  
2. Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
