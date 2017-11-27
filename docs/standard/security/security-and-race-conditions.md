---
title: Sicurezza e race condition
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
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c092113f670c5799d98dcb13c9c713bbd1a47fb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-race-conditions"></a>Sicurezza e race condition
Un'altra area di interesse è il rischio di protezione possano essere sfruttati da race condition. Esistono diversi modi in cui questa situazione potrebbe verificarsi. Negli argomenti che seguono descrivono alcuni aspetti problematici che lo sviluppatore deve evitare.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Race condition nel metodo Dispose  
 Se una classe **Dispose** (metodo) (per ulteriori informazioni, vedere [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) non è sincronizzato, è possibile il codice di pulizia all'interno di **Dispose** può essere eseguito più di una volta, come illustrato nell'esempio seguente.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Poiché questo **Dispose** implementazione non è sincronizzata, è possibile per `Cleanup` di essere chiamato da un primo thread e quindi un secondo thread prima `_myObj` è impostato su **null**. Se si tratta di un problema di sicurezza varia a seconda che cosa avviene quando il `Cleanup` viene eseguito codice. Un problema con non sincronizzate **Dispose** implementazioni prevede l'utilizzo di handle di risorsa, ad esempio file. Eliminazione non corretta può causare l'handle non corretto da usare, che spesso le vulnerabilità di sicurezza.  
  
## <a name="race-conditions-in-constructors"></a>Condizioni di competizione nei costruttori  
 In alcune applicazioni, potrebbe essere possibile che altri thread di accedere a membri della classe prima che i costruttori di classe hanno eseguito completamente. È necessario esaminare tutti i costruttori di classe per assicurarsi che non siano presenti problemi di sicurezza se questo deve verificarsi o sincronizzare i thread se necessario.  
  
## <a name="race-conditions-with-cached-objects"></a>Condizioni di competizione con gli oggetti memorizzati nella cache  
 Codice che memorizza nella cache le informazioni di sicurezza o che utilizza la sicurezza dall'accesso di codice [Assert](../../../docs/framework/misc/using-the-assert-method.md) operazione può essere vulnerabile a race condition se altre parti della classe non sono sincronizzati in modo appropriato, come illustrato nell'esempio seguente.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 Se sono presenti altri percorsi di `DoOtherWork` che possono essere chiamati da un altro thread con lo stesso oggetto, un chiamante non attendibile può essere aggirata da una richiesta.  
  
 Se il codice memorizza nella cache le informazioni di sicurezza, assicurarsi di verificare per questa vulnerabilità.  
  
## <a name="race-conditions-in-finalizers"></a>Condizioni di competizione nei distruttori  
 Le condizioni di competizione possono verificarsi anche in un oggetto che fa riferimento a una risorsa statica o non gestita che viene resa disponibile nel finalizzatore. Se più oggetti condividono una risorsa che viene modificata in un finalizzatore di classe, è necessario sincronizzare gli oggetti ogni accesso a tale risorsa.  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
