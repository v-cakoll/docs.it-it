---
title: virtualCERCall (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
ms.openlocfilehash: a2112baed863b1035cbee4e956c1b6e271ff6e3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181717"
---
# <a name="virtualcercall-mda"></a>virtualCERCall (MDA)
L'assistente al debug gestito `virtualCERCall` viene attivato come avviso che indica che un sito di chiamata all'interno di un grafico chiamate di un'area a esecuzione vincolata fa riferimento a una destinazione virtuale, ovvero una chiamata virtuale a un metodo virtuale non finale o a una chiamata che usa un'interfaccia. Common Language Runtime (CLR) non può prevedere il metodo di destinazione di queste chiamate solo dal linguaggio intermedio e dall'analisi dei metadati. Di conseguenza, non è possibile preparare l'albero delle chiamate come parte del grafico dell'area a esecuzione vincolata e le interruzioni dei thread in tale sottoalbero non possono essere bloccate automaticamente. Questo assistente al debug gestito segnala i casi in cui un'area a esecuzione vincolata potrebbe dover essere estesa usando chiamate esplicite al metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> una volta che le informazioni aggiuntive necessarie per calcolare la destinazione della chiamata sono note in fase di esecuzione.  
  
## <a name="symptoms"></a>Sintomi  
 Le aree a esecuzione vincolata non vengono eseguite quando un thread viene interrotto o quando viene scaricato un dominio dell'applicazione.  
  
## <a name="cause"></a>Causa  
 Un'area a esecuzione vincolata contiene una chiamata a un metodo virtuale che non è possibile preparare automaticamente.  
  
## <a name="resolution"></a>Risoluzione  
 Chiamare <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> per il metodo virtuale.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
  
```output
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
  
```csharp
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
