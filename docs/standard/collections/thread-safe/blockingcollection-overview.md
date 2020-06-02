---
title: Panoramica di BlockingCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BlockingCollection, overview
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
ms.openlocfilehash: 708ab9dc8df2ee3128036ffc71e9abc51a56e33b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287913"
---
# <a name="blockingcollection-overview"></a>Panoramica di BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> è una classe di raccolta thread-safe che offre le funzionalità seguenti:  
  
- Implementazione del modello Producer-Consumer.  
  
- Aggiunta e rimozione simultanea di elementi da più thread.  
  
- Capacità massima facoltativa.  
  
- Operazioni di inserimento e rimozione che si bloccano quando la raccolta è vuota o piena.  
  
- Operazioni "prova" di inserimento e rimozione che non si bloccano o che si bloccano per un periodo di tempo specificato.  
  
- Incapsulamento di qualsiasi tipo di raccolta che implementi <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>  
  
- Annullamento con token di annullamento.  
  
- Due tipi di enumerazione con `foreach` (`For Each` in Visual Basic):  
  
    1. Enumerazione di sola lettura.  
  
    2. Enumerazione che rimuove gli elementi quando vengono enumerati.  
  
## <a name="bounding-and-blocking-support"></a>Supporto di delimitazione e blocco  
 <xref:System.Collections.Concurrent.BlockingCollection%601> supporta delimitazione e blocco. La delimitazione consente di impostare la capacità massima della raccolta. La delimitazione è importante in determinati scenari poiché consente di controllare la dimensione massima della raccolta in memoria, impedendo ai thread Producer di spostarsi troppo oltre i thread Consumer.  
  
 Più thread o attività possono aggiungere contemporaneamente elementi alla raccolta, e se la raccolta raggiunge la capacità massima specificata, i thread Producer si bloccano fino a quando non viene rimosso un elemento. Più Consumer possono rimuovere contemporaneamente elementi e quando la raccolta diventa vuota, i thread Consumer si bloccano fino a quando un Producer aggiunge un elemento. Un thread Producer può chiamare <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> per indicare che non verranno aggiunti altri elementi. I Consumer monitorano la proprietà <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> per sapere quando la raccolta è vuota e non verranno aggiunti altri elementi. Nell'esempio seguente viene illustrato un semplice BlockingCollection con una capacità delimitata di 100. Un'attività Producer aggiunge elementi alla raccolta, purché una condizione esterna sia true e quindi chiama <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>. L'attività di tipo Consumer accetta elementi finché la proprietà <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> è true.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Per un esempio completo, vedere [Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection](how-to-add-and-take-items.md).  
  
## <a name="timed-blocking-operations"></a>Operazioni di blocco temporizzate  
 Nelle operazioni di blocco temporizzate <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> sulle raccolte delimitate il metodo tenta di aggiungere o rimuovere un elemento. Se è disponibile un elemento, questo viene posizionato nella variabile che è stata passata per riferimento e il metodo restituisce true. Se dopo un periodo di timeout specificato non viene recuperato alcun elemento, il metodo restituisce false. Il thread è quindi libero di eseguire altre operazioni utili prima di tentare nuovamente di accedere alla raccolta. Per un esempio di accesso con blocco temporizzato, vedere il secondo esempio in [Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection](how-to-add-and-take-items.md).  
  
## <a name="cancelling-add-and-take-operations"></a>Annullamento di operazioni di aggiunta e rimozione  
 Le operazioni di aggiunta e rimozione solitamente vengono eseguite in un ciclo. È possibile annullare un ciclo passando un <xref:System.Threading.CancellationToken> al metodo <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> e quindi controllando il valore della proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token in ogni iterazione. Se il valore è true, l'utente deve decidere se rispondere alla richiesta di annullamento cancellando tutte le risorse e uscendo dal ciclo. Nell'esempio seguente viene illustrato un overload di <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> che accetta un token di annullamento e il codice che viene usato:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Per un esempio di aggiunta del supporto per l'annullamento, vedere il secondo esempio in [Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection](how-to-add-and-take-items.md).  
  
## <a name="specifying-the-collection-type"></a>Specifica del tipo di raccolta  
 Quando si crea un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601>, è possibile specificare non solo la capacità delimitata ma anche il tipo di raccolta da usare. Ad esempio, è possibile specificare <xref:System.Collections.Concurrent.ConcurrentQueue%601> per il comportamento FIFO (First In, First Out) o <xref:System.Collections.Concurrent.ConcurrentStack%601> per il comportamento LIFO (Last In, First Out). È possibile usare qualsiasi classe di raccolta che implementa l'interfaccia <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>. Il tipo di raccolta predefinito per <xref:System.Collections.Concurrent.BlockingCollection%601> è <xref:System.Collections.Concurrent.ConcurrentQueue%601>. L'esempio di codice seguente illustra come creare un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> di stringhe con capacità 1000, che usa un oggetto <xref:System.Collections.Concurrent.ConcurrentBag%601>:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Per altre informazioni, vedere [Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta](how-to-add-bounding-and-blocking.md).  
  
## <a name="ienumerable-support"></a>Supporto di IEnumerable  
 <xref:System.Collections.Concurrent.BlockingCollection%601> offre un metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> che consente agli utenti di usare `foreach` (`For Each` in Visual Basic) per rimuovere gli elementi fino a quando non viene completata la raccolta, ovvero finché non è vuota e non vengono aggiunti altri elementi. Per altre informazioni, vedere [Procedura: usare ForEach per rimuovere elementi in un oggetto BlockingCollection](how-to-use-foreach-to-remove.md).  
  
## <a name="using-many-blockingcollections-as-one"></a>Uso di più oggetti BlockingCollections come uno solo  
 Per gli scenari in cui un Consumer deve rimuovere elementi da più raccolte contemporaneamente, è possibile creare matrici di <xref:System.Collections.Concurrent.BlockingCollection%601> e usare i metodi statici, ad esempio <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A> che eseguiranno operazioni di aggiunta o rimozione in qualsiasi raccolta nella matrice. Se una raccolta è bloccata, il metodo ne cerca immediatamente un'altra finché non ne trova una che può eseguire l'operazione. Per altre informazioni, vedere [Procedura: usare matrici di BlockingCollection in una pipeline](how-to-use-arrays-of-blockingcollections.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Raccolte e strutture di dati](../index.md)
- [Raccolte thread-safe](index.md)
