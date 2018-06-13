---
title: MDA jitCompilationStart
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9643a2d2ea0967b8cf6d8e18ce2e9073ae583f71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387036"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="35492-102">MDA jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="35492-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="35492-103">L'assistente al debug gestito `jitCompilationStart` viene attivato per segnalare il momento in cui il compilatore JIT avvia la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="35492-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="35492-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="35492-104">Symptoms</span></span>  
 <span data-ttu-id="35492-105">Le dimensioni del working set per un programma che è già in formato di immagine nativa aumentano, perché mscorjit.dll viene caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="35492-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="35492-106">Causa</span><span class="sxs-lookup"><span data-stu-id="35492-106">Cause</span></span>  
 <span data-ttu-id="35492-107">Non tutti gli assembly da cui dipende il programma sono stati generati in formato nativo e quelli che lo sono non sono stati registrati correttamente.</span><span class="sxs-lookup"><span data-stu-id="35492-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="35492-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="35492-108">Resolution</span></span>  
 <span data-ttu-id="35492-109">L'abilitazione di questo assistente al debug gestito permette di determinare quale funzione è stata compilata tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="35492-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="35492-110">Determinare se l'assembly che contiene la funzione è stato generato in formato nativo e registrato correttamente.</span><span class="sxs-lookup"><span data-stu-id="35492-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="35492-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="35492-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="35492-112">Poiché questo assistente al debug gestito registra un messaggio appena prima della compilazione JIT di un metodo, la sua abilitazione ha un notevole impatto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="35492-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="35492-113">Si noti che se un metodo è inline, l'assistente al debug gestito non genera un messaggio separato.</span><span class="sxs-lookup"><span data-stu-id="35492-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="35492-114">Output</span><span class="sxs-lookup"><span data-stu-id="35492-114">Output</span></span>  
 <span data-ttu-id="35492-115">L'esempio di codice seguente mostra l'output di esempio.</span><span class="sxs-lookup"><span data-stu-id="35492-115">The following code sample shows sample output.</span></span> <span data-ttu-id="35492-116">In questo caso, l'output mostra che nell'assembly Test il metodo "m" nella classe "ns2.CO" è stato compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="35492-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="35492-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="35492-117">Configuration</span></span>  
 <span data-ttu-id="35492-118">Il file di configurazione seguente mostra diversi filtri che è possibile usare per escludere i metodi segnalati quando vengono prima compilati tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="35492-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="35492-119">È possibile specificare che devono essere segnalati tutti i metodi impostando il valore dell'attributo name su \*.</span><span class="sxs-lookup"><span data-stu-id="35492-119">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="35492-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="35492-120">Example</span></span>  
 <span data-ttu-id="35492-121">L'esempio seguente mostra il codice da usare con il file di configurazione precedente.</span><span class="sxs-lookup"><span data-stu-id="35492-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```  
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="35492-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35492-122">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="35492-123">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="35492-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="35492-124">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="35492-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
