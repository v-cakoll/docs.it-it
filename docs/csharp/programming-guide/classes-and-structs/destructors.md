---
title: Finalizzatori - Guida per programmatori C#
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: 62fc531a8064a8a5cb144a89aa9975b3199db976
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990121"
---
# <a name="finalizers-c-programming-guide"></a>Finalizzatori (Guida per programmatori C#)
I finalizzatori (detti anche **distruttori**) vengono usati per eseguire operazioni di pulizia finale eventualmente necessarie quando un'istanza di classe viene raccolta da Garbage Collector.  
  
## <a name="remarks"></a>Osservazioni  
  
- I finalizzatori non possono essere definiti negli struct. Vengono usati solo con le classi.  
  
- Una classe può avere un solo finalizzatore.  
  
- I finalizzatori non possono essere ereditati e non è possibile eseguirne l'overload.  
  
- I finalizzatori non possono essere chiamati. Vengono richiamati automaticamente.  
  
- Un finalizzatore non accetta modificatori e non ha parametri.  
  
 Ad esempio, di seguito è riportata la dichiarazione di un finalizzatore per la classe `Car`.
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

Un finalizzatore può anche essere implementato come definizione di corpo dell'espressione, come illustrato nell'esempio seguente.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 Il finalizzatore chiama implicitamente <xref:System.Object.Finalize%2A> per la classe di base dell'oggetto. Di conseguenza, una chiamata a un finalizzatore viene convertita implicitamente nel codice seguente:  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 Questo progetto significa che il `Finalize` metodo viene chiamato in modo ricorsivo per tutte le istanze nella catena di ereditarietà, dal più derivato al meno derivato.  
  
> [!NOTE]
> I finalizzatori vuoti non devono essere usati. Quando una classe contiene un finalizzatore, viene creata una voce nella coda `Finalize`. Quando si chiama il finalizzatore, viene richiamato Garbage Collector per elaborare la coda. Se il finalizzatore è vuoto, si verifica semplicemente un calo di prestazioni.  
  
 Il programmatore non ha alcun controllo sul momento in cui viene chiamato il finalizzatore; il Garbage Collector decide quando chiamarlo. Il Garbage Collector controlla gli oggetti che non vengono più usati dall'applicazione e, se considera un oggetto idoneo per la finalizzazione, chiama il finalizzatore (se presente) e recupera la memoria usata per archiviare l'oggetto.

 Nelle applicazioni .NET Framework (ma non nelle applicazioni .NET Core) i finalizzatori vengono chiamati anche alla chiusura del programma.
  
 È possibile forzare la Garbage Collection chiamando <xref:System.GC.Collect%2A> , ma nella maggior parte dei casi, questa chiamata deve essere evitata perché potrebbe creare problemi di prestazioni.  
  
## <a name="using-finalizers-to-release-resources"></a>Uso di finalizzatori per liberare risorse  
 In generale, in C# non è richiesto il maggior livello di gestione della memoria da parte dello sviluppatore come linguaggi che non hanno come destinazione un runtime con Garbage Collection. Ciò è dovuto al fatto che .NET Garbage Collector gestisce in modo implicito l'allocazione e il rilascio di memoria per gli oggetti. Tuttavia, quando l'applicazione incapsula risorse non gestite, ad esempio Windows, file e connessioni di rete, è necessario usare i finalizzatori per liberare tali risorse. Quando l'oggetto è idoneo per la finalizzazione, il Garbage Collector esegue il metodo `Finalize` dell'oggetto.
  
## <a name="explicit-release-of-resources"></a>Rilascio esplicito di risorse  
 Se l'applicazione usa una risorsa esterna che consuma molta memoria, è consigliabile specificare un modo per rilasciare la risorsa in modo esplicito prima che il Garbage Collector renda disponibile l'oggetto. Per rilasciare la risorsa, implementare un `Dispose` metodo dall' <xref:System.IDisposable> interfaccia che esegue la pulizia necessaria per l'oggetto. Questo consente di migliorare notevolmente le prestazioni dell'applicazione. Anche con questo controllo esplicito sulle risorse, il finalizzatore diventa una protezione per la pulizia delle risorse se la chiamata al `Dispose` metodo ha esito negativo.  
  
 Per ulteriori informazioni sulla pulizia delle risorse, vedere gli articoli seguenti:  
  
- [Pulizia delle risorse non gestite](../../../standard/garbage-collection/unmanaged.md)  
  
- [Implementazione di un metodo Dispose](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [Istruzione using](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea tre classi che costituiscono una catena di ereditarietà. La classe `First` è la classe base, `Second` è derivata da `First` e `Third` è derivata da `Second`. Tutte e tre hanno finalizzatori. In `Main` viene creata un'istanza della classe più derivata. Durante l'esecuzione del programma, si noti che i finalizzatori delle tre classi vengono chiamati automaticamente e in ordine, dalla classe più derivata alla meno derivata.  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere la sezione [Distruttori](~/_csharplang/spec/classes.md#destructors) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable>
- [Guida per programmatori C#](../index.md)
- [Costruttori](./constructors.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
