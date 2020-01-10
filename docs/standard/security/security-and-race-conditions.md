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
ms.openlocfilehash: 8980122acdd069bc840aa09129483a1cb9a379fd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705873"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="33af4-102">Sicurezza e race condition</span><span class="sxs-lookup"><span data-stu-id="33af4-102">Security and Race Conditions</span></span>
<span data-ttu-id="33af4-103">Un'altra area di interesse è la possibilità di buchi di sicurezza sfruttati da race condition.</span><span class="sxs-lookup"><span data-stu-id="33af4-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="33af4-104">Questa situazione può verificarsi in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="33af4-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="33af4-105">Gli argomenti secondari che seguono illustrano alcune delle principali insidie che lo sviluppatore deve evitare.</span><span class="sxs-lookup"><span data-stu-id="33af4-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="33af4-106">Race condition nel metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="33af4-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="33af4-107">Se il metodo **Dispose** di una classe (per altre informazioni, vedere [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) non è sincronizzato, è possibile che il codice di pulitura all'interno di **Dispose** possa essere eseguito più di una volta, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="33af4-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="33af4-108">Poiché questa implementazione di **Dispose** non è sincronizzata, è possibile che `Cleanup` venga chiamata dal primo thread e quindi da un secondo thread prima che `_myObj` sia impostato su **null**.</span><span class="sxs-lookup"><span data-stu-id="33af4-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="33af4-109">Se questo è un problema di sicurezza, dipende da cosa accade quando viene eseguito il codice `Cleanup`.</span><span class="sxs-lookup"><span data-stu-id="33af4-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="33af4-110">Un problema importante con le implementazioni **Dispose** non sincronizzate prevede l'uso di handle di risorsa, ad esempio i file.</span><span class="sxs-lookup"><span data-stu-id="33af4-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="33af4-111">L'eliminazione non corretta può causare l'uso di un handle errato, che spesso genera vulnerabilità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="33af4-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="33af4-112">Race condition nei costruttori</span><span class="sxs-lookup"><span data-stu-id="33af4-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="33af4-113">In alcune applicazioni, è possibile che altri thread accedano ai membri della classe prima che i costruttori della classe vengano eseguiti completamente.</span><span class="sxs-lookup"><span data-stu-id="33af4-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="33af4-114">È necessario esaminare tutti i costruttori di classe per assicurarsi che non vi siano problemi di sicurezza, se necessario, o sincronizzare i thread, se necessario.</span><span class="sxs-lookup"><span data-stu-id="33af4-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="33af4-115">Race condition con oggetti memorizzati nella cache</span><span class="sxs-lookup"><span data-stu-id="33af4-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="33af4-116">Il codice che memorizza nella cache le informazioni di sicurezza o utilizza l'operazione di [asserzione](../../../docs/framework/misc/using-the-assert-method.md) di sicurezza dall'accesso di codice potrebbe essere vulnerabile alle race condition se altre parti della classe non sono sincronizzate in modo appropriato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="33af4-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="33af4-117">Se sono presenti altri percorsi da `DoOtherWork` che possono essere chiamati da un altro thread con lo stesso oggetto, un chiamante non attendibile può sfuggire a una richiesta.</span><span class="sxs-lookup"><span data-stu-id="33af4-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="33af4-118">Se il codice memorizza nella cache le informazioni di sicurezza, assicurarsi di esaminarle per questa vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="33af4-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="33af4-119">Race condition nei finalizzatori</span><span class="sxs-lookup"><span data-stu-id="33af4-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="33af4-120">Le race condition possono verificarsi anche in un oggetto che fa riferimento a una risorsa statica o non gestita che quindi libera nel finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="33af4-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="33af4-121">Se più oggetti condividono una risorsa che viene modificata nel finalizzatore di una classe, gli oggetti devono sincronizzare tutti gli accessi a tale risorsa.</span><span class="sxs-lookup"><span data-stu-id="33af4-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33af4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33af4-122">See also</span></span>

- [<span data-ttu-id="33af4-123">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="33af4-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
