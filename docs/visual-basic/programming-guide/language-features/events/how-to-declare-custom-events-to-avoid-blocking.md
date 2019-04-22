---
title: 'Procedura: Dichiarare eventi personalizzati per evitare il blocco (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821257"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Procedura: Dichiarare eventi personalizzati per evitare il blocco (Visual Basic)
Esistono diversi casi quando è importante che un gestore eventi non bloccano i gestori eventi successivi. Eventi personalizzati consentono di chiamare i relativi gestori eventi in modo asincrono l'evento.  
  
 Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi. Ciò significa che se un singolo gestore richiede molto tempo per il completamento, si blocca altri gestori fino al completamento. (I gestori eventi ben progettate devono evitare di eseguire operazioni di lunga durate o potenzialmente di blocco.)  
  
 Invece di usare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile usare un evento personalizzato da eseguire in modo asincrono i gestori di eventi.  
  
## <a name="example"></a>Esempio  
 In questo esempio, il `AddHandler` della funzione di accesso aggiunge il delegato per ogni gestore del `Click` evento a un <xref:System.Collections.ArrayList> archiviati nel `EventHandlerList` campo.  
  
 Quando il codice genera il `Click` evento, il `RaiseEvent` funzione di accesso richiama tutti i delegati del gestore eventi in modo asincrono utilizzando il <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> (metodo). Tale metodo richiama ciascun gestore su un thread di lavoro e restituisce immediatamente, in modo che i gestori non blocchino reciprocamente.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Procedura: Dichiarare eventi personalizzati per proteggere la memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
