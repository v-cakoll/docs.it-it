---
title: Implementare un metodo Dispose
ms.date: 05/27/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: a16034b074b518b25244c47a7d00cb484e145c6e
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307020"
---
# <a name="implement-a-dispose-method"></a>Implementare un metodo Dispose

L'implementazione del <xref:System.IDisposable.Dispose%2A> metodo è principalmente per rilasciare le risorse non gestite usate dal codice. Quando si lavora con membri di istanza che sono <xref:System.IDisposable> implementazioni, le chiamate a cascata sono comuni <xref:System.IDisposable.Dispose%2A> . Esistono altri motivi per l'implementazione di <xref:System.IDisposable.Dispose%2A> , ad esempio l'annullamento di un'operazione eseguita in precedenza. Ad esempio, liberando la memoria allocata, rimuovendo un elemento da una raccolta che è stata aggiunta, segnalando il rilascio di un blocco acquisito e così via.

Il [Garbage Collector .NET](index.md) non alloca o rilascia la memoria non gestita. Il modello per l'eliminazione di un oggetto, definito come modello Dispose, impone un ordine per la durata di un oggetto. Il modello Dispose viene usato per gli oggetti che implementano l' <xref:System.IDisposable> interfaccia ed è comune quando si interagisce con handle di file e pipe, handle del registro di sistema, handle di attesa o puntatori a blocchi di memoria non gestita. Questo perché il Garbage Collector non è in grado di recuperare gli oggetti non gestiti.

Per garantire che le risorse vengano sempre pulite correttamente, un <xref:System.IDisposable.Dispose%2A> metodo deve essere idempotente, in modo che sia possibile chiamarlo più volte senza generare un'eccezione. Inoltre, le chiamate successive di <xref:System.IDisposable.Dispose%2A> non devono eseguire alcuna operazione.

Nell'esempio di codice fornito per il <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> metodo viene illustrato come Garbage Collection possibile causare l'esecuzione di un finalizzatore, mentre un riferimento non gestito all'oggetto o ai relativi membri è ancora in uso. Potrebbe essere utile usare <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> per rendere l'oggetto non idoneo per Garbage Collection dall'inizio della routine corrente fino al punto in cui viene chiamato il metodo.

## <a name="safe-handles"></a>Handle sicuri

La scrittura di codice per il finalizzatore di un oggetto è un'attività complessa che può causare problemi se non eseguita correttamente. È pertanto consigliabile costruire oggetti <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> anziché implementare un finalizzatore.

Un <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> è un tipo gestito astratto che esegue il wrapping di un oggetto <xref:System.IntPtr?displayProperty=nameWithType> che identifica una risorsa non gestita. In Windows è possibile che identifichi un handle in UNIX, un descrittore di file. Fornisce tutta la logica necessaria per garantire che questa risorsa venga rilasciata una sola volta, quando l'oggetto `SafeHandle` viene eliminato o quando tutti i riferimenti all'oggetto `SafeHandle` sono stati eliminati e l' `SafeHandle` istanza viene finalizzata.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>È una classe di base astratta. Le classi derivate forniscono istanze specifiche per diversi tipi di handle. Queste classi derivate convalidano quali valori per <xref:System.IntPtr?displayProperty=nameWithType> sono considerati non validi e come effettivamente liberare l'handle. Ad esempio, <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> deriva da `SafeHandle` a wrap `IntPtrs` che identificano gli handle di file aperti/descrittori ed esegue l'override <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle?displayProperty=nameWithType> del relativo metodo per chiuderlo (tramite la `close` funzione su UNIX o `CloseHandle` Function in Windows). La maggior parte delle API nelle librerie .NET che creano una risorsa non gestita ne eseguirà il wrapping in un oggetto `SafeHandle` e lo restituirà in `SafeHandle` base alle esigenze, anziché tornare al puntatore non elaborato. Nelle situazioni in cui si interagisce con un componente non gestito e si ottiene un `IntPtr` per una risorsa non gestita, è possibile creare un `SafeHandle` tipo personalizzato per eseguire il wrapping. Di conseguenza, pochi `SafeHandle` tipi non devono implementare i finalizzatori. la maggior parte delle implementazioni di modelli Disposable finirà solo con il wrapping di altre risorse gestite, alcune delle quali possono essere `SafeHandle` .

Le seguenti classi derivate nello spazio dei nomi <xref:Microsoft.Win32.SafeHandles> forniscono handle sicuri:

- Le classi <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> e <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> per file, file mappati alla memoria e pipe.
- La classe <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> per visualizzazioni di memoria.
- Le classi <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> e <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> per i costrutti di crittografia.
- La classe <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> per le chiavi del Registro di sistema.
- La classe <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> per gli handle di attesa.

