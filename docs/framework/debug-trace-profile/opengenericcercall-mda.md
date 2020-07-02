---
title: openGenericCERCall (MDA)
description: Vedere l'assistente al debug gestito openGenericCERCall, che può essere attivato se il codice CER non viene eseguito quando un thread viene interrotto o quando viene scaricato un dominio dell'applicazione.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: 4df33b0cdf9759edec47f02b3feb671d03284ec8
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803937"
---
# <a name="opengenericcercall-mda"></a>openGenericCERCall (MDA)

L'assistente al debug gestito `openGenericCERCall` viene attivato per avvisare che il grafico dell'area a esecuzione vincolata con variabili di tipo generico in corrispondenza del metodo radice viene elaborato in fase di compilazione JIT o di generazione delle immagini native e almeno una delle variabili di tipo generico è un tipo riferimento oggetto.

## <a name="symptoms"></a>Sintomi

Il codice dell'area a esecuzione vincolata non viene eseguito quando un thread viene interrotto o quando viene scaricato un dominio dell'applicazione.

## <a name="cause"></a>Causa

In fase di compilazione JIT, la creazione di un'istanza che contiene un tipo riferimento oggetto è rappresentativa solo perché il codice risultante è condiviso e ognuna delle variabili di tipo riferimento oggetto potrebbe essere qualsiasi tipo riferimento oggetto. Ciò può impedire la preparazione anticipata di alcune risorse in fase di esecuzione.

In particolare, i metodi con variabili di tipo generico possono allocare risorse in background in modo differito. Queste sono note come voci di dizionario generiche. Ad esempio, per l'istruzione in `List<T> list = new List<T>();` cui `T` è una variabile di tipo generico, è necessario che il runtime cerchi la ricerca ed eventualmente crei l'esatta creazione di un'istanza in fase di esecuzione, ad esempio, `List<Object>, List<String>` e così via. Questa operazione può non riuscire per svariati motivi non sotto il controllo dello sviluppatore, ad esempio memoria insufficiente.

Questo assistente al debug gestito deve essere attivato solo in fase di compilazione JIT e non quando è prevista la creazione di un'istanza esatta.

Quando viene attivato questo assistente al debug gestito, i sintomi più probabili sono il mancato funzionamento delle aree a esecuzione vincolata per le creazioni di istanze non valide. In effetti, il runtime non ha tentato di implementare un'area a esecuzione vincolata nelle circostanze che hanno causato l'attivazione dell'assistente al debug gestito. Pertanto, se lo sviluppatore usa la creazione d'istanza condivisa dell'area a esecuzione vincolata, gli errori di compilazione JIT, gli errori di caricamento di tipi generici o le interruzioni di thread all'interno dell'area a esecuzione vincolata prevista non vengono intercettati.

## <a name="resolution"></a>Soluzione

Non usare variabili di tipo generico che sono di tipo riferimento oggetto per i metodi che possono contenere un'area a esecuzione vincolata.

## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione

L'assistente al debug gestito non ha alcun effetto su CLR.

## <a name="output"></a>Output

Di seguito è riportato un esempio di output di questo assistente al debug gestito:
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution.
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a>Configurazione

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a>Esempio

Il codice dell'area a esecuzione vincolata non viene eseguito.

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
