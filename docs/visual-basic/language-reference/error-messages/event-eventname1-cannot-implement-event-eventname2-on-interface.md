---
title: "Evento &#39; &lt;nomeevento1&gt;&#39; non può implementare l'evento &#39;&lt; nomeevento2&gt;&#39; interfaccia &#39;&lt; interfaccia&gt;&#39; perché i relativi tipi delegati &#39;&lt; Delegate1&gt;&#39; e &#39;&lt; delegate2&gt;&#39; non corrispondono"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords: BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0fcbbf8a6e23270e4dcbf9d813c773e1522a92a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a>Evento &#39; &lt;nomeevento1&gt;&#39; non può implementare l'evento &#39;&lt; nomeevento2&gt;&#39; interfaccia &#39;&lt; interfaccia&gt;&#39; perché i relativi tipi delegati &#39;&lt; Delegate1&gt;&#39; e &#39;&lt; delegate2&gt;&#39; non corrispondono
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]non è possibile implementare un evento perché il tipo delegato dell'evento non corrisponde al tipo di delegato dell'evento nell'interfaccia. Questo errore può insorgere quando si definiscono più eventi in un'interfaccia e si prova a implementarli assieme con lo stesso evento. Un evento può implementare due o più eventi solo se tutti gli eventi implementati vengono dichiarati usando la sintassi `As` e se tutti specificano lo stesso tipo delegato.  
  
 **ID errore:** BC31423  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Implementare gli eventi separatamente.  
  
     -oppure-  
  
-   Definire gli eventi nell'interfaccia utilizzando il `As` sintassi e specificare lo stesso tipo delegato.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
