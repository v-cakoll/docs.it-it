---
title: try-catch - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 5289dbe3aff0a9e1f1024a293ff469df44d34a3b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713027"
---
# <a name="try-catch-c-reference"></a>try-catch (Riferimenti per C#)

L'istruzione try-catch è costituita da un blocco `try` seguito da una o più clausole `catch`, che specificano i gestori per eccezioni diverse.

Quando viene generata un'eccezione, Common Language Runtime(CLR) cerca l'istruzione `catch` che gestisce questa eccezione. Se il metodo attualmente in esecuzione non contiene tale blocco `catch`, CLR analizza il metodo che ha chiamato il metodo corrente e così via fino allo stack di chiamate. Se non viene trovato alcun blocco `catch`, CLR visualizza un messaggio di eccezione non gestita per l'utente e interrompe l'esecuzione del programma.

Il blocco `try` contiene il codice protetto che potrebbe generare l'eccezione. Il blocco viene eseguito fino a quando non viene generata un'eccezione o viene completato correttamente. Ad esempio, il seguente tentativo di eseguire il cast di un oggetto `null` genera l'eccezione <xref:System.NullReferenceException>:

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

Anche se la clausola `catch` può essere usata senza argomenti per intercettare qualsiasi tipo di eccezione, questo utilizzo non è consigliato. In generale, è consigliabile intercettare solo le eccezioni di cui si sa come eseguire il ripristino. È quindi opportuno specificare sempre argomento di oggetto derivato da <xref:System.Exception?displayProperty=nameWithType>, ad esempio:

```csharp
catch (InvalidCastException e)
{
}
```

È possibile usare più clausole `catch` specifiche nella stessa istruzione try-catch. In questo caso, l'ordine delle clausole `catch` è importante perché le clausole `catch` vengono esaminate nell'ordine specificato. Intercettare le eccezioni più specifiche prima di quelle meno specifiche. Il compilatore provoca un errore se si ordinano i blocchi catch in modo che un blocco successivo non possa mai essere raggiunto.

Usando gli argomenti `catch`, è possibile filtrare le eccezioni che si desidera gestire.  È anche possibile usare un filtro eccezioni per esaminare ulteriormente l'eccezione e decidere se gestirla.  Se il filtro eccezioni restituisce false, la ricerca di un gestore prosegue.

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

I filtri eccezioni sono preferibili per l'intercettazione e la rigenerazione (come illustrato di seguito) perché lasciano intatto lo stack.  Se un gestore successivo esegue il dump dello stack, è possibile visualizzare l'origine dell'eccezione, anziché solo l'ultima posizione in cui è stata rigenerata.  Un uso comune delle espressioni di filtro eccezioni è la registrazione.  È possibile creare un filtro che restituisca sempre false da visualizzare anche in un log. È possibile registrare le eccezioni mentre si verificano senza doverle gestire e rigenerare.

Un'istruzione [throw](throw.md) può essere usata in un blocco `catch` per rigenerare l'eccezione intercettata dall'istruzione `catch`. Il seguente esempio estrae le informazioni di origine da un'eccezione <xref:System.IO.IOException> e quindi genera l'eccezione per il metodo padre.

```csharp
catch (FileNotFoundException e)
{
    // FileNotFoundExceptions are handled here.
}
catch (IOException e)
{
    // Extract some information from this exception, and then 
    // throw it to the parent method.
    if (e.Source != null)
        Console.WriteLine("IOException source: {0}", e.Source);
    throw;
}
```

È possibile intercettare un'eccezione e generarne un'altra. In questo caso, specificare l'eccezione intercettata come eccezione interna, come mostrato nell'esempio seguente.

