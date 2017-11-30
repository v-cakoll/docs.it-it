---
title: 'Procedura: Implementare un provider'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a>Procedura: Implementare un provider
Il modello di progettazione osservatore richiede una divisione tra un provider che monitora i dati e invia le notifiche, e uno o più osservatori che ricevono le notifiche (callback) dal provider. In questo argomento viene illustrato come creare un provider. Un argomento correlato, [procedura: implementare un elemento Observer](../../../docs/standard/events/how-to-implement-an-observer.md), viene illustrato come creare un osservatore.  
  
### <a name="to-create-a-provider"></a>Per creare un provider  
  
1.  Definire i dati che il provider è responsabile per l'invio agli osservatori. Sebbene possano essere un singolo tipo di provider e i dati che invia agli osservatori, in genere sono rappresentati da tipi diversi. Ad esempio, in un'applicazione, il monitoraggio della temperatura di `Temperature` struttura definisce i dati che il provider (rappresentata dalla `TemperatureMonitor` classe definita nel passaggio successivo) consente di monitorare e da cui gli osservatori sottoscrivere.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Definire il provider di dati, ovvero un tipo che implementa il <xref:System.IObservable%601?displayProperty=nameWithType> interfaccia. Argomento di tipo generico del provider è il tipo che il provider invia agli osservatori. L'esempio seguente definisce un `TemperatureMonitor` (classe), ovvero un oggetto costruito <xref:System.IObservable%601?displayProperty=nameWithType> implementazione con un argomento di tipo generico di `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Determinare come il provider archivierà i riferimenti agli osservatori, in modo che ogni osservatore può ricevere una notifica quando appropriato. In genere, un oggetto di raccolta, ad esempio un oggetto generico <xref:System.Collections.Generic.List%601> oggetto viene utilizzato per questo scopo. L'esempio seguente definisce una privata <xref:System.Collections.Generic.List%601> oggetto che viene creata un'istanza di `TemperatureMonitor` costruttore della classe.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Definire un <xref:System.IDisposable> implementazione che il provider può restituire ai sottoscrittori in modo che possano smettere di ricevere notifiche in qualsiasi momento. L'esempio seguente definisce un tipo annidato `Unsubscriber` classe che viene passato un riferimento alla raccolta di sottoscrittori e al sottoscrittore quando viene creata un'istanza della classe. Questo codice consente di chiamare l'oggetto sottoscrittore <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementazione per rimuoverlo dalla raccolta di sottoscrittori.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Implementare il metodo <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>. Il metodo viene passato un riferimento di <xref:System.IObserver%601?displayProperty=nameWithType> l'interfaccia e devono essere archiviate nell'oggetto progettata a tale scopo, nel passaggio 3. Il metodo deve restituire quindi il <xref:System.IDisposable> implementazione sviluppato nel passaggio 4. Nell'esempio seguente viene illustrata l'implementazione del <xref:System.IObservable%601.Subscribe%2A> metodo la `TemperatureMonitor` classe.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Notificare agli osservatori esigenze chiamando i relativi <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, e <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementazioni. In alcuni casi, un provider non può chiamare il <xref:System.IObserver%601.OnError%2A> metodo quando si verifica un errore. Ad esempio, `GetTemperature` metodo simula un monitoraggio che legge i dati di temperatura ogni cinque secondi e notifica osservatori se la temperatura è stato modificato da almeno.1 gradi rispetto alla lettura precedente. Se il dispositivo non segnala una temperatura (ovvero, se il valore è null), il provider invia una notifica agli osservatori che la trasmissione è stata completata. Si noti che, oltre a chiamare ogni osservatore <xref:System.IObserver%601.OnCompleted%2A> (metodo), il `GetTemperature` metodo cancella il <xref:System.Collections.Generic.List%601> insieme. In questo caso, il provider non rende Nessuna chiamata al <xref:System.IObserver%601.OnError%2A> metodo osservatori.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente contiene il codice sorgente completo per la definizione di un <xref:System.IObservable%601> implementazione per un'applicazione di monitoraggio della temperatura. Include il `Temperature` struttura, ovvero i dati inviati agli osservatori, e `TemperatureMonitor` (classe), ovvero il <xref:System.IObservable%601> implementazione.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IObservable%601>  
 [Modello di progettazione observer](../../../docs/standard/events/observer-design-pattern.md)  
 [Procedura: Implementare un elemento Observer](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [Procedure consigliate per un modello di progettazione observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)
