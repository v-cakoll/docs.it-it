---
title: "&#39; Set &#39; funzione di accesso della proprietà &#39; &lt;propertyname&gt;&#39; non è accessibile"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9256a09b719ad3890e1d7c2cc23ffb0d40eec62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39; Set &#39; funzione di accesso della proprietà &#39; &lt;propertyname&gt;&#39; non è accessibile
Un'istruzione tenta di archiviare il valore di una proprietà quando dispone di accesso per la proprietà `Set` stored procedure.  
  
 Se il [istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md) è contrassegnata con un accesso più restrittivo livello relativa [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md), un tentativo di impostare il valore della proprietà potrebbe non riuscire nei casi seguenti:  
  
-   Il `Set` è contrassegnata [privata](../../../visual-basic/language-reference/modifiers/private.md) e il codice chiamante è di fuori della classe o struttura in cui la proprietà è definita.  
  
-   Il `Set` è contrassegnata [Protected](../../../visual-basic/language-reference/modifiers/protected.md) e il codice chiamante non nella classe o struttura in cui la proprietà è definita, né in una classe derivata.  
  
-   Il `Set` è contrassegnata [Friend](../../../visual-basic/language-reference/modifiers/friend.md) e il codice chiamante non è presente nello stesso assembly in cui la proprietà è definita.  
  
 **ID errore:** BC31102  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se si dispone di controllo del codice sorgente che definisce la proprietà, si consideri la dichiarazione di `Set` procedure con lo stesso livello di accesso della proprietà stessa.  
  
-   Se non si dispone del controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Set` procedure livello di accesso più la proprietà stessa, provare a spostare l'istruzione che imposta il valore della proprietà a un'area del codice che dispone di un accesso migliore per il proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
