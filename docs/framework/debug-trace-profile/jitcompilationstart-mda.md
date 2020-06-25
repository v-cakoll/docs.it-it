---
title: Assistente al debug gestito jitCompilationStart
description: L'assistente al debug gestito jitCompilationStart segnala quando il compilatore just-in-time (JIT) inizia a compilare una funzione .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: 13e20c1a940b7bfa777245ba35f3cc1b003d15b2
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325531"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="40528-103">MDA jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="40528-103">jitCompilationStart MDA</span></span>

<span data-ttu-id="40528-104">L'assistente al debug gestito `jitCompilationStart` viene attivato per segnalare il momento in cui il compilatore JIT avvia la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="40528-104">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="40528-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="40528-105">Symptoms</span></span>  
 <span data-ttu-id="40528-106">Il working set dimensioni aumenta per un programma che è già in formato di immagine nativa, perché mscorjit.dll viene caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="40528-106">The working set size increases for a program that's already in native image format, because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="40528-107">Causa</span><span class="sxs-lookup"><span data-stu-id="40528-107">Cause</span></span>  
<span data-ttu-id="40528-108">Non tutti gli assembly da cui dipende il programma sono stati generati in formato nativo oppure un assembly non è registrato correttamente.</span><span class="sxs-lookup"><span data-stu-id="40528-108">Not all the assemblies the program depends on have been generated into native format, or an assembly is not registered correctly.</span></span>  

## <a name="resolution"></a><span data-ttu-id="40528-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="40528-109">Resolution</span></span>  
 <span data-ttu-id="40528-110">L'abilitazione di questo assistente al debug gestito consente di identificare la funzione compilata tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="40528-110">Enabling this MDA allows you to identify which function is being JIT-compiled.</span></span> <span data-ttu-id="40528-111">Verificare che l'assembly che contiene la funzione venga generato in formato nativo e registrato correttamente.</span><span class="sxs-lookup"><span data-stu-id="40528-111">Make sure that the assembly that contains the function is generated to native format and properly registered.</span></span>
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="40528-112">Effetto sul runtime</span><span class="sxs-lookup"><span data-stu-id="40528-112">Effect on the runtime</span></span>  
 <span data-ttu-id="40528-113">Poiché questo assistente al debug gestito registra un messaggio appena prima della compilazione JIT di un metodo, la sua abilitazione ha un notevole impatto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="40528-113">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="40528-114">Se un metodo è inline, questo assistente al debug gestito non genererà un messaggio separato.</span><span class="sxs-lookup"><span data-stu-id="40528-114">If a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="40528-115">Output</span><span class="sxs-lookup"><span data-stu-id="40528-115">Output</span></span>  
 <span data-ttu-id="40528-116">L'esempio di codice seguente mostra l'output di esempio.</span><span class="sxs-lookup"><span data-stu-id="40528-116">The following code sample shows sample output.</span></span> <span data-ttu-id="40528-117">In questo caso, l'output mostra che, nel test dell'assembly, il metodo "m" sulla classe "ns2.CO" è stato compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="40528-117">In this case, the output shows that, in assembly Test, the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="40528-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="40528-118">Configuration</span></span>  
 <span data-ttu-id="40528-119">Il file di configurazione seguente mostra diversi filtri che è possibile usare per escludere i metodi segnalati quando vengono prima compilati tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="40528-119">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="40528-120">È possibile specificare che tutti i metodi vengano segnalati impostando il valore dell'attributo Name su \* .</span><span class="sxs-lookup"><span data-stu-id="40528-120">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="40528-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="40528-121">Example</span></span>  
 <span data-ttu-id="40528-122">L'esempio seguente mostra il codice da usare con il file di configurazione precedente.</span><span class="sxs-lookup"><span data-stu-id="40528-122">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="40528-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="40528-123">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="40528-124">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="40528-124">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="40528-125">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="40528-125">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
