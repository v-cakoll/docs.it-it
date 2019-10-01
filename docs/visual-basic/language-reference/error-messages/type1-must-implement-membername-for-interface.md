---
title: <type1>'<typename>' deve implementare '<membername>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696886"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1 >' \<typename >' deve implementare ' \<membername >' per l'interfaccia ' \<interfacename >'
' \<typename >' deve implementare ' \<membername >' per l'interfaccia ' \<interfacename >'. La proprietà di implementazione deve avere identificatori ' ReadOnly '/' WriteOnly ' corrispondenti.  
  
 Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine, una proprietà o un evento definito dall'interfaccia. È necessario implementare tutti i membri dell'interfaccia.  
  
 **ID errore:** BC30154  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare un membro con lo stesso nome e la stessa firma definiti nell'interfaccia. Assicurarsi di includere almeno l'istruzione `End Function`, `End Sub` o `End Property`.  
  
2. Aggiungere una clausola `Implements` alla fine dell'istruzione `Function`, `Sub`, `Property` o `Event`. Esempio:  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` venga usato nello stesso modo in cui si trova nella definizione dell'interfaccia.  
  
4. Quando si implementa una proprietà, dichiarare le procedure `Get` e `Set`, a seconda delle esigenze.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
