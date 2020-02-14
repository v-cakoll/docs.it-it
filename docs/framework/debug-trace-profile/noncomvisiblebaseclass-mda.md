---
title: nonComVisibleBaseClass (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: b46d5c6ffbf12efbae113a95bbfccd5742ec9ec9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217292"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="a9597-102">nonComVisibleBaseClass (MDA)</span><span class="sxs-lookup"><span data-stu-id="a9597-102">nonComVisibleBaseClass MDA</span></span>
<span data-ttu-id="a9597-103">L'assistente al debug gestito `nonComVisibleBaseClass` viene attivato quando viene effettuata una chiamata `QueryInterface` da codice nativo o non gestito nel CCW (COM Callable Wrapper) di una classe gestita visibile a COM, che deriva da una classe di base non visibile a COM.</span><span class="sxs-lookup"><span data-stu-id="a9597-103">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="a9597-104">La chiamata `QueryInterface` determina l'attivazione dell'assistente al debug gestito solo nei casi in cui la chiamata richiede l'interfaccia di classe o l'interfaccia `IDispatch` predefinita della classe gestita visibile a COM.</span><span class="sxs-lookup"><span data-stu-id="a9597-104">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="a9597-105">L'assistente al debug gestito non viene attivato quando la chiamata `QueryInterface` è destinata a un'interfaccia esplicita alla quale è applicato l'attributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> ed è implementata esplicitamente dalla classe visibile a COM.</span><span class="sxs-lookup"><span data-stu-id="a9597-105">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a9597-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="a9597-106">Symptoms</span></span>  
 <span data-ttu-id="a9597-107">Viene effettuata una chiamata `QueryInterface` da codice nativo che restituisce l'errore COR_E_INVALIDOPERATION HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a9597-107">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="a9597-108">L'errore HRESULT potrebbe essere causato dal fatto che Common Language Runtime non consente chiamate `QueryInterface` che comporterebbero l'attivazione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="a9597-108">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a9597-109">Causa</span><span class="sxs-lookup"><span data-stu-id="a9597-109">Cause</span></span>  
 <span data-ttu-id="a9597-110">Per evitare potenziali problemi di controllo delle versioni, il runtime non consente chiamate `QueryInterface` per l'interfaccia di classe o l'interfaccia `IDispatch` predefinita di una classe visibile a COM, che deriva da una classe non visibile a COM.</span><span class="sxs-lookup"><span data-stu-id="a9597-110">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="a9597-111">Ad esempio, se sono stati aggiunti membri pubblici alla classe di base non visibile a COM, i client COM esistenti che usano la classe derivata potrebbero interrompersi, perché la vtable della classe derivata, che contiene i membri della classe di base, verrebbe alterata da una tale modifica.</span><span class="sxs-lookup"><span data-stu-id="a9597-111">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="a9597-112">Le interfacce esplicite esposte a COM non presentano questo problema, perché non includono i membri di base delle interfacce nella vtable.</span><span class="sxs-lookup"><span data-stu-id="a9597-112">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a9597-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="a9597-113">Resolution</span></span>  
 <span data-ttu-id="a9597-114">Non esporre l'interfaccia della classe.</span><span class="sxs-lookup"><span data-stu-id="a9597-114">Do not expose the class interface.</span></span> <span data-ttu-id="a9597-115">Definire un'interfaccia esplicita e applicarvi l'attributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a9597-115">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a9597-116">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="a9597-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="a9597-117">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="a9597-117">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a9597-118">Output</span><span class="sxs-lookup"><span data-stu-id="a9597-118">Output</span></span>  
 <span data-ttu-id="a9597-119">Di seguito è riportato un messaggio di esempio relativo a una chiamata `QueryInterface` su una classe `Derived` visibile a COM che deriva da una classe `Base` non visibile a COM.</span><span class="sxs-lookup"><span data-stu-id="a9597-119">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```output
A QueryInterface call was made requesting the class interface of COM   
visible managed class 'Derived'. However since this class derives from   
non COM visible class 'Base', the QueryInterface call will fail. This   
is done to prevent the non COM visible base class from being   
constrained by the COM versioning rules.   
```  
  
## <a name="configuration"></a><span data-ttu-id="a9597-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="a9597-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9597-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9597-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a9597-122">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="a9597-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a9597-123">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a9597-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
