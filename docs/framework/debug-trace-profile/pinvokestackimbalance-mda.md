---
title: MDA pInvokeStackImbalance
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
ms.openlocfilehash: c789e8cb409bd4c59c91d6b646efe428afe7c86d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217252"
---
# <a name="pinvokestackimbalance-mda"></a>PInvokeStackImbalance (MDA)

Il `PInvokeStackImbalance` assistente al debug gestito viene attivato quando CLR rileva che la profondità dello stack dopo una chiamata platform invoke non corrisponde alla profondità dello stack prevista, in base alla convenzione di chiamata specificata nell'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> e alla dichiarazione dei parametri nella firma gestita.

L'assistente al debug gestito `PInvokeStackImbalance` viene implementato solo per piattaforme x86 a 32 bit.

> [!NOTE]
> Il `PInvokeStackImbalance` MDA è disabilitato per impostazione predefinita. In Visual Studio 2017 e versioni successive, il `PInvokeStackImbalance` MDA viene visualizzato nell'elenco **assistenti al debug gestito** nella finestra di dialogo **Impostazioni eccezioni** (visualizzata quando si seleziona **debug** > **Windows** > **Impostazioni eccezioni**). Tuttavia, la selezione o la cancellazione della casella di controllo **Interrompi quando viene generata** non Abilita o Disabilita l'assistente al debug gestito; controlla solo se Visual Studio genera un'eccezione quando viene attivato l'assistente al debug gestito.

## <a name="symptoms"></a>Sintomi

Un'applicazione rileva una violazione di accesso o un danneggiamento della memoria durante o dopo una chiamata PInvoke.

## <a name="cause"></a>Causa

La firma gestita della chiamata PInvoke potrebbe non corrispondere alla firma non gestita del metodo chiamato.  Questa mancata corrispondenza può essere causata dalla firma gestita che non dichiara il numero corretto di parametri o non specifica le dimensioni appropriate per i parametri.  L'assistente al debug gestito può essere attivato anche perché la convenzione di chiamata specificata dall'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> non corrisponde alla convenzione di chiamata non gestita.

## <a name="resolution"></a>Risoluzione

Rivedere la firma PInvoke gestita e la convenzione di chiamata per verificare la corrispondenza con la firma e la convenzione di chiamata della destinazione nativa.  Provare a specificare in modo esplicito la convenzione di chiamata su entrambi i lati, gestito e non gestito. È anche possibile, anche se improbabile, che la funzione non gestita abbia sbilanciato lo stack per altri motivi, ad esempio un bug nel compilatore non gestito.

## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione

Forza l'uso del percorso non ottimizzato in CLR per tutte le chiamate PInvoke.

## <a name="output"></a>Output

Il messaggio dell'assistente al debug gestito fornisce il nome della chiamata al metodo PInvoke che sta causando lo sbilanciamento dello stack. Un messaggio di esempio di una chiamata PInvoke al metodo `SampleMethod` è:

**Una chiamata alla funzione PInvoke ' SampleMethod ' ha sbilanciato lo stack. Questa operazione è probabilmente dovuta al fatto che la firma PInvoke gestita non corrisponde alla firma di destinazione non gestita. Verificare che la convenzione di chiamata e i parametri della firma PInvoke corrispondano alla firma non gestita di destinazione.**

## <a name="configuration"></a>Configurazione

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
