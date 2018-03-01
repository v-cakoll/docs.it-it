---
title: "&#39; &lt;parola chiave&gt;&#39; è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a>&#39; &lt;parola chiave&gt;&#39; è valido solo all'interno di un metodo di istanza
Il `Me`, `MyClass`, e `MyBase` parole chiave fanno riferimento a istanze di classe specifico. Non possono essere utilizzati all'interno di un oggetto condiviso `Function` o `Sub` stored procedure.  
  
 **ID errore:** BC30043  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere la parola chiave dalla routine oppure rimuovere il `Shared` parola chiave dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Assegnazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
