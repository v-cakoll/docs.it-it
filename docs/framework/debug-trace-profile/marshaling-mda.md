---
title: MDA marshalling
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: f7bb630d3a1e832cf6bf083ce4cf603034248ceb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217326"
---
# <a name="marshaling-mda"></a><span data-ttu-id="8d665-102">MDA marshalling</span><span class="sxs-lookup"><span data-stu-id="8d665-102">marshaling MDA</span></span>
<span data-ttu-id="8d665-103">L'assistente al debug gestito `marshaling` viene attivato quando CLR configura le informazioni di marshalling per un parametro di un metodo o un campo di una struttura.</span><span class="sxs-lookup"><span data-stu-id="8d665-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="8d665-104">Questo assistente al debug gestito non funziona per gli assembly con compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="8d665-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8d665-105">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8d665-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="8d665-106">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="8d665-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8d665-107">Output</span><span class="sxs-lookup"><span data-stu-id="8d665-107">Output</span></span>  
 <span data-ttu-id="8d665-108">L'assistente al debug gestito visualizza il tipo del parametro o del campo nei contesti gestiti e non gestiti e la struttura o il metodo contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="8d665-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="8d665-109">Di seguito viene riportato un esempio di output per un campo.</span><span class="sxs-lookup"><span data-stu-id="8d665-109">The following is an example of the output for a field:</span></span>  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="8d665-110">Configurazione</span><span class="sxs-lookup"><span data-stu-id="8d665-110">Configuration</span></span>  
 <span data-ttu-id="8d665-111">La configurazione dell'assistente al debug gestito consente di filtrare le informazioni di marshalling restituite in base ai nomi dei campi o dei metodi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="8d665-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="8d665-112">Il seguente esempio mostra l'uso degli elementi `methodFilter`, `fieldFilter`e `match` per specificare i filtri.</span><span class="sxs-lookup"><span data-stu-id="8d665-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="8d665-113">L'impostazione dell'attributo `name` su un asterisco (\*) corrisponderà a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="8d665-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d665-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d665-114">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8d665-115">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="8d665-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8d665-116">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="8d665-116">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
