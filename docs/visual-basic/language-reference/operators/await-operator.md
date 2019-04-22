---
title: Opertore Await (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: d9d50433e3bc24df7cda137a145ab3f0f0302a1f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841979"
---
# <a name="await-operator-visual-basic"></a>Opertore Await (Visual Basic)
Applicare l'operatore `Await` a un operando in un metodo o in un'espressione lambda asincroni per sospendere l'esecuzione del metodo finché l'attività di cui si è in attesa non viene completata. L'attività rappresenta il lavoro attualmente in fase di esecuzione.  
  
 Il metodo in cui `Await` viene usato deve avere un' [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore. Tale metodo, definito usando il modificatore `Async` e contenente di solito una o più espressioni `Await`, viene denominato *metodo asincrono*.  
  
> [!NOTE]
>  Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012. Per un'introduzione alla programmazione asincrona, vedere [programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 In genere, l'attività a cui si applica il `Await` operatore è il valore restituito da una chiamata a un metodo che implementa le [Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=204847), vale a dire una <xref:System.Threading.Tasks.Task> o un <xref:System.Threading.Tasks.Task%601>.  
  
 Nel seguente codice, l'elemento <xref:System.Net.Http.HttpClient> del metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> restituisce `getContentsTask`, un elemento `Task(Of Byte())`. L'attività è una promessa di produrre la matrice di byte effettiva una volta completata l'operazione. L'operatore `Await` viene applicato a `getContentsTask` per sospendere l'esecuzione in `SumPageSizesAsync` fino al completamento di `getContentsTask`. Nel frattempo, il controllo viene restituito al chiamante di `SumPageSizesAsync`. Quando `getContentsTask` termina, l'espressione `Await` restituisce una matrice di byte.  
  
```vb  
Private Async Function SumPageSizesAsync() As Task  
  
    ' To use the HttpClient type in desktop apps, you must include a using directive and add a   
    ' reference for the System.Net.Http namespace.  
    Dim client As HttpClient = New HttpClient()   
    ' . . .   
    Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
    Dim urlContents As Byte() = Await getContentsTask  
  
    ' Equivalently, now that you see how it works, you can write the same thing in a single line.  
    'Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ' . . .  
End Function  
```  
  
> [!IMPORTANT]
>  Per un esempio completo, vedere [Procedura dettagliata: Accesso al Web con Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). È possibile scaricare l'esempio da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per sviluppatori) del sito Web Microsoft. L'esempio è nel progetto AsyncWalkthrough_HttpClient.  
  
 Se `Await` viene applicato al risultato di una chiamata a un metodo che restituisce un elemento `Task(Of TResult)`, il tipo dell'espressione `Await` è TResult. Se `Await` viene applicato al risultato di una chiamata a un metodo che restituisce `Task`, l'espressione `Await` non restituisce un valore. Nell'esempio che segue viene illustrata la differenza.  
  
```vb  
' Await used with a method that returns a Task(Of TResult).  
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()  
  
' Await used with a method that returns a Task.  
Await AsyncMethodThatReturnsTask()  
```  
  
 Un'espressione o un'istruzione `Await` non blocca il thread su cui è in esecuzione. Comporta invece la registrazione, tramite il compilatore, della parte restante del metodo asincrono, dopo l'espressione `Await`, come continuazione dell'attività di cui si è in attesa. Il controllo quindi viene restituito al chiamante del metodo asincrono. Al termine dell'attività, ne richiama la continuazione e l'esecuzione del metodo asincrono riprende da dove era stata interrotta.  
  
 Un'espressione `Await` può trovarsi solo nel corpo di un metodo che la contiene o di un'espressione lambda contrassegnata da un modificatore `Async`. Il termine *Await* funge da parola chiave solo in tale contesto. Altrove, viene interpretata come identificatore. All'interno dell'espressione di metodo o espressione lambda asincroni, un `Await` in un'espressione di query, l'espressione non può verificarsi nel `catch` o `finally` blocco di un [Try... Catch... Infine](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) istruzione, nell'espressione variabile di controllo del ciclo di un `For` oppure `For Each` ciclo, o nel corpo di una [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) istruzione.  
  
## <a name="exceptions"></a>Eccezioni  
 La maggior parte dei metodi asincroni restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Le proprietà dell'attività restituita contengono informazioni sullo stato e sulla cronologia, ad esempio se l'attività è stata completata, se il metodo asincrono ha generato un'eccezione o è stato annullato e il risultato finale. L'operatore `Await` accede a tali proprietà.  
  
 Se si è in attesa di un metodo asincrono che restituisce un'attività che genera un'eccezione, tramite l'operatore `Await` viene rigenerata l'eccezione.  
  
 Se si è in attesa di un metodo asincrono che restituisce un'attività che è stato annullato, tramite l'operatore `Await` viene rigenerata un'eccezione <xref:System.OperationCanceledException>.  
  
 Una singola attività in uno stato di errore può rispecchiare più eccezioni.  Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, l'operazione await rigenera solo una delle eccezioni. Tuttavia, non è possibile prevedere quale delle eccezioni verrà rigenerata.  
  
 Per esempi di gestione degli errori nei metodi asincroni, vedere [Try... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="example"></a>Esempio  
 Il seguente esempio di Windows Form illustra l'uso di `Await` in un metodo asincrono, `WaitAsynchronouslyAsync`. Contrastare il comportamento di tale metodo con il comportamento di `WaitSynchronously`. Senza un operatore `Await`, `WaitSynchronously` viene eseguito in modo sincrono nonostante l'uso del modificatore `Async` nella definizione e di una chiamata a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> nel corpo.  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Procedura dettagliata: Accesso al Web con Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Async](../../../visual-basic/language-reference/modifiers/async.md)