## <a name="dispose-and-disposebool"></a>Dispose () e Dispose (bool)

L'interfaccia <xref:System.IDisposable> richiede l'implementazione di un singolo metodo senza parametri, <xref:System.IDisposable.Dispose%2A>. Inoltre, qualsiasi classe non sealed deve avere un `Dispose(bool)` metodo di overload aggiuntivo da implementare:

- `public`Implementazione non virtuale ( `NonInheritable` in Visual Basic) priva di <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> parametri.

- `protected virtual`Metodo ( `Overridable` in Visual Basic) la `Dispose` cui firma è:

  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]

  > [!IMPORTANT]
  > Il `disposing` parametro deve essere `false` chiamato da un finalizzatore e quando viene `true` chiamato dal <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> metodo. In altre parole, è quando viene chiamato in modo `true` deterministico e quando viene chiamato in modo `false` non deterministico.

### <a name="the-dispose-method"></a>Metodo Dispose ()

Poiché la proprietà `public` , non virtuale ( `NonInheritable` in Visual Basic), il metodo senza parametri `Dispose` viene chiamato da un consumer del tipo, il suo scopo è liberare le risorse non gestite, eseguire una pulizia generale e indicare che il finalizzatore, se presente, non è necessario eseguire. La liberazione della memoria effettiva associata a un oggetto gestito è sempre il dominio del [Garbage Collector](index.md). Per questo motivo il metodo ha un'implementazione standard:

[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]

Il metodo `Dispose` esegue la pulizia di tutti gli oggetti, quindi il Garbage Collector non deve più chiamare l'override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> degli oggetti. Pertanto, la chiamata al metodo <xref:System.GC.SuppressFinalize%2A> impedisce al Garbage Collector di eseguire il finalizzatore. Se il tipo non dispone di un finalizzatore, la chiamata a <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> non ha alcun effetto. Si noti che l'effettiva pulizia viene eseguita dall' `Dispose(bool)` Overload del metodo.

### <a name="the-disposebool-method-overload"></a>Overload del metodo Dispose (bool)

Nell'overload, il `disposing` parametro è un oggetto <xref:System.Boolean> che indica se la chiamata al metodo deriva da un <xref:System.IDisposable.Dispose%2A> Metodo (il valore è `true` ) o da un finalizzatore (il valore è `false` ).

Il corpo del metodo è costituito da due blocchi di codice:

- Un blocco che libera le risorse non gestite. Questo blocco viene eseguito indipendentemente dal valore del parametro `disposing`.
- Un blocco condizionale che libera le risorse gestite. Il blocco è eseguito se il valore di `disposing` è `true`. Le risorse gestite liberate possono includere:

  - **Oggetti gestiti che implementano <xref:System.IDisposable>.** Il blocco condizionale può essere usato per chiamare la relativa <xref:System.IDisposable.Dispose%2A> implementazione (Cascade Dispose). Se è stata usata una classe derivata di <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> per eseguire il wrapping della risorsa non gestita, è necessario chiamare l' <xref:System.Runtime.InteropServices.SafeHandle.Dispose?displayProperty=nameWithType> implementazione qui.

  - **Oggetti gestiti che usano grandi quantità di memoria o risorse insufficienti.** Assegnare riferimenti a oggetti gestiti di grandi dimensioni a `null` per renderli più probabilmente irraggiungibili. Questo li rilascia più velocemente rispetto a quelli che sono stati recuperati in modo non deterministico.

Se la chiamata al metodo deriva da un finalizzatore, deve essere eseguito solo il codice che libera le risorse non gestite. L'implementatore è responsabile di garantire che il percorso false non interagisca con gli oggetti gestiti che potrebbero essere stati recuperati. Questo è importante perché l'ordine in cui il Garbage Collector elimina gli oggetti gestiti durante la finalizzazione non è deterministico.

## <a name="cascade-dispose-calls"></a>Chiamate a Dispose a catena

Se la classe è proprietaria di un campo o di una proprietà e il tipo implementa <xref:System.IDisposable> , anche la classe che lo contiene deve implementare <xref:System.IDisposable> . Una classe che crea un'istanza di un' <xref:System.IDisposable> implementazione di e la archivia come membro di istanza è anche responsabile della pulizia. Ciò consente di garantire che ai tipi Disposable a cui viene fatto riferimento venga data la possibilità di eseguire la pulizia in modo deterministico tramite il <xref:System.IDisposable.Dispose%2A> metodo. In questo esempio la classe è `sealed` (o `NotInheritable` in Visual Basic).

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/disposable1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/disposable1.vb#1)]

