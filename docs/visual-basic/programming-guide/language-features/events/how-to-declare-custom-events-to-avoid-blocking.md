---
title: 'Procedura: dichiarare eventi personalizzati per evitare il blocco'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345144"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)
In alcuni casi è importante che un gestore eventi non blocchi i gestori eventi successivi. Gli eventi personalizzati consentono all'evento di chiamare i relativi gestori eventi in modo asincrono.  
  
 Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi. Ciò significa che se un gestore impiega molto tempo per il completamento, blocca gli altri gestori fino a quando non viene completato. I gestori di eventi ben funzionanti non devono mai eseguire operazioni lunghe o potenzialmente bloccanti.  
  
 Anziché utilizzare l'implementazione predefinita di eventi forniti da Visual Basic, è possibile utilizzare un evento personalizzato per eseguire i gestori eventi in modo asincrono.  
  
## <a name="example"></a>Esempio  
 In questo esempio, la funzione di accesso `AddHandler` aggiunge il delegato per ogni gestore dell'evento `Click` a un <xref:System.Collections.ArrayList> archiviato nel campo `EventHandlerList`.  
  
 Quando il codice genera l'evento `Click`, la funzione di accesso `RaiseEvent` richiama tutti i delegati del gestore eventi in modo asincrono usando il metodo <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>. Il metodo richiama ogni gestore in un thread di lavoro e restituisce immediatamente il controllo, in modo che i gestori non possano bloccarsi l'uno all'altro.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Procedura: Dichiarare eventi personalizzati per proteggere la memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
