---
title: Utilizzo di delegati (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], how to use
ms.assetid: 99a2fc27-a32e-4a34-921c-e65497520eec
ms.openlocfilehash: b27c94570fdf76808e8a7df67b34466bde20de7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-delegates-c-programming-guide"></a>Utilizzo di delegati (Guida per programmatori C#)
Un [delegato](../../../csharp/language-reference/keywords/delegate.md) è un tipo che incapsula in modo sicuro un metodo, simile a un puntatore a funzione in C e C++. A differenza dei puntatori a funzione, tuttavia, i delegati sono orientati a oggetti, indipendenti dai tipi e sicuri. Il tipo delegato è definito dal nome del delegato. Nell'esempio seguente viene dichiarato un delegato denominato `Del` che può incapsulare un metodo che accetta una [stringa](../../../csharp/language-reference/keywords/string.md) come argomento e restituisce [void](../../../csharp/language-reference/keywords/void.md):  
  
 [!code-csharp[csProgGuideDelegates#21](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_1.cs)]  
  
 Un oggetto delegato viene normalmente creato fornendo il nome del metodo di cui il delegato eseguirà il wrapping o con un [metodo anonimo](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md). Una volta che viene creata un'istanza di un delegato, una chiamata al metodo effettuata al delegato verrà passata dal delegato a tale metodo. I parametri passati al delegato dal chiamante vengono passati al metodo e il valore restituito, se presente, dal metodo viene restituito al chiamante dal delegato. Questa operazione è nota come richiamare il delegato. È possibile richiamare un delegato per cui è stata creata un'istanza come se fosse il metodo di wrapping stesso. Ad esempio:  
  
 [!code-csharp[csProgGuideDelegates#22](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_2.cs)]  
  
 [!code-csharp[csProgGuideDelegates#23](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_3.cs)]  
  
 Tipi delegati vengono derivati dalla classe <xref:System.Delegate> di.NET Framework. I tipi delegati sono [sealed](../../../csharp/language-reference/keywords/sealed.md), ovvero non possono essere usati per la derivazione, e non è possibile derivare classi personalizzate da <xref:System.Delegate>. Poiché l'istanza del delegato è un oggetto, può essere passata come parametro o assegnata a una proprietà. In questo modo un metodo può accettare un delegato come parametro e chiamare il delegato in un secondo momento. Questa operazione è nota come callback asincrono ed è un metodo comune per notificare un chiamante al termine di un processo lungo. Quando un delegato viene usato in questo modo, per il codice che usa il delegato non è richiesta alcuna conoscenza dell'implementazione del metodo in uso. La funzionalità è simile all'incapsulamento fornito dalle interfacce.  
  
 Un altro utilizzo comune dei callback è la definizione di un metodo di confronto personalizzato e il passaggio di tale delegato a un metodo di ordinamento. Consente al codice del chiamante di entrare a far parte dell'algoritmo di ordinamento. Nell'esempio di metodo seguente viene usato il tipo `Del` come parametro:  
  
 [!code-csharp[csProgGuideDelegates#24](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_4.cs)]  
  
 È quindi possibile passare il delegato creato in precedenza a tale metodo:  
  
 [!code-csharp[csProgGuideDelegates#25](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_5.cs)]  
  
 e visualizzare il seguente output sulla console:  
  
 `The number is: 3`  
  
 Usando il delegato come astrazione, non è necessario chiamare direttamente la console da `MethodWithCallback`, ovvero questo non deve essere progettato tenendo presente una console. `MethodWithCallback` si limita a preparare una stringa e a passarla a un altro metodo. Questa operazione è particolarmente efficace perché un metodo delegato può usare qualsiasi numero di parametri.  
  
 Quando viene creato un delegato per eseguire il wrapping di un metodo di istanza, il delegato fa riferimento sia all'istanza sia al metodo. Un delegato non ha alcuna conoscenza del tipo di istanza a parte il metodo di cui esegue il wrapping, perciò un delegato può fare riferimento a qualsiasi tipo di oggetto a condizione che vi sia un metodo su tale oggetto che corrisponda alla firma del delegato. Quando viene creato un delegato per eseguire il wrapping di un metodo statico, fa riferimento solo al metodo. Si considerino le dichiarazioni seguenti:  
  
 [!code-csharp[csProgGuideDelegates#26](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_6.cs)]  
  
 Insieme al metodo statico `DelegateMethod` illustrato in precedenza, ci sono tre metodi di cui è possibile eseguire il wrapping in un'istanza di `Del`.  
  
 Un delegato può chiamare più di un metodo, quando viene richiamato. Questo processo viene definito multicasting. Per aggiungere un ulteriore metodo all'elenco dei metodi del delegato (l'elenco chiamate), è necessario semplicemente aggiungere due delegati usando gli operatori addizione o di assegnazione di addizione ("+" o "+="). Ad esempio:  
  
 [!code-csharp[csProgGuideDelegates#27](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_7.cs)]  
  
 A questo punto `allMethodsDelegate` contiene tre metodi nel relativo elenco chiamate: `Method1`, `Method2` e `DelegateMethod`. I tre delegati originali, `d1`, `d2` e `d3`, rimangono invariati. Quando si richiama `allMethodsDelegate`, tutti e tre i metodi vengono chiamati nell'ordine. Se il delegato usa parametri per riferimento, il riferimento viene passato in sequenza a ciascuno dei tre metodi a turno e le eventuali modifiche apportate da un solo metodo saranno visibili al metodo successivo. Quando uno dei metodi genera un'eccezione non rilevata all'interno del metodo, tale eccezione viene passata al chiamante del delegato e non verrà chiamato nessun metodo successivo nell'elenco chiamate. Se il delegato ha un valore restituito e/o i parametri out, restituisce il valore restituito e i parametri dell'ultimo metodo richiamato. Per rimuovere un metodo dall'elenco chiamate, usare l'operatore di decremento o l'operatore di decremento di assegnazione ("-" o "-="'). Ad esempio:  
  
 [!code-csharp[csProgGuideDelegates#28](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_8.cs)]  
  
 Poiché i tipi delegati vengono derivati da `System.Delegate`, i metodi e le proprietà definiti da tale classe possono essere chiamati sul delegato. Ad esempio, per trovare il numero di metodi nell'elenco chiamate di un delegato, è possibile scrivere:  
  
 [!code-csharp[csProgGuideDelegates#29](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_9.cs)]  
  
 I delegati con più metodi nel relativo elenco chiamate derivano da <xref:System.MulticastDelegate>, cioè una sottoclasse di `System.Delegate`. Il codice sopra riportato funziona in entrambi i casi, perché entrambe le classi supportano `GetInvocationList`.  
  
 I delegati multicast vengono ampiamente usati nella gestione degli eventi. Gli oggetti di origine evento inviano notifiche di eventi agli oggetti destinatario registrati per ricevere l'evento. Per registrarsi a un evento, il destinatario crea un metodo che può gestire l'evento, quindi crea un delegato per il metodo e passa il delegato all'origine evento. L'origine chiama il delegato quando si verifica l'evento. Il delegato chiama quindi il metodo di gestione eventi sul destinatario, recapitando i dati dell'evento. Il tipo delegato per un determinato evento è definito dall'origine evento. Per altre informazioni, vedere [Eventi](../../../csharp/programming-guide/events/index.md).  
  
 Se si confrontano delegati di due tipi diversi assegnati in fase di compilazione si avrà un errore di compilazione. Se le istanze dei delegati sono staticamente del tipo `System.Delegate`, il confronto è consentito, ma restituirà false in fase di esecuzione. Ad esempio:  
  
 [!code-csharp[csProgGuideDelegates#30](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_10.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Delegati](../../../csharp/programming-guide/delegates/index.md)  
 [Uso della varianza nei delegati](http://msdn.microsoft.com/library/e6acad03-93e0-4efb-a158-8696d5eb4ecf)  
 [Varianza nei delegati](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca)  
 [Uso della varianza per i delegati generici Func e Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290)  
 [Eventi](../../../csharp/programming-guide/events/index.md)
