---
title: async (Riferimenti per C#)
ms.date: 05/22/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: 52
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2ddbd0f7268dd5dae4095d661cf800b5b481cbbd
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="async-c-reference"></a>async (Riferimenti per C#)
Usare il modificatore `async` per specificare che un metodo, un'[espressione lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) o un [metodo anonimo](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) sia asincrono. Se si usa questo modificatore in un metodo o in un'espressione, viene indicato come *metodo asincrono*. L'esempio seguente definisce un metodo asincrono denominato `ExampleMethodAsync`: 
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  
 
Se non si ha esperienza di programmazione asincrona o non si sa in che modo un metodo asincrono usa la parola chiave `await` per eseguire attività potenzialmente prolungate senza bloccare il thread del chiamante, leggere l'introduzione in [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md). Il codice seguente si trova all'interno di un metodo asincrono e chiama il metodo <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>: 
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
Un metodo asincrono viene eseguito in modo sincrono finché non raggiunge la prima espressione `await`. A quel punto, il metodo viene sospeso fino al completamento dell'attività attesa. Nel frattempo il controllo torna al chiamante del metodo, come illustrato nell'esempio della sezione successiva.  
  
Il metodo modificato dalla parola chiave `async` viene eseguito in modo sincrono se non contiene un'espressione o un'istruzione `await`. Un avviso del compilatore segnala eventuali metodi asincroni che non contengono istruzioni `await`, perché questa situazione potrebbe indicare un errore. Vedere [Avviso del compilatore (livello 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).  
  
 La parola chiave `async` è contestuale, in quanto è una parola chiave solo quando modifica un metodo, un'espressione lambda o un metodo anonimo. In tutti gli altri contesti, viene interpretato come identificatore.  
  
## <a name="example"></a>Esempio  
Nell'esempio seguente vengono illustrati la struttura e il flusso di controllo tra un gestore eventi asincrono, `StartButton_Click`, e un metodo asincrono, `ExampleMethodAsync`. Il risultato ottenuto dal metodo asincrono è il numero di caratteri di una pagina Web. Il codice è adatto per un'applicazione Windows Presentation Foundation (WPF) o un'app di Windows Store creata in Visual Studio. Vedere i commenti del codice per l'installazione dell'applicazione.  

È possibile eseguire questo codice in Visual Studio come un'app Windows Presentation Foundation (WPF) o un'app di Windows Store. Sono necessari un controllo Button denominato `StartButton` e un controllo Textbox denominato `ResultsTextBox`. Ricordare di impostare i nomi e il gestore in modo da ottenere codice simile al seguente:  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
Per eseguire il codice come app WPF:  

- Incollare il codice nella classe `MainWindow` in MainWindow.xaml.cs.  
- Aggiungere un riferimento a System.Net.Http.  
- Aggiungere una direttiva `using` per System.Net.Http.  
  
Per eseguire il codice come app di Windows Store:  
- Incollare questo codice nella classe `MainPage` in MainPage.xaml.cs.  
- Aggiungere direttive using per System.Net.Http e System.Threading.Tasks.  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
>  Per altre informazioni sulle attività e sul codice eseguito in attesa di un'attività, vedere [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md). Per un esempio di WPF completo che usa elementi simili, vedere [Procedura dettagliata: accesso al Web tramite async e await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
## <a name="return-types"></a>Tipi restituiti  
Un metodo asincrono può avere i tipi restituiti seguenti:

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- [void](../../../csharp/language-reference/keywords/void.md), che deve essere usato solo per i gestori eventi.
- A partire da C# 7, qualsiasi tipo con un metodo `GetAwaiter` accessibile. Il tipo `System.Threading.Tasks.ValueTask<TResult>` è una di queste implementazioni ed è disponibile aggiungendo il pacchetto NuGet `System.Threading.Tasks.Extensions`. 

Un metodo asincrono non può dichiarare parametri [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) e nemmeno avere un [valore di riferimento restituito ](../../programming-guide/classes-and-structs/ref-returns.md), ma può chiamare metodi con tali parametri.  
  
Specificare `Task<TResult>` come tipo restituito di un metodo asincrono se l'istruzione [return](../../../csharp/language-reference/keywords/return.md) del metodo specifica un operando di tipo `TResult`. Utilizzare `Task` se non viene restituito alcun valore significativo al completamento del metodo. Ciò significa che una chiamata al metodo restituisce `Task`, ma al completamento di `Task`, qualsiasi espressione `await` in attesa di `Task` restituisce `void`.  
  
Utilizzare il tipo restituito `void` principalmente per definire gestori eventi, che richiedono tale tipo restituito. Il chiamante di un metodo asincrono che restituisce `void` non può attendere il metodo e non può acquisire eccezioni generate dal metodo.  

A partire da C# 7, si restituisce a un altro tipo, in genere un tipo valore, che ha un metodo `GetAwaiter` per ridurre al minimo le allocazioni di memoria nelle sezioni del codice critiche per le prestazioni. 

Per altre informazioni ed esempi, vedere [Tipi restituiti asincroni](../../../csharp/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [await](../../../csharp/language-reference/keywords/await.md)  
 [Procedura dettagliata: Accesso al Web tramite Async e Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md)
