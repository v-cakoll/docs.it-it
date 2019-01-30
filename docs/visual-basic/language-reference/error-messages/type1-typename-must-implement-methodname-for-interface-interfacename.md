---
title: <type1>'<typename>' deve implementare '<methodname>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c5dd7c6889a3fb5344142ee9914f98e8922d748b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264434"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1 >'\<nomeTipo >' deve implementare '\<NomeMetodo >' per l'interfaccia '\<nomeinterfaccia >'
Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia. Ogni membro dell'interfaccia deve essere implementata.  
  
 **ID errore:** BC30149  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiara una routine con lo stesso nome e firma, come definito nell'interfaccia. Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.  
  
2.  Aggiungere un `Implements` alla fine della clausola il `Function` o `Sub` istruzione. Ad esempio:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