```csharp
catch (InvalidCastException e) 
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

È anche possibile generare nuovamente un'eccezione quando una determinata condizione è true, come mostrato nell'esempio seguente.

```csharp
catch (InvalidCastException e)
{
    if (e.Data == null)
    {
        throw;
    }
    else
    {
        // Take some action.
    }
}
```

> [!NOTE]
> È anche possibile usare un filtro eccezioni per ottenere un risultato simile in un modo spesso più pulito, che in più non modifichi lo stack, come descritto in precedenza in questo documento. L'esempio seguente presenta un comportamento simile al precedente per i chiamanti. La funzione restituisce `InvalidCastException` al chiamante quando `e.Data` è `null`.
> 
> ```csharp
> catch (InvalidCastException e) when (e.Data != null) 
> {
>     // Take some action.
> }
> ``` 

Da un blocco `try` inizializzare solo le variabili dichiarate al suo interno. In caso contrario, è possibile che si verifichi un'eccezione prima del completamento dell'esecuzione del blocco. Nel seguente esempio di codice, la variabile `n` viene inizializzata nel blocco `try`. Un tentativo di usare questa variabile al di fuori del blocco `try` nell'istruzione `Write(n)` genererà un errore del compilatore.

```csharp
static void Main() 
{
    int n;
    try 
    {
        // Do not initialize this variable here.
        n = 123;
    }
    catch
    {
    }
    // Error: Use of unassigned local variable 'n'.
    Console.Write(n);
}
```

Per altre informazioni su catch, vedere [try-catch-finally](try-catch-finally.md).

## <a name="exceptions-in-async-methods"></a>Eccezioni nei metodi asincroni

Un metodo asincrono viene contrassegnato da un modificatore [async](async.md) e in genere contiene una o più espressioni o istruzioni await. Un'espressione await applica l'operatore [await](../operators/await.md) a un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.

Quando il controllo raggiunge un oggetto `await` nel metodo asincrono, l'avanzamento nel metodo viene sospeso fino al completamento dell'attività attesa. Una volta completata l'attività, l'esecuzione del metodo può riprendere. Per altre informazioni, vedere [Programmazione asincrona con Async e Await](../../programming-guide/concepts/async/index.md) e [Flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md).

L'attività completata a cui viene applicato `await` può essere in uno stato di errore a causa di un'eccezione non gestita nel metodo che restituisce l'attività. L'attesa dell'attività genera un'eccezione. Un'attività può inoltre terminare con uno stato di annullamento se viene annullato il processo asincrono che la restituisce. L'attesa di un'attività annullata genera un'eccezione `OperationCanceledException`. Per altre informazioni su come annullare un processo asincrono, vedere [Ottimizzazione dell'applicazione Async](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).

Per intercettare l'eccezione, attendere l'attività in un blocco `try` e intercettare l'eccezione nel blocco `catch` associato. Per un esempio, vedere la sezione [Esempio di metodo asincrono](#async-method-example).

Un'attività può essere in uno stato di errore perché si sono verificate più eccezioni nel metodo asincrono atteso. Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, solo una delle eccezioni viene intercettata, ma non è possibile prevedere quale. Per un esempio, vedere la sezione [Esempio di Task.WhenAll](#taskwhenall-example).

## <a name="example"></a>Esempio

Nel seguente esempio, il blocco `try` contiene una chiamata al metodo `ProcessString` che potrebbe causare un'eccezione. La clausola `catch` contiene il gestore di eccezioni che visualizza solo un messaggio sullo schermo. Quando l'istruzione `throw` viene chiamata da `MyMethod`, il sistema cerca l'istruzione `catch` e visualizza il messaggio `Exception caught`.

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a>Esempio di due blocchi catch

Nell'esempio seguente, vengono usati due blocchi catch e viene intercettata l'eccezione più specifica, che è la prima.

Per intercettare l'eccezione meno specifica, è possibile sostituire l'istruzione throw in `ProcessString` con l'istruzione seguente: `throw new Exception()`.

Se nell'esempio si inserisce per primo il blocco catch meno specifico, viene visualizzato il messaggio di errore seguente: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a>Esempio di metodo asincrono

L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni. Per intercettare un'eccezione generata da un'attività asincrona, inserire l'espressione `await` in un blocco `try` e intercettare l'eccezione in un blocco `catch`.

Rimuovere il commento dalla riga `throw new Exception` nell'esempio per illustrare la gestione delle eccezioni. La proprietà `IsFaulted` dell'attività viene impostata su `True`, la proprietà `Exception.InnerException` dell'attività viene impostata sull'eccezione e l'eccezione viene intercettata nel blocco `catch`.

Rimuovere il commento dalla riga `throw new OperationCanceledException` per illustrare cosa accade quando si annulla un processo asincrono. La proprietà `IsCanceled` dell'attività viene impostata su `true` e l'eccezione viene intercettata nel blocco `catch`. In alcune condizioni che non si applicano a questo esempio, la proprietà `IsFaulted` dell'attività viene impostata su `true` e `IsCanceled` viene impostata su `false`.

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a>Esempio di Task.WhenAll

Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni. Il blocco `try` attende l'attività restituita da una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. L'attività viene completata quando vengono completate le tre attività a cui si applica WhenAll.

Ognuna delle tre attività genera un'eccezione. Il blocco `catch` scorre le eccezioni presenti nella proprietà `Exception.InnerExceptions` dell'attività restituita da <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Istruzione try](~/_csharplang/spec/statements.md#the-try-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzioni try, throw e catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-finally](try-finally.md)
- [Procedura: Come generare in modo esplicito le eccezioni](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
