---
title: "&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;membername&gt; &#39; per l'interfaccia di &#39; &lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 0f93bd137bdc21268cbca139ae739843561350ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596746"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;membername&gt; &#39; per l'interfaccia di &#39; &lt;interfacename&gt;&#39;
'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'. Implementazione della proprietà deve contenere corrispondenti 'ReadOnly' o 'WriteOnly' identificatori.  
  
 Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine, proprietà o evento definito dall'interfaccia. Ogni membro dell'interfaccia deve essere implementata.  
  
 **ID errore:** BC30154  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiarare un membro con lo stesso nome e firma, come definito nell'interfaccia. Assicurarsi di includere almeno le `End Function`, `End Sub`, o `End Property` istruzione.  
  
2.  Aggiungere un `Implements` clausola alla fine del `Function`, `Sub`, `Property`, o `Event` istruzione. Ad esempio:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` viene utilizzato in modo analogo la definizione dell'interfaccia.  
  
4.  Quando si implementa una proprietà, dichiarare `Get` e `Set` procedure, come appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
