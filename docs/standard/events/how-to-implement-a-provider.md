---
title: 'Procedura: Implementare un provider'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
ms.openlocfilehash: 4f8a213c0df3ef3c633106b7249a4947fe77c0d2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280023"
---
# <a name="how-to-implement-a-provider"></a>Procedura: Implementare un provider
Lo schema progettuale degli observer richiede una divisione tra un provider, che monitora i dati e invia le notifiche, e uno o più observer, che ricevono le notifiche (callback) dal provider. Questo argomento mostra come creare un provider. Un argomento correlato, [Procedura: Implementare un observer](how-to-implement-an-observer.md), descrive come creare un observer.  
  
### <a name="to-create-a-provider"></a>Per creare un provider  
  
1. Definire i dati del cui invio agli observer è responsabile il provider. Anche se il provider e i dati inviati agli observer possono essere di un unico tipo, sono in genere rappresentati da tipi diversi. Ad esempio, in un'applicazione di monitoraggio della temperatura la struttura `Temperature` definisce i dati che il provider (rappresentato dalla classe `TemperatureMonitor` definita nel prossimo passaggio) monitora e che gli observer sottoscrivono.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2. Definire il provider di dati, che è un tipo che implementa l'interfaccia <xref:System.IObservable%601?displayProperty=nameWithType>. L'argomento di tipo generico del provider è il tipo che il provider invia agli observer. L'esempio seguente definisce una classe `TemperatureMonitor`, che è un'implementazione <xref:System.IObservable%601?displayProperty=nameWithType> costruita con un argomento di tipo generico `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3. Determinare in che modo il provider archivierà i riferimenti agli observer, in modo che ogni observer riceva una notifica nei casi appropriati. In genere, a questo scopo viene usato un oggetto raccolta, ad esempio un oggetto <xref:System.Collections.Generic.List%601> generico. L'esempio seguente definisce un oggetto <xref:System.Collections.Generic.List%601> privato di cui viene creata un'istanza nel costruttore di classe `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4. Definire un'implementazione <xref:System.IDisposable> che il provider può restituire ai sottoscrittori in modo che questi possano smettere di ricevere notifiche in qualsiasi momento. L'esempio seguente definisce una classe `Unsubscriber` annidata alla quale viene passato un riferimento alla raccolta di sottoscrittori e al sottoscrittore quando viene creata un'istanza della classe. Questo codice consente al sottoscrittore di chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> dell'oggetto per rimuovere se stesso dalla raccolta di sottoscrittori.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5. Implementare il metodo <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>. Al metodo viene passato un riferimento all'interfaccia <xref:System.IObserver%601?displayProperty=nameWithType> e il metodo deve essere archiviato nell'oggetto progettato a questo scopo nel passaggio 3. Il metodo deve quindi restituire l'implementazione <xref:System.IDisposable> sviluppata nel passaggio 4. L'esempio seguente mostra l'implementazione del metodo <xref:System.IObservable%601.Subscribe%2A> nella classe `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6. Inviare notifiche agli observer nel modo appropriato chiamando le rispettive implementazioni <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType> e <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. In alcuni casi, un provider non può chiamare il metodo <xref:System.IObserver%601.OnError%2A> quando si verifica un errore. Ad esempio, il metodo `GetTemperature` seguente simula un monitoraggio che legge i dati di temperatura ogni cinque secondi e invia una notifica agli observer se la temperatura è cambiata di almeno 0,1 gradi rispetto alla lettura precedente. Se il dispositivo non segnala alcuna temperatura (ovvero se il valore è null), il provider invia una notifica agli observer indicando che la trasmissione è completa. Si noti che, oltre a chiamare il metodo <xref:System.IObserver%601.OnCompleted%2A> di ogni observer, il metodo `GetTemperature` cancella la raccolta <xref:System.Collections.Generic.List%601>. In questo caso, il provider non effettua alcuna chiamata al metodo <xref:System.IObserver%601.OnError%2A> dei relativi observer.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene il codice sorgente completo per la definizione di un'implementazione <xref:System.IObservable%601> per un'applicazione di monitoraggio della temperatura. L'esempio include la struttura `Temperature`, che corrisponde ai dati inviati agli observer, e la classe `TemperatureMonitor`, che corrisponde all'implementazione <xref:System.IObservable%601>.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IObservable%601>
- [Modello di progettazione Observer](observer-design-pattern.md)
- [Procedura: implementare un Observer](how-to-implement-an-observer.md)
- [Procedure consigliate per un modello di progettazione observer](observer-design-pattern-best-practices.md)
