---
title: Parametri e valori restituiti per routine multithreading (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 545da3e89d44c29c67784b5f01812d87350030c6
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874611"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Parametri e valori restituiti per routine multithreading (Visual Basic)
L'invio e la restituzione di valori in un'applicazione multithreading è un processo complesso poiché è necessario che il costruttore della classe di thread riceva un riferimento a una routine che non accetta alcun argomento e non restituisce alcun valore. Le sezioni seguenti descrivono alcuni metodi semplici per l'inserimento di parametri e la restituzione di valori da routine su thread diversi.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Inserimento di parametri per routine multithreading  
 Il modo migliore per inserire i parametri per una chiamata di metodo multithreading consiste nel racchiudere il metodo di destinazione in una classe e definire per la classe campi che verranno usati come parametri per il nuovo thread. Il vantaggio di questo approccio consiste nella possibilità di creare una nuova istanza della classe con parametri propri ogni volta che si vuole iniziare un nuovo thread. Ad esempio, si supponga di avere una funzione che calcola l'area di un triangolo come nel codice seguente:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 È possibile scrivere una classe che racchiuda la funzione `CalcArea` e crei i campi in cui memorizzare i parametri di input come segue:  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 Per usare `AreaClass`, è possibile creare un oggetto `AreaClass` e impostare le proprietà `Base` e `Height` come illustrato nel codice seguente:  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 Si noti che la routine `TestArea` non verifica il valore del campo `Area` dopo che è stato chiamato il metodo `CalcArea`. Poiché `CalcArea` viene eseguita su un thread separato, il campo `Area` non sarà necessariamente impostato se lo si controlla subito dopo avere chiamato `Thread.Start`. La sezione seguente illustra un metodo più efficace per la restituzione di valori dalle routine multithreading.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Restituzione di valori da routine multithreading  
 La restituzione di valori da routine eseguite su thread diversi è resa complessa dal fatto che le routine non possono essere funzioni e non possono usare argomenti `ByRef`. Il modo più semplice per restituire i valori consiste nell'usare il componente <xref:System.ComponentModel.BackgroundWorker> per gestire i thread e generare un evento dopo aver completato l'attività e quindi elaborare i risultati con un gestore eventi.  
  
 L'esempio seguente restituisce un valore generando un evento da una routine eseguita su un thread separato:  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 La variabile facoltativa dell'oggetto di stato `ByVal` del metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> consente di inserire parametri e restituire valori ai thread del pool di thread. Un oggetto di stato è supportato a questo scopo anche dai thread dei timer di thread. Per informazioni sul pooling dei thread e i timer di thread, vedere [pool di Thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[pool di Thread](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) e [timer](../../../../standard/threading/timers.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Multithreading con il componente BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Creazione di pool di thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [Sincronizzazione di thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Applicazioni multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Multithreading nei componenti](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
