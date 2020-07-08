---
title: MDA marshalling
description: Esaminare l'assistente al debug gestito di marshalling, che viene richiamato se CLR configura le informazioni di marshalling per un parametro del metodo o un campo della struttura.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: 77811c526d1770b91b14aa1199dfc7b3177e6c59
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051155"
---
# <a name="marshaling-mda"></a><span data-ttu-id="cbaeb-103">MDA marshalling</span><span class="sxs-lookup"><span data-stu-id="cbaeb-103">marshaling MDA</span></span>
<span data-ttu-id="cbaeb-104">L'assistente al debug gestito `marshaling` viene attivato quando CLR configura le informazioni di marshalling per un parametro di un metodo o un campo di una struttura.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-104">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="cbaeb-105">Questo assistente al debug gestito non funziona per gli assembly con compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-105">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cbaeb-106">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="cbaeb-106">Effect on the Runtime</span></span>  
 <span data-ttu-id="cbaeb-107">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-107">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cbaeb-108">Output</span><span class="sxs-lookup"><span data-stu-id="cbaeb-108">Output</span></span>  
 <span data-ttu-id="cbaeb-109">L'assistente al debug gestito visualizza il tipo del parametro o del campo nei contesti gestiti e non gestiti e la struttura o il metodo contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-109">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="cbaeb-110">Di seguito viene riportato un esempio di output per un campo.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-110">The following is an example of the output for a field:</span></span>  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="cbaeb-111">Configurazione</span><span class="sxs-lookup"><span data-stu-id="cbaeb-111">Configuration</span></span>  
 <span data-ttu-id="cbaeb-112">La configurazione dell'assistente al debug gestito consente di filtrare le informazioni di marshalling restituite in base ai nomi dei campi o dei metodi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-112">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="cbaeb-113">Il seguente esempio mostra l'uso degli elementi `methodFilter`, `fieldFilter`e `match` per specificare i filtri.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-113">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="cbaeb-114">L'impostazione dell' `name` attributo su un asterisco ( \* ) corrisponderà a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-114">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cbaeb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbaeb-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="cbaeb-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="cbaeb-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="cbaeb-117">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cbaeb-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
