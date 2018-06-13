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
ms.openlocfilehash: fdfc4d9e9ba3653bd1a762767e3c39a4f62e587a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582135"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="fe76e-102">Sicurezza e race condition</span><span class="sxs-lookup"><span data-stu-id="fe76e-102">Security and Race Conditions</span></span>
<span data-ttu-id="fe76e-103">Un'altra area di interesse è il rischio di protezione possano essere sfruttati da race condition.</span><span class="sxs-lookup"><span data-stu-id="fe76e-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="fe76e-104">Esistono diversi modi in cui questa situazione potrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="fe76e-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="fe76e-105">Negli argomenti che seguono descrivono alcuni aspetti problematici che lo sviluppatore deve evitare.</span><span class="sxs-lookup"><span data-stu-id="fe76e-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="fe76e-106">Race condition nel metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="fe76e-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="fe76e-107">Se una classe **Dispose** (metodo) (per ulteriori informazioni, vedere [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) non è sincronizzato, è possibile il codice di pulizia all'interno di **Dispose** può essere eseguito più di una volta, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fe76e-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fe76e-108">Poiché questo **Dispose** implementazione non è sincronizzata, è possibile per `Cleanup` di essere chiamato da un primo thread e quindi un secondo thread prima `_myObj` è impostato su **null**.</span><span class="sxs-lookup"><span data-stu-id="fe76e-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="fe76e-109">Se si tratta di un problema di sicurezza varia a seconda che cosa avviene quando il `Cleanup` viene eseguito codice.</span><span class="sxs-lookup"><span data-stu-id="fe76e-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="fe76e-110">Un problema con non sincronizzate **Dispose** implementazioni prevede l'utilizzo di handle di risorsa, ad esempio file.</span><span class="sxs-lookup"><span data-stu-id="fe76e-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="fe76e-111">Eliminazione non corretta può causare l'handle non corretto da usare, che spesso le vulnerabilità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fe76e-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="fe76e-112">Condizioni di competizione nei costruttori</span><span class="sxs-lookup"><span data-stu-id="fe76e-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="fe76e-113">In alcune applicazioni, potrebbe essere possibile che altri thread di accedere a membri della classe prima che i costruttori di classe hanno eseguito completamente.</span><span class="sxs-lookup"><span data-stu-id="fe76e-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="fe76e-114">È necessario esaminare tutti i costruttori di classe per assicurarsi che non siano presenti problemi di sicurezza se questo deve verificarsi o sincronizzare i thread se necessario.</span><span class="sxs-lookup"><span data-stu-id="fe76e-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="fe76e-115">Condizioni di competizione con gli oggetti memorizzati nella cache</span><span class="sxs-lookup"><span data-stu-id="fe76e-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="fe76e-116">Codice che memorizza nella cache le informazioni di sicurezza o che utilizza la sicurezza dall'accesso di codice [Assert](../../../docs/framework/misc/using-the-assert-method.md) operazione può essere vulnerabile a race condition se altre parti della classe non sono sincronizzati in modo appropriato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fe76e-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fe76e-117">Se sono presenti altri percorsi di `DoOtherWork` che possono essere chiamati da un altro thread con lo stesso oggetto, un chiamante non attendibile può essere aggirata da una richiesta.</span><span class="sxs-lookup"><span data-stu-id="fe76e-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="fe76e-118">Se il codice memorizza nella cache le informazioni di sicurezza, assicurarsi di verificare per questa vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="fe76e-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="fe76e-119">Condizioni di competizione nei distruttori</span><span class="sxs-lookup"><span data-stu-id="fe76e-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="fe76e-120">Le condizioni di competizione possono verificarsi anche in un oggetto che fa riferimento a una risorsa statica o non gestita che viene resa disponibile nel finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="fe76e-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="fe76e-121">Se più oggetti condividono una risorsa che viene modificata in un finalizzatore di classe, è necessario sincronizzare gli oggetti ogni accesso a tale risorsa.</span><span class="sxs-lookup"><span data-stu-id="fe76e-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe76e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe76e-122">See Also</span></span>  
 [<span data-ttu-id="fe76e-123">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="fe76e-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
