---
title: Operazioni interlocked
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 361e618578e836e10cf8655f027bed42eac7affd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393139"
---
# <a name="interlocked-operations"></a>Operazioni interlocked
La classe <xref:System.Threading.Interlocked> fornisce metodi per la sincronizzazione dell'accesso a una variabile condivisa da più thread. I thread di processi differenti possono usare questo meccanismo se la variabile si trova nella memoria condivisa. Le operazioni con interlock sono atomiche, ovvero un'intera operazione costituisce un'unità che non può essere interrotta da un'altra operazione con interlock nella stessa variabile. Questa caratteristica è importante nei sistemi operativi con multithreading preemptive in cui un thread può essere sospeso dopo il caricamento di un valore da un indirizzo di memoria, ma prima che sia possibile modificarlo e memorizzarlo.  
  
 La classe <xref:System.Threading.Interlocked> fornisce le operazioni seguenti:  
  
-   In .NET Framework versione 2.0 il metodo <xref:System.Threading.Interlocked.Add%2A> aggiunge un valore intero a una variabile e restituisce il nuovo valore della variabile.  
  
-   In .NET Framework versione 2.0 il metodo <xref:System.Threading.Interlocked.Read%2A> legge un valore intero a 64 bit come operazione atomica. Questa caratteristica è utile nei sistemi a 32 bit in cui la lettura di un valore integer a 64 bit non è normalmente un'operazione atomica.  
  
-   I metodi <xref:System.Threading.Interlocked.Increment%2A> e <xref:System.Threading.Interlocked.Decrement%2A> aumentano o riducono il valore di una variabile e restituiscono il valore risultante.  
  
-   Il metodo <xref:System.Threading.Interlocked.Exchange%2A> esegue uno scambio atomico del valore in una variabile specificata, restituendo il valore e sostituendolo con un nuovo valore. In .NET Framework versione 2.0 è possibile usare un overload generico di questo metodo per eseguire lo scambio in una variabile di qualsiasi tipo di riferimento. Vedere <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   Anche il metodo <xref:System.Threading.Interlocked.CompareExchange%2A> scambia due valori, ma in base al risultato di un confronto. In .NET Framework versione 2.0 è possibile usare un overload generico di questo metodo per eseguire lo scambio in una variabile di qualsiasi tipo di riferimento. Vedere <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 Nei processori moderni i metodi della classe <xref:System.Threading.Interlocked> possono essere spesso implementati da una singola istruzione. In questo modo, offrono una sincronizzazione ad alte prestazioni e possono essere usati per compilare meccanismi di sincronizzazione di livello più elevato, come gli spinlock.  
  
 Per un esempio che usa le classi <xref:System.Threading.Monitor> e <xref:System.Threading.Interlocked> in combinazione, vedere [Monitor](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>Esempio di CompareExchange  
 Il metodo <xref:System.Threading.Interlocked.CompareExchange%2A> può essere usato per la protezione di calcoli più complessi rispetto al semplice incremento o decremento. L'esempio seguente illustra un metodo thread-safe che aggiunge un totale parziale memorizzato come numero a virgola mobile. Per i valori interi, il metodo <xref:System.Threading.Interlocked.Add%2A> rappresenta una soluzione più semplice. Per esempi di codice completi, vedere gli overload di <xref:System.Threading.Interlocked.CompareExchange%2A> che accettano argomenti a virgola mobile a precisione singola e precisione doppia (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> e <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Overload non tipizzati di Exchange e CompareExchange  
 I metodi <xref:System.Threading.Interlocked.Exchange%2A> e <xref:System.Threading.Interlocked.CompareExchange%2A> hanno overload che accettano argomenti di tipo <xref:System.Object>. Il primo argomento di ognuno di questi overload è `ref Object` (`ByRef … As Object` in Visual Basic) e, per garantire l'indipendenza dai tipi, la variabile passata a questo argomento deve essere rigorosamente di tipo <xref:System.Object>. Non è possibile eseguire semplicemente il cast del primo argomento nel tipo <xref:System.Object> quando si chiamano questi metodi.  
  
> [!NOTE]
>  In .NET Framework versione 2.0 usare gli overload generici dei metodi <xref:System.Threading.Interlocked.Exchange%2A> e <xref:System.Threading.Interlocked.CompareExchange%2A> per lo scambio di variabili fortemente tipizzate.  
  
 L'esempio di codice seguente illustra una proprietà di tipo `ClassA` che può essere impostata una sola volta poiché può essere implementata in .NET Framework versione 1.0 o 1.1.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)
