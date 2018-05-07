---
title: "&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;NomeMetodo&gt; &#39; per l'interfaccia di &#39; &lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: daeeab853f6a7f582542fa15ffc09ce749731d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;NomeMetodo&gt; &#39; per l'interfaccia di &#39; &lt;interfacename&gt;&#39;
Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia. Ogni membro dell'interfaccia deve essere implementata.  
  
 **ID errore:** BC30149  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiarare una routine con lo stesso nome e firma, come definito nell'interfaccia. Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.  
  
2.  Aggiungere un `Implements` clausola alla fine del `Function` o `Sub` istruzione. Ad esempio:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
