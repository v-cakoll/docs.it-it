---
title: <type1>«<typename>'deve implementare'<membername>'per l'interfaccia'<interfacename>»
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 86b0d46e0e27b2fd8d1fccb37f4a3c45e95f5f63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295328"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1 >'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'
'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'. Implementazione della proprietà deve contenere corrispondenti 'ReadOnly' o 'WriteOnly' identificatori.  
  
 Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine, proprietà o eventi definiti dall'interfaccia. Ogni membro dell'interfaccia deve essere implementata.  
  
 **ID errore:** BC30154  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare un membro con lo stesso nome e firma, come definito nell'interfaccia. Assicurarsi di includere almeno le `End Function`, `End Sub`, o `End Property` istruzione.  
  
2. Aggiungere un `Implements` alla fine della clausola il `Function`, `Sub`, `Property`, o `Event` istruzione. Ad esempio:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` viene usato in modo analogo la definizione dell'interfaccia.  
  
4. Quando si implementa una proprietà, dichiarare `Get` e `Set` procedure, come appropriato.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
