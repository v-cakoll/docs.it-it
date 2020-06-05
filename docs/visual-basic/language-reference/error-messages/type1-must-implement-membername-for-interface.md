---
title: <type1>'<typename>' deve implementare '<membername>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 4ffe18e11c388a8c69ef0592bde1b78f5b219680
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386854"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1>'\<typename>' deve implementare '\<membername>' per l'interfaccia '\<interfacename>'
' \<typename> ' deve implementare '' \<membername> per l'interfaccia ' \<interfacename> '. La proprietà di implementazione deve avere identificatori ' ReadOnly '/' WriteOnly ' corrispondenti.  
  
 Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine, una proprietà o un evento definito dall'interfaccia. È necessario implementare tutti i membri dell'interfaccia.  
  
 **ID errore:** BC30154  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare un membro con lo stesso nome e la stessa firma definiti nell'interfaccia. Assicurarsi di includere almeno l' `End Function` `End Sub` istruzione, o `End Property` .  
  
2. Aggiungere una `Implements` clausola alla fine dell' `Function` `Sub` istruzione,, `Property` o `Event` . Ad esempio:  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` venga usato nello stesso modo in cui si trova nella definizione dell'interfaccia.  
  
4. Quando si implementa una proprietà, `Get` dichiarare `Set` le routine e, a seconda delle esigenze.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../statements/implements-statement.md)
- [Interfacce](../../programming-guide/language-features/interfaces/index.md)
