---
title: <type1>'<typename>' deve implementare '<methodname>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 90d2b6d70390bfb732af4a5868c935de61d18f94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408498"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1>'\<typename>' deve implementare '\<methodname>' per l'interfaccia '\<interfacename>'
Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine definita dall'interfaccia. È necessario implementare tutti i membri dell'interfaccia.  
  
 **ID errore:** BC30149  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare una routine con lo stesso nome e la stessa firma definiti nell'interfaccia. Assicurarsi di includere almeno l' `End Function` `End Sub` istruzione o.  
  
2. Aggiungere una `Implements` clausola alla fine dell' `Function` `Sub` istruzione o. Ad esempio:  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../statements/implements-statement.md)
- [Interfacce](../../programming-guide/language-features/interfaces/index.md)
