---
title: MDA dirtyCastAndCallOnInterface
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a28820479ca15ad72475ae9a7754bbbf99ce5c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108589"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="9ed2d-102">MDA dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="9ed2d-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="9ed2d-103">L'assistente al debug gestito `dirtyCastAndCallOnInterface` viene attivato quando viene tentata una chiamata ad associazione anticipata attraverso un vtable su un'interfaccia di classe contrassegnata solo per l'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9ed2d-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="9ed2d-104">Symptoms</span></span>  
 <span data-ttu-id="9ed2d-105">Un'applicazione genera una violazione di accesso o ha un comportamento imprevisto quando si inserisce in CLR una chiamata ad associazione anticipata tramite COM.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9ed2d-106">Causa</span><span class="sxs-lookup"><span data-stu-id="9ed2d-106">Cause</span></span>  
 <span data-ttu-id="9ed2d-107">Il codice sta tentando una chiamata ad associazione anticipata attraverso un vtable tramite un'interfaccia di classe solo ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="9ed2d-108">Si noti che, per impostazione predefinita, le interfacce di classe vengono identificate solo come ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="9ed2d-109">Possono essere identificate come ad associazione tardiva anche con l'attributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> con un valore <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span><span class="sxs-lookup"><span data-stu-id="9ed2d-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9ed2d-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="9ed2d-110">Resolution</span></span>  
 <span data-ttu-id="9ed2d-111">La soluzione consigliata prevede di definire un'interfaccia esplicita da usare con COM e di fare in modo che i client COM chiamino tramite questa interfaccia invece che tramite l'interfaccia di classe generata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="9ed2d-112">In alternativa, è possibile trasformare la chiamata da COM in una chiamata ad associazione tardiva mediante `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="9ed2d-113">Infine, è possibile identificare la classe come <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) per consentire alle chiamate ad associazione anticipata di essere inserite da COM. Tuttavia, l'uso di <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> è fortemente sconsigliato a causa delle limitazioni nel controllo delle versioni descritte in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9ed2d-114">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="9ed2d-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="9ed2d-115">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="9ed2d-116">Segnala solo i dati sulle chiamate ad associazione anticipata sulle interfacce ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9ed2d-117">Output</span><span class="sxs-lookup"><span data-stu-id="9ed2d-117">Output</span></span>  
 <span data-ttu-id="9ed2d-118">Nome del metodo o nome del campo a cui si accede con associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="9ed2d-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9ed2d-119">Configurazione</span><span class="sxs-lookup"><span data-stu-id="9ed2d-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ed2d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed2d-120">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="9ed2d-121">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="9ed2d-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
