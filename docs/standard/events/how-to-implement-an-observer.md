---
title: 'Procedura: Implementare un elemento Observer'
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
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a>Procedura: Implementare un elemento Observer
Il modello di progettazione osservatore richiede una divisione tra un osservatore, che registra per le notifiche, e un provider, che esegue il monitoraggio dei dati e inviare notifiche agli osservatori di uno o più. In questo argomento viene illustrato come creare un osservatore. Un argomento correlato, [procedura: implementare un Provider](../../../docs/standard/events/how-to-implement-a-provider.md), viene illustrato come creare un provider.  
  
### <a name="to-create-an-observer"></a>Per creare un elemento observer  
  
1.  Definire l'osservatore, che è un tipo che implementa il <xref:System.IObserver%601?displayProperty=nameWithType> interfaccia. Ad esempio, il codice seguente definisce un tipo denominato `TemperatureReporter` che rappresenta un elemento costruito <xref:System.IObserver%601?displayProperty=nameWithType> implementazione con un argomento di tipo generico di `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Se l'osservatore può interrompere la ricezione di notifiche prima che il provider chiama il relativo <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementazione, definire una variabile privata che conterrà il <xref:System.IDisposable> implementazione il provider ha restituito <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> metodo. È inoltre necessario definire un metodo di sottoscrizione che chiama il provider <xref:System.IObservable%601.Subscribe%2A> (metodo) e archivia l'oggetto restituito <xref:System.IDisposable> oggetto. Ad esempio, il codice seguente definisce una variabile privata denominata `unsubscriber` e definisce un `Subscribe` metodo che chiama il provider <xref:System.IObservable%601.Subscribe%2A> metodo e assegna l'oggetto restituito per il `unsubscriber` variabile.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Definire un metodo che consente l'osservatore interrompere la ricezione di notifiche prima che il provider chiama il relativo <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementazione, se questa funzionalità è necessaria. L'esempio seguente definisce un `Unsubscribe` metodo.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Fornire le implementazioni dei tre metodi definiti dal <xref:System.IObserver%601> interfaccia: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, e <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. A seconda di provider e le esigenze dell'applicazione, il <xref:System.IObserver%601.OnError%2A> e <xref:System.IObserver%601.OnCompleted%2A> metodi possono essere implementazioni dello stub. Si noti che il <xref:System.IObserver%601.OnError%2A> metodo non deve gestire l'oggetto passato <xref:System.Exception> oggetto come un'eccezione e <xref:System.IObserver%601.OnCompleted%2A> metodo è libero di chiamare il provider <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementazione. Nell'esempio seguente il <xref:System.IObserver%601> implementazione del `TemperatureReporter` classe.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente contiene il codice sorgente completo per il `TemperatureReporter` (classe), che fornisce il <xref:System.IObserver%601> implementazione per un'applicazione di monitoraggio della temperatura.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IObserver%601>  
 [Modello di progettazione observer](../../../docs/standard/events/observer-design-pattern.md)  
 [Procedura: Implementare un provider](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [Procedure consigliate per un modello di progettazione observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)