## <a name="implement-the-dispose-pattern"></a>Implementare il modello Dispose

Tutte le classi non sealed o (Visual Basic classi non modificate come `NotInheritable` ) devono essere considerate come una classe di base potenziale, perché potrebbero essere ereditate. Se si implementa il modello Dispose per qualsiasi classe di base potenziale, è necessario specificare quanto segue:

- Un'implementazione <xref:System.IDisposable.Dispose%2A> che chiami il metodo `Dispose(bool)`.
- `Dispose(bool)`Metodo che esegue la pulizia effettiva.
- Una classe derivata da <xref:System.Runtime.InteropServices.SafeHandle> che esegua il wrapping della risorsa non gestita (consigliato) o un override al metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La <xref:System.Runtime.InteropServices.SafeHandle> classe fornisce un finalizzatore, quindi non è necessario scriverne uno manualmente.

> [!IMPORTANT]
> Una classe di base può fare riferimento solo a oggetti gestiti e implementare il modello Dispose. In questi casi, un finalizzatore non è necessario. Un finalizzatore è necessario solo se si fa riferimento direttamente A risorse non gestite.

Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe di base che usa un handle sicuro.

[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]

> [!NOTE]
> L'esempio precedente usa un oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per illustrato il criterio; sarebbe possibile usare invece qualsiasi oggetto derivato da <xref:System.Runtime.InteropServices.SafeHandle>. Si noti che l'esempio non crea correttamente un'istanza del relativo oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.

Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe di base che esegue l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.

[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]

> [!TIP]
> In C# si crea un [finalizzatore](../../csharp/programming-guide/classes-and-structs/destructors.md) eseguendo l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType> . In Visual Basic, questa operazione viene eseguita con `Protected Overrides Sub Finalize()` .

## <a name="implement-the-dispose-pattern-for-a-derived-class"></a>Implementare il modello Dispose per una classe derivata

Una classe derivata da una classe che implementa l'interfaccia <xref:System.IDisposable> non deve implementare <xref:System.IDisposable>, poiché l'implementazione della classe di base di <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> viene ereditata dalle classi derivate. Al contrario, per pulire una classe derivata, è necessario specificare quanto segue:

- `protected override void Dispose(bool)`Metodo che esegue l'override del metodo della classe di base ed esegue l'effettiva pulizia della classe derivata. Questo metodo deve anche chiamare il `base.Dispose(bool)` `MyBase.Dispose(bool)` Metodo (in Visual Basic) della classe di base e passare il relativo stato di eliminazione per l'argomento.
- Una classe derivata da <xref:System.Runtime.InteropServices.SafeHandle> che esegua il wrapping della risorsa non gestita (consigliato) o un override al metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La classe <xref:System.Runtime.InteropServices.SafeHandle> fornisce un finalizzatore, evitando la necessità di codificarne uno. Se si fornisce un finalizzatore, questo deve chiamare l' `Dispose(bool)` Overload di con un `disposing` argomento di `false` .

Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe derivata che usa un handle sicuro:

[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]

> [!NOTE]
> L'esempio precedente usa un oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per illustrato il criterio; sarebbe possibile usare invece qualsiasi oggetto derivato da <xref:System.Runtime.InteropServices.SafeHandle>. Si noti che l'esempio non crea correttamente un'istanza del relativo oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.

Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe derivata che esegue l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:

[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]

## <a name="implement-the-dispose-pattern-with-safe-handles"></a>Implementare il modello Dispose con handle sicuri

L'esempio seguente illustra il modello Dispose per una classe di base, `DisposableStreamResource`, che usa handle sicuri per incapsulare le risorse non gestite. Viene definita una classe `DisposableStreamResource` che usa <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per eseguire il wrapping di un oggetto <xref:System.IO.Stream> che rappresenta un file aperto. La classe include anche una singola proprietà, `Size` , che restituisce il numero totale di byte nel flusso di file.

[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]

## <a name="implement-the-dispose-pattern-for-a-derived-class-with-safe-handles"></a>Implementare il modello Dispose per una classe derivata con handle sicuri

Nell'esempio seguente viene illustrato il modello Dispose per una classe derivata, `DisposableStreamResource2`, che eredita dalla classe `DisposableStreamResource` presentata nell'esempio precedente. La classe aggiunge un metodo aggiuntivo, `WriteFileInfo`, e usa un oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per il wrapping dell'handle del file modificabile.

[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]

## <a name="see-also"></a>Vedere anche

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [Definire e utilizzare classi e struct (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
