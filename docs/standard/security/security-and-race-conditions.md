---
title: Sicurezza e race condition
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
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
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186787"
---
# <a name="security-and-race-conditions"></a>Sicurezza e race condition
Un'altra area di preoccupazione è il potenziale di falle di sicurezza sfruttate dalle condizioni di gara. Ci sono diversi modi in cui questo potrebbe accadere. I sottoargomenti che seguono delineano alcune delle principali insidie che lo sviluppatore deve evitare.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Condizioni di gara nel metodo DisposeRace Conditions in the Dispose Method  
 Se il metodo **Dispose** di una classe (per ulteriori informazioni, vedere [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) non è sincronizzato, è possibile che il codice di pulitura all'interno di **Dispose** possa essere eseguito più volte, come illustrato nell'esempio seguente.  
  
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
  
 Poiché questa implementazione **di Dispose** non `Cleanup` è sincronizzata, è possibile che `_myObj` venga chiamata prima da un thread e quindi un secondo thread prima sia impostato su **null**. Se si tratta di un problema `Cleanup` di sicurezza dipende da ciò che accade quando viene eseguito il codice. Un problema importante con le implementazioni **Dispose** non sincronizzate prevede l'utilizzo di handle di risorsa, ad esempio i file. L'eliminazione non corretta può causare l'utilizzo della maniglia errata, che spesso porta a vulnerabilità della sicurezza.  
  
## <a name="race-conditions-in-constructors"></a>Condizioni di gara nei costruttoriRace Conditions in Constructors  
 In alcune applicazioni, potrebbe essere possibile per altri thread accedere ai membri della classe prima che i relativi costruttori di classe siano stati completamente eseguiti. È consigliabile esaminare tutti i costruttori di classe per assicurarsi che non vi siano problemi di sicurezza, se ciò dovesse verificarsi, oppure sincronizzare i thread, se necessario.  
  
## <a name="race-conditions-with-cached-objects"></a>Condizioni di gara con gli oggetti memorizzati nella cacheRace Conditions with Cached Objects  
 Il codice che memorizza nella cache le informazioni di sicurezza o utilizza l'operazione [Assert](../../../docs/framework/misc/using-the-assert-method.md) di sicurezza dall'accesso di codice potrebbe anche essere vulnerabile a condizioni di gara se altre parti della classe non sono sincronizzate in modo appropriato, come illustrato nell'esempio seguente.  
  
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
  
 Se esistono altri `DoOtherWork` percorsi che possono essere chiamati da un altro thread con lo stesso oggetto, un chiamante non attendibile può sfuggire a una richiesta.  
  
 Se il codice memorizza nella cache le informazioni di sicurezza, assicurarsi di esaminarle per questa vulnerabilità.  
  
## <a name="race-conditions-in-finalizers"></a>Condizioni di gara nei finalizzatori  
 Le race condition possono verificarsi anche in un oggetto che fa riferimento a una risorsa statica o non gestita che viene quindi liberata nel finalizzatore. Se più oggetti condividono una risorsa che viene modificata nel finalizzatore di una classe, gli oggetti devono sincronizzare tutti gli accessi a tale risorsa.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
