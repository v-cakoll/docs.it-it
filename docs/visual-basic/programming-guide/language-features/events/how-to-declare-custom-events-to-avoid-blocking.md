---
title: 'Procedura: dichiarare eventi personalizzati per evitare il blocco'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: a9f9529d468a036d81c4e436429cbdb3207efd6e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405157"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Procedura: dichiarare eventi personalizzati per evitare il blocco (Visual Basic)
In alcuni casi è importante che un gestore eventi non blocchi i gestori eventi successivi. Gli eventi personalizzati consentono all'evento di chiamare i relativi gestori eventi in modo asincrono.  
  
 Per impostazione predefinita, il campo di archivio di backup per una dichiarazione di evento è un delegato multicast che combina in modo seriale tutti i gestori eventi. Ciò significa che se un gestore impiega molto tempo per il completamento, blocca gli altri gestori fino a quando non viene completato. I gestori di eventi ben funzionanti non devono mai eseguire operazioni lunghe o potenzialmente bloccanti.  
  
 Anziché utilizzare l'implementazione predefinita di eventi forniti da Visual Basic, è possibile utilizzare un evento personalizzato per eseguire i gestori eventi in modo asincrono.  
  
## <a name="example"></a>Esempio  
 In questo esempio, la `AddHandler` funzione di accesso aggiunge il delegato per ogni gestore dell' `Click` evento a un oggetto <xref:System.Collections.ArrayList> archiviato nel `EventHandlerList` campo.  
  
 Quando il codice genera l' `Click` evento, la `RaiseEvent` funzione di accesso richiama tutti i delegati del gestore eventi in modo asincrono usando il <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> metodo. Il metodo richiama ogni gestore in un thread di lavoro e restituisce immediatamente il controllo, in modo che i gestori non possano bloccarsi l'uno all'altro.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Events](index.md)
- [Procedura: dichiarare eventi personalizzati per proteggere la memoria](how-to-declare-custom-events-to-conserve-memory.md)
