---
title: 'Procedura: chiamare un servizio Web in modo asincrono (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: 8968eaa8edd8dee177906a6c801f2f46c2a740d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a>Procedura: chiamare un servizio Web in modo asincrono (Visual Basic)
Questo esempio associa un gestore a un evento gestore asincrono di un servizio Web in modo che possa recuperare il risultato di una chiamata di metodo sincrono. L'esempio usa il servizio Web DemoTemperatureService disponibile all'indirizzo http://www.xmethods.net.  
  
 Quando in un progetto si fa riferimento a un servizio Web nell'ambiente di sviluppo integrato (IDE, Integrated Development Environment) di Visual Studio, questo viene aggiunto all'oggetto `My.WebServices` e l'IDE genera una classe proxy del client per accedere a un servizio Web specifico  
  
 La classe proxy consente di chiamare i metodi del servizio Web in modo sincrono; in altre parole l'applicazione aspetta che la funzione sia terminata. Inoltre, il proxy crea membri aggiuntivi che contribuiscono a chiamare il metodo in modo asincrono. Per ogni funzione di servizio Web, *NameOfWebServiceFunction*, il proxy crea una subroutine *NameOfWebServiceFunction*`Async`, un evento *NameOfWebServiceFunction*`Completed` e una classe *NameOfWebServiceFunction*`CompletedEventArgs`. L'esempio dimostra come usare i membri asincroni per accedere alla funzione `getTemp` del servizio Web DemoTemperatureService.  
  
> [!NOTE]
>  Tale codice non funziona nelle applicazioni Web perché ASP.NET non supporta l'oggetto `My.WebServices`.  
  
### <a name="to-call-a-web-service-asynchronously"></a>Per chiamare un servizio Web in modo asincrono  
  
1.  Fare riferimento al servizio Web DemoTemperatureService Web in http://www.xmethods.net. L'indirizzo è  
  
    ```  
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl  
    ```  
  
2.  Aggiungere un gestore eventi per l'evento `getTempCompleted`:  
  
    ```  
    Private Sub getTempCompletedHandler(ByVal sender As Object,   
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)  
  
        MsgBox("Temperature: " & e.Result)  
    End Sub  
    ```  
  
    > [!NOTE]
    >  Non è possibile usare l'istruzione `Handles` per associare un gestore eventi agli eventi dell'oggetto `My.WebServices`.  
  
3.  Aggiungere un campo di cui tenere traccia se il gestore eventi è stato aggiunto all'evento `getTempCompleted`:  
  
    ```  
    Private handlerAttached As Boolean = False  
    ```  
  
4.  Aggiungere un metodo che consenta di aggiungere, se necessario, il gestore eventi all'evento `getTempCompleted` e di chiamare il metodo `getTempAsynch`:  
  
    ```  
    Sub CallGetTempAsync(ByVal zipCode As Integer)  
        If Not handlerAttached Then  
            AddHandler My.WebServices.  
                TemperatureService.getTempCompleted,   
                AddressOf Me.TS_getTempCompleted  
            handlerAttached = True  
        End If  
        My.WebServices.TemperatureService.getTempAsync(zipCode)  
    End Sub  
    ```  
  
     Per chiamare il metodo Web `getTemp` in modo asincrono, chiamare il metodo `CallGetTempAsync`. Al termine dell'esecuzione del metodo Web il relativo valore restituito viene passato al gestore eventi `getTempCompletedHandler`.  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)  
 [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
