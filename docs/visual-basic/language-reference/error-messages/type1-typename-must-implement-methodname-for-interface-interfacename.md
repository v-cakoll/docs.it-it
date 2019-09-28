---
title: <type1>'<typename>' deve implementare '<methodname>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591587"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1 >' \<typename >' deve implementare ' \<methodname >' per l'interfaccia ' \<interfacename >'
Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine definita dall'interfaccia. È necessario implementare tutti i membri dell'interfaccia.  
  
 **ID errore:** BC30149  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare una routine con lo stesso nome e la stessa firma definiti nell'interfaccia. Assicurarsi di includere almeno l'istruzione `End Function` o `End Sub`.  
  
2. Aggiungere una clausola `Implements` alla fine dell'istruzione `Function` o `Sub`. Esempio:  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
