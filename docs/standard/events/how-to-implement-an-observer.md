---
title: 'Procedura: Implementare un elemento Observer'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
ms.openlocfilehash: e6aba4d85e502563291478640927bd0f234736a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139316"
---
# <a name="how-to-implement-an-observer"></a>Procedura: Implementare un elemento Observer
Lo schema progettuale degli observer richiede una divisione tra un observer, che si registra per le notifiche, e un provider, che monitora i dati e invia notifiche a uno o più observer. Questo argomento descrive come creare un observer. Un argomento correlato, [Procedura: Implementare un provider](../../../docs/standard/events/how-to-implement-a-provider.md), descrive come creare un provider.  
  
### <a name="to-create-an-observer"></a>Per creare un observer  
  
1. Definire l'observer, che è un tipo che implementa l'interfaccia <xref:System.IObserver%601?displayProperty=nameWithType>. Ad esempio, il codice seguente definisce un tipo denominato `TemperatureReporter` che rappresenta un'implementazione costruita <xref:System.IObserver%601?displayProperty=nameWithType> con un argomento di tipo generico `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2. Se l'observer può smettere di ricevere notifiche prima che il provider chiami la relativa implementazione <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, definire una variabile privata che conterrà l'implementazione <xref:System.IDisposable> restituita dal metodo <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> del provider. È anche necessario definire un metodo di sottoscrizione che chiama il metodo <xref:System.IObservable%601.Subscribe%2A> del provider e archivia l'oggetto <xref:System.IDisposable> restituito. Ad esempio, il codice seguente definisce una variabile privata denominata `unsubscriber` e un metodo `Subscribe` che chiama il metodo <xref:System.IObservable%601.Subscribe%2A> del provider e assegna l'oggetto restituito alla variabile `unsubscriber`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3. Definire un metodo che consente all'observer di smettere di ricevere interrompere notifiche prima che il provider chiami la relativa implementazione <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, se questa funzionalità è necessaria. L'esempio seguente definisce un metodo `Unsubscribe`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4. Fornire le implementazioni dei tre metodi definiti dall'interfaccia <xref:System.IObserver%601>: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType> e <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. A seconda del provider e delle esigenze dell'applicazione, i metodi <xref:System.IObserver%601.OnError%2A> e <xref:System.IObserver%601.OnCompleted%2A> possono essere implementazioni dello stub. Si noti che il metodo <xref:System.IObserver%601.OnError%2A> non deve gestire l'oggetto <xref:System.Exception> passato come eccezione e che il metodo <xref:System.IObserver%601.OnCompleted%2A> è libero di chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> del provider. L'esempio seguente mostra l'implementazione <xref:System.IObserver%601> della classe `TemperatureReporter`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene il codice sorgente completo per la classe `TemperatureReporter`, che fornisce l'implementazione <xref:System.IObserver%601> per un'applicazione di monitoraggio della temperatura.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IObserver%601>
- [Modello di progettazione observer](../../../docs/standard/events/observer-design-pattern.md)
- [Procedura: Implementare un provider](../../../docs/standard/events/how-to-implement-a-provider.md)
- [Procedure consigliate per un modello di progettazione observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)
