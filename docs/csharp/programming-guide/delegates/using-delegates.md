---
title: Uso dei delegati - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], how to use
ms.assetid: 99a2fc27-a32e-4a34-921c-e65497520eec
ms.openlocfilehash: dcc73aba738d6296a44c48aad8b66cd6fc7f4a7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77448439"
---
# <a name="using-delegates-c-programming-guide"></a>Utilizzo di delegati (Guida per programmatori C#)

Un [delegato](../../language-reference/builtin-types/reference-types.md) è un tipo che incapsula in modo sicuro un metodo, simile a un puntatore a funzione in C e C++. A differenza dei puntatori a funzione, tuttavia, i delegati sono orientati a oggetti, indipendenti dai tipi e sicuri. Il tipo delegato è definito dal nome del delegato. Nell'esempio seguente viene dichiarato un delegato denominato `Del` che può incapsulare un metodo che accetta una [stringa](../../language-reference/builtin-types/reference-types.md) come argomento e restituisce [void](../../language-reference/builtin-types/void.md):

[!code-csharp[csProgGuideDelegates#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#21)]

Un oggetto delegato viene normalmente creato fornendo il nome del metodo di cui il delegato eseguirà il wrapping o con una [funzione anonima](../statements-expressions-operators/anonymous-functions.md). Una volta che viene creata un'istanza di un delegato, una chiamata al metodo effettuata al delegato verrà passata dal delegato a tale metodo. I parametri passati al delegato dal chiamante vengono passati al metodo e il valore restituito, se presente, dal metodo viene restituito al chiamante dal delegato. Questa operazione è nota come richiamare il delegato. È possibile richiamare un delegato per cui è stata creata un'istanza come se fosse il metodo di wrapping stesso. Ad esempio:

[!code-csharp[csProgGuideDelegates#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#22)]  

[!code-csharp[csProgGuideDelegates#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#23)]

Tipi delegati vengono derivati dalla classe <xref:System.Delegate> di.NET Framework. I tipi delegati sono [sealed](../../language-reference/keywords/sealed.md), ovvero non possono essere usati per la derivazione, e non è possibile derivare classi personalizzate da <xref:System.Delegate>. Poiché l'istanza del delegato è un oggetto, può essere passata come parametro o assegnata a una proprietà. In questo modo un metodo può accettare un delegato come parametro e chiamare il delegato in un secondo momento. Questa operazione è nota come callback asincrono ed è un metodo comune per notificare un chiamante al termine di un processo lungo. Quando un delegato viene usato in questo modo, per il codice che usa il delegato non è richiesta alcuna conoscenza dell'implementazione del metodo in uso. La funzionalità è simile all'incapsulamento fornito dalle interfacce.

Un altro utilizzo comune dei callback è la definizione di un metodo di confronto personalizzato e il passaggio di tale delegato a un metodo di ordinamento. Consente al codice del chiamante di entrare a far parte dell'algoritmo di ordinamento. Nell'esempio di metodo seguente viene usato il tipo `Del` come parametro:

[!code-csharp[csProgGuideDelegates#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#24)]

È quindi possibile passare il delegato creato in precedenza a tale metodo:

[!code-csharp[csProgGuideDelegates#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#25)]

e visualizzare il seguente output sulla console:

```console
The number is: 3
```

Usando il delegato come astrazione, non è necessario chiamare direttamente la console da `MethodWithCallback`, ovvero questo non deve essere progettato tenendo presente una console. `MethodWithCallback` si limita a preparare una stringa e a passarla a un altro metodo. Questa operazione è particolarmente efficace perché un metodo delegato può usare qualsiasi numero di parametri.

Quando viene creato un delegato per eseguire il wrapping di un metodo di istanza, il delegato fa riferimento sia all'istanza sia al metodo. Un delegato non ha alcuna conoscenza del tipo di istanza a parte il metodo di cui esegue il wrapping, perciò un delegato può fare riferimento a qualsiasi tipo di oggetto a condizione che vi sia un metodo su tale oggetto che corrisponda alla firma del delegato. Quando viene creato un delegato per eseguire il wrapping di un metodo statico, fa riferimento solo al metodo. Si considerino le dichiarazioni seguenti:

[!code-csharp[csProgGuideDelegates#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#26)]

Insieme al metodo statico `DelegateMethod` illustrato in precedenza, ci sono tre metodi di cui è possibile eseguire il wrapping in un'istanza di `Del`.

Un delegato può chiamare più di un metodo, quando viene richiamato. Questo processo viene definito multicasting. Per aggiungere un ulteriore metodo all'elenco dei metodi del delegato (l'elenco chiamate), è necessario semplicemente aggiungere due delegati usando gli operatori addizione o di assegnazione di addizione ("+" o "+="). Ad esempio:

[!code-csharp[csProgGuideDelegates#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#27)]

A questo punto `allMethodsDelegate` contiene tre metodi nel relativo elenco chiamate: `Method1`, `Method2` e `DelegateMethod`. I tre delegati originali, `d1`, `d2` e `d3`, rimangono invariati. Quando si richiama `allMethodsDelegate`, tutti e tre i metodi vengono chiamati nell'ordine. Se il delegato usa parametri per riferimento, il riferimento viene passato in sequenza a ciascuno dei tre metodi a turno e le eventuali modifiche apportate da un solo metodo saranno visibili al metodo successivo. Quando uno dei metodi genera un'eccezione non rilevata all'interno del metodo, tale eccezione viene passata al chiamante del delegato e non verrà chiamato nessun metodo successivo nell'elenco chiamate. Se il delegato ha un valore restituito e/o i parametri out, restituisce il valore restituito e i parametri dell'ultimo metodo richiamato. Per rimuovere un metodo dall'elenco chiamate, utilizzare gli operatori`-` `-=`di assegnazione di [sottrazione o sottrazione](../../language-reference/operators/subtraction-operator.md) ( o ). Ad esempio:

[!code-csharp[csProgGuideDelegates#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#28)]

Poiché i tipi delegati vengono derivati da `System.Delegate`, i metodi e le proprietà definiti da tale classe possono essere chiamati sul delegato. Ad esempio, per trovare il numero di metodi nell'elenco chiamate di un delegato, è possibile scrivere:

[!code-csharp[csProgGuideDelegates#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#29)]

I delegati con più metodi nel relativo elenco chiamate derivano da <xref:System.MulticastDelegate>, cioè una sottoclasse di `System.Delegate`. Il codice sopra riportato funziona in entrambi i casi, perché entrambe le classi supportano `GetInvocationList`.

I delegati multicast vengono ampiamente usati nella gestione degli eventi. Gli oggetti di origine evento inviano notifiche di eventi agli oggetti destinatario registrati per ricevere l'evento. Per registrarsi a un evento, il destinatario crea un metodo che può gestire l'evento, quindi crea un delegato per il metodo e passa il delegato all'origine evento. L'origine chiama il delegato quando si verifica l'evento. Il delegato chiama quindi il metodo di gestione eventi sul destinatario, recapitando i dati dell'evento. Il tipo delegato per un determinato evento è definito dall'origine evento. Per altre informazioni, vedere [Eventi](../events/index.md).

Se si confrontano delegati di due tipi diversi assegnati in fase di compilazione si avrà un errore di compilazione. Se le istanze dei delegati sono staticamente del tipo `System.Delegate`, il confronto è consentito, ma restituirà false in fase di esecuzione. Ad esempio:

[!code-csharp[csProgGuideDelegates#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#30)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Delegati](./index.md)
- [Uso della varianza nei delegati](../concepts/covariance-contravariance/using-variance-in-delegates.md)
- [Varianza nei delegati](../concepts/covariance-contravariance/variance-in-delegates.md)
- [Uso della varianza per i delegati generici Func e Action](../concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
- [Events](../events/index.md)
