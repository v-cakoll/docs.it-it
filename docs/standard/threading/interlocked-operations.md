---
title: Operazioni interlocked
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
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a>Operazioni interlocked
La <xref:System.Threading.Interlocked> classe fornisce metodi per sincronizzare l'accesso a una variabile condivisa da più thread. I thread di processi differenti possono usare questo meccanismo se la variabile si trova nella memoria condivisa. Le operazioni con interlock sono atomiche, ovvero un'intera operazione costituisce un'unità che non può essere interrotta da un'altra operazione con interlock nella stessa variabile. Questa caratteristica è importante nei sistemi operativi con multithreading preemptive in cui un thread può essere sospeso dopo il caricamento di un valore da un indirizzo di memoria, ma prima che sia possibile modificarlo e memorizzarlo.  
  
 La <xref:System.Threading.Interlocked> classe fornisce le seguenti operazioni:  
  
-   In .NET Framework versione 2.0, il <xref:System.Threading.Interlocked.Add%2A> metodo aggiunge un valore integer a una variabile e restituisce il nuovo valore della variabile.  
  
-   In .NET Framework versione 2.0, il <xref:System.Threading.Interlocked.Read%2A> metodo legge un valore integer a 64 bit come operazione atomica. Questa caratteristica è utile nei sistemi a 32 bit in cui la lettura di un valore integer a 64 bit non è normalmente un'operazione atomica.  
  
-   Il <xref:System.Threading.Interlocked.Increment%2A> e <xref:System.Threading.Interlocked.Decrement%2A> metodi incrementare o decrementare una variabile e restituire il valore risultante.  
  
-   Il <xref:System.Threading.Interlocked.Exchange%2A> metodo esegue uno scambio atomico del valore in una variabile specificata, restituendo tale valore e sostituirlo con un nuovo valore. In .NET Framework versione 2.0 è possibile usare un overload generico di questo metodo per eseguire lo scambio in una variabile di qualsiasi tipo di riferimento. Vedere <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   Il <xref:System.Threading.Interlocked.CompareExchange%2A> anche metodo scambia due valori, ma in base al risultato di un confronto. In .NET Framework versione 2.0 è possibile usare un overload generico di questo metodo per eseguire lo scambio in una variabile di qualsiasi tipo di riferimento. Vedere <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 Nei metodi di moderni processori di <xref:System.Threading.Interlocked> classe spesso può essere implementata da una singola istruzione. In questo modo, offrono una sincronizzazione ad alte prestazioni e possono essere usati per compilare meccanismi di sincronizzazione di livello più elevato, come gli spinlock.  
  
 Per un esempio che utilizza il <xref:System.Threading.Monitor> e <xref:System.Threading.Interlocked> classi combinate, vedere [monitoraggi](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>Esempio di CompareExchange  
 Il <xref:System.Threading.Interlocked.CompareExchange%2A> metodo può essere utilizzato per proteggere i calcoli più complessi di semplice incremento e decremento. L'esempio seguente illustra un metodo thread-safe che aggiunge un totale parziale memorizzato come numero a virgola mobile. (Per i numeri interi, di <xref:System.Threading.Interlocked.Add%2A> metodo è una soluzione più semplice.) Per esempi di codice completo, vedere gli overload di <xref:System.Threading.Interlocked.CompareExchange%2A> che accettano argomenti a virgola mobile e precisione singola e precisione doppia (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> e <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Overload non tipizzati di Exchange e CompareExchange  
 Il <xref:System.Threading.Interlocked.Exchange%2A> e <xref:System.Threading.Interlocked.CompareExchange%2A> metodi dispongono di overload che accettano argomenti di tipo <xref:System.Object>. Il primo argomento di ciascuno di questi overload è `ref Object` (`ByRef … As Object` in Visual Basic), e indipendenza dai tipi richiede la variabile passata a questo argomento deve essere rigorosamente di <xref:System.Object>; non è possibile convertire semplicemente il primo argomento di tipo <xref:System.Object> Quando si chiamano questi metodi.  
  
> [!NOTE]
>  In .NET Framework versione 2.0, usare gli overload generici del <xref:System.Threading.Interlocked.Exchange%2A> e <xref:System.Threading.Interlocked.CompareExchange%2A> variabili di metodi per lo scambio fortemente tipizzate.  
  
 L'esempio di codice seguente illustra una proprietà di tipo `ClassA` che può essere impostata una sola volta poiché può essere implementata in .NET Framework versione 1.0 o 1.1.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)
