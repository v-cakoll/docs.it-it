---
title: 'Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646926"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)
Quando è importante che un gestore eventi non bloccano i gestori eventi successivi, esistono diverse circostanze. Eventi personalizzati consentono di chiamare i relativi gestori eventi in modo asincrono l'evento.  
  
 Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi. Ciò significa che se un gestore richiede molto tempo, si blocca altri gestori fino al completamento. (Gestori eventi ben progettati non devono mai eseguire operazioni di lunga durate o di blocco.)  
  
 Anziché utilizzare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile utilizzare un evento personalizzato per eseguire i gestori eventi in modo asincrono.  
  
## <a name="example"></a>Esempio  
 In questo esempio, il `AddHandler` accessor aggiunge il delegato per ogni gestore del `Click` evento da un <xref:System.Collections.ArrayList> archiviati nel `EventHandlerList` campo.  
  
 Quando il codice genera il `Click` evento, il `RaiseEvent` della funzione di accesso richiama tutti i delegati del gestore eventi in modo asincrono utilizzando il <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> metodo. Tale metodo richiama ciascun gestore su un thread di lavoro e restituisce immediatamente, pertanto non è possibile bloccare gestori tra loro.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Procedura: Dichiarare eventi personalizzati per proteggere la memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
