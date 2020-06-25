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
# <a name="jitcompilationstart-mda"></a>MDA jitCompilationStart

L'assistente al debug gestito `jitCompilationStart` viene attivato per segnalare il momento in cui il compilatore JIT avvia la compilazione di una funzione.  
  
## <a name="symptoms"></a>Sintomi  
 Il working set dimensioni aumenta per un programma che è già in formato di immagine nativa, perché mscorjit.dll viene caricato nel processo.  
  
## <a name="cause"></a>Causa  
Non tutti gli assembly da cui dipende il programma sono stati generati in formato nativo oppure un assembly non è registrato correttamente.  

## <a name="resolution"></a>Risoluzione  
 L'abilitazione di questo assistente al debug gestito consente di identificare la funzione compilata tramite JIT. Verificare che l'assembly che contiene la funzione venga generato in formato nativo e registrato correttamente.
  
## <a name="effect-on-the-runtime"></a>Effetto sul runtime  
 Poiché questo assistente al debug gestito registra un messaggio appena prima della compilazione JIT di un metodo, la sua abilitazione ha un notevole impatto sulle prestazioni. Se un metodo è inline, questo assistente al debug gestito non genererà un messaggio separato.  
  
## <a name="output"></a>Output  
 L'esempio di codice seguente mostra l'output di esempio. In questo caso, l'output mostra che, nel test dell'assembly, il metodo "m" sulla classe "ns2.CO" è stato compilato tramite JIT.  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a>Configurazione  
 Il file di configurazione seguente mostra diversi filtri che è possibile usare per escludere i metodi segnalati quando vengono prima compilati tramite JIT. È possibile specificare che tutti i metodi vengano segnalati impostando il valore dell'attributo Name su \* .  
  
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
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra il codice da usare con il file di configurazione precedente.  
  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
