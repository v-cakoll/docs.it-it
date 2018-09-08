---
title: Sicurezza e race condition
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138942"
---
# <a name="security-and-race-conditions"></a>Sicurezza e race condition
Un'altra area di interesse è il rischio di sicurezza possano essere sfruttati da situazioni di race condition. Esistono diversi modi in cui questo può verificarsi. Negli argomenti che seguono illustrano alcuni aspetti problematici che lo sviluppatore deve evitare.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Le race condition nel metodo Dispose  
 Se una classe **Dispose** (metodo) (per altre informazioni, vedere [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) non è sincronizzato, è possibile che il codice di pulitura all'interno **Dispose** può essere eseguito più di una volta, come illustrato nell'esempio seguente.  
  
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
    if (myObj != null)   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Perché ciò **Dispose** implementazione non è sincronizzata, è possibile `Cleanup` deve essere chiamato da un primo thread e quindi un secondo thread prima `_myObj` è impostata su **null**. Se si tratta di una questione di sicurezza varia a seconda che cosa accade quando il `Cleanup` codice viene eseguito. Un problema principale con non sincronizzate **Dispose** implementazioni prevede l'uso degli handle di risorsa, ad esempio i file. Eliminazione non corretta può causare l'handle non corretto da usare, che spesso comporta le vulnerabilità di sicurezza.  
  
## <a name="race-conditions-in-constructors"></a>Condizioni di competizione nei costruttori  
 In alcune applicazioni, potrebbe essere possibile accedere ai membri della classe prima che i costruttori di classe sono completata l'esecuzione di altri thread. È consigliabile esaminare tutti i costruttori della classe per assicurarsi che non siano presenti problemi di sicurezza se questo deve verificarsi o sincronizzare i thread se necessario.  
  
## <a name="race-conditions-with-cached-objects"></a>Le race condition con gli oggetti memorizzati nella cache  
 Il codice che memorizza nella cache le informazioni di sicurezza o Usa la sicurezza dall'accesso di codice [Assert](../../../docs/framework/misc/using-the-assert-method.md) operazione può essere vulnerabile a situazioni di race condition se altre parti della classe non sono sincronizzati in modo appropriato, come illustrato nell'esempio seguente.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
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
    if (SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()   
{  
    if (fCallersOK)   
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
  
 Se sono presenti altri percorsi `DoOtherWork` che può essere chiamato da un altro thread con lo stesso oggetto, un chiamante non attendibile può essere aggirata da una richiesta.  
  
 Se il codice memorizza nella cache le informazioni di sicurezza, assicurarsi che esaminarlo per questa vulnerabilità.  
  
## <a name="race-conditions-in-finalizers"></a>Condizioni di competizione nei finalizzatori  
 Le race condition possono verificarsi anche in un oggetto che fa riferimento a una risorsa statica o non gestita che viene resa disponibile nel relativo finalizzatore. Se più oggetti condividono una risorsa che verrà modificata in un finalizzatore di classe, è necessario sincronizzare gli oggetti tutti gli accessi alla risorsa.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
