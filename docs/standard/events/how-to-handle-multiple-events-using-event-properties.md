---
title: 'Procedura: gestire più eventi mediante le relative proprietà'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: c5be541c1a40c5d16a0502e76adef24f6a41cc89
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288472"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a>Procedura: gestire più eventi mediante le relative proprietà
Per utilizzare le proprietà evento è necessario definire queste proprietà nella classe tramite cui vengono generati gli eventi e, successivamente, impostarne i delegati nelle classi mediante cui vengono gestiti gli eventi. Per implementare più proprietà evento in una classe, la classe deve archiviare e mantenere internamente il delegato definito per ogni evento. Uno degli approcci più comuni consiste nell'implementare una raccolta di delegati indicizzata da una chiave evento.  
  
 Per archiviare i delegati per ogni evento, è possibile usare la classe <xref:System.ComponentModel.EventHandlerList> o implementare una raccolta personalizzata. La classe della raccolta deve fornire metodi per l'impostazione, l'accesso e il recupero del delegato del gestore eventi in base alla chiave evento. È possibile, ad esempio, usare una classe <xref:System.Collections.Hashtable> o derivare una classe personalizzata dalla classe <xref:System.Collections.DictionaryBase>. I dettagli sull'implementazione della raccolta di delegati non devono necessariamente essere esposti al di fuori della classe.  
  
 Ogni proprietà evento all'interno della classe definisce un metodo della funzione di accesso add e un metodo della funzione di accesso remove. La funzione di accesso add di una proprietà evento aggiunge un'istanza del delegato di input alla raccolta di delegati. La funzione di accesso remove di una proprietà evento rimuove un'istanza del delegato di input dalla raccolta di delegati. Le funzioni di accesso delle proprietà evento usano la chiave predefinita della proprietà per aggiungere e rimuovere istanze nella raccolta di delegati.  
  
### <a name="to-handle-multiple-events-using-event-properties"></a>Per gestire più eventi mediante le relative proprietà  
  
1. Definire una raccolta di delegati all'interno della classe che genera gli eventi.  
  
2. Definire una chiave per ogni evento.  
  
3. Definire le proprietà evento nella classe che genera gli eventi.  
  
4. Usare la raccolta di delegati per implementare i metodi delle funzioni di accesso add e remove per le proprietà evento.  
  
5. Usare le proprietà evento pubbliche per aggiungere e rimuovere i delegati dei gestori eventi nelle classi che gestiscono gli eventi.  
  
## <a name="example"></a>Esempio  
 L'esempio C# seguente implementa le proprietà evento `MouseDown` e `MouseUp`, usando un oggetto <xref:System.ComponentModel.EventHandlerList> per archiviare il delegato di ogni evento. Le parole chiave dei costrutti delle proprietà evento sono riportate in grassetto.  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [Events](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [Procedura: dichiarare eventi personalizzati per proteggere la memoria](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
