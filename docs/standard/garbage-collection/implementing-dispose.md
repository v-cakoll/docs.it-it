---
title: Implementazione di un metodo Dispose
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: f3d3269ccf56954f963762503d2bc1c53b9e6b83
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78238988"
---
# <a name="implementing-a-dispose-method"></a>Implementazione di un metodo Dispose

Implementare un metodo <xref:System.IDisposable.Dispose%2A> per rilasciare le risorse non gestite usate dall'applicazione. Garbage Collector di .NET non alloca e non rilascia la memoria non gestita.  
  
Il criterio per eliminare un oggetto, definito [criterio Dispose](implementing-dispose.md), definisce un ordine in base alla durata di un oggetto. Il modello Dispose viene usato solo per gli oggetti che accedono a risorse non gestite, quali handle di file e pipe, handle del Registro di sistema, handle di attesa o puntatori ai blocchi di memoria non gestita. Ciò è dovuto al fatto che il Garbage Collector è molto efficiente nel recupero degli oggetti gestiti inutilizzati, ma non è in grado di recuperare gli oggetti non gestiti.  
  
Il modello Dispose precede due variazioni:  
  
- Viene eseguito il wrapping di ogni risorsa non gestita utilizzata da un tipo in un handle sicuro (ovvero in una classe derivata da <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>). In questo caso, viene implementata l'interfaccia <xref:System.IDisposable> e un ulteriore metodo `Dispose(Boolean)`. Questa è la variazione consigliata e non richiede l'override del metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.  
  
  > [!NOTE]
  > Lo spazio dei nomi <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> fornisce un set di classi derivate da <xref:System.Runtime.InteropServices.SafeHandle>, elencate nella sezione [Uso di handle sicuri](#SafeHandles). Se non è possibile trovare una classe in grado di rilasciare la risorsa non gestita, è possibile implementare una propria sottoclasse di <xref:System.Runtime.InteropServices.SafeHandle>.  
  
- Viene implementata l'interfaccia <xref:System.IDisposable> e un ulteriore metodo `Dispose(Boolean)` e viene inoltre eseguito l'override del metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. È necessario eseguire l'override di <xref:System.Object.Finalize%2A> per assicurarsi che le risorse non gestite vengano eliminate quando l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> non viene chiamata da un consumer del tipo. Se si usa la tecnica consigliata discussa nel precedente punto, questa operazione viene eseguita automaticamente dalla classe <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>.  
  
Al fine di garantire la corretta pulitura delle risorse in ogni occasione, deve essere possibile chiamare il metodo <xref:System.IDisposable.Dispose%2A> più volte senza che venga generata un'eccezione.  
  
Nell'esempio di codice fornito per il metodo <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> viene illustrato il modo in cui Garbage Collection può causare l'esecuzione di un finalizzatore, mentre un riferimento non gestito all'oggetto o ai relativi membri è ancora in uso. Potrebbe essere utile usare <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> per rendere l'oggetto non idoneo per Garbage Collection dall'inizio della routine corrente fino al punto in cui viene chiamato il metodo.
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a>Dispose() e Dispose(Boolean)  

L'interfaccia <xref:System.IDisposable> richiede l'implementazione di un singolo metodo senza parametri, <xref:System.IDisposable.Dispose%2A>. Tuttavia, il modello Dispose richiede due metodi `Dispose` per essere implementato:  
  
- Un'implementazione `NonInheritable` pubblica non virtuale (<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in Visual Basic) senza parametri.  
  
- Un metodo `Overridable` protetto virtuale (`Dispose` in Visual Basic) la cui firma è indicata di seguito:  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a>Overload Dispose()

Poiché il metodo pubblico, non virtuale (`NonInheritable` in Visual Basic), privo di parametri `Dispose` è chiamato da un consumer del tipo, lo scopo è liberare le risorse non gestite e indicare che non è necessario eseguire il finalizzatore, se disponibili. Per questo motivo il metodo ha un'implementazione standard:  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
Il metodo `Dispose` esegue la pulizia di tutti gli oggetti, quindi il Garbage Collector non deve più chiamare l'override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> degli oggetti. Pertanto, la chiamata al metodo <xref:System.GC.SuppressFinalize%2A> impedisce al Garbage Collector di eseguire il finalizzatore. Se il tipo non dispone di un finalizzatore, la chiamata a <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> non ha alcun effetto. Si noti che l'effettiva operazione di rilascio delle risorse non gestite viene eseguita dal secondo overload del metodo `Dispose`.  
  
### <a name="the-disposeboolean-overload"></a>Overload Dispose(Boolean)

Nel secondo overload il parametro *disposing* è un oggetto <xref:System.Boolean> che indica se la chiamata al metodo proviene da un metodo <xref:System.IDisposable.Dispose%2A> (il valore è `true`) o da un finalizzatore (il valore è `false`).  
  
Il corpo del metodo è costituito da due blocchi di codice:  
  
- Un blocco che libera le risorse non gestite. Questo blocco viene eseguito indipendentemente dal valore del parametro `disposing`.  
  
- Un blocco condizionale che libera le risorse gestite. Il blocco è eseguito se il valore di `disposing` è `true`. Le risorse gestite liberate possono includere:  
  
  **Oggetti gestiti che implementano <xref:System.IDisposable>.** Il blocco condizionale può essere usato per chiamare la relativa implementazione <xref:System.IDisposable.Dispose%2A>. Se è stato utilizzato un handle sicuro per eseguire il wrapping della risorsa non gestita, l'implementazione <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> dovrebbe essere chiamata in questo punto.  
  
  **Oggetti gestiti che usano grandi quantità di memoria o risorse insufficienti.** La liberazione esplicita di questi oggetti nel metodo `Dispose` ne consente un rilascio più veloce rispetto al recupero non deterministico eseguito dal Garbage Collector.  
  
Se la chiamata al metodo proviene da un finalizzatore (ovvero se *disposing* è `false`), viene eseguito solo il codice che libera le risorse non gestite. Poiché l'ordine in cui il Garbage Collector elimina gli oggetti gestiti durante la finalizzazione non è definito, la chiamata a questo overload `Dispose` con valore `false` impedisce che il finalizzatore tenti di liberare risorse gestite che potrebbero essere già state recuperate.  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Implementazione del modello Dispose per una classe di base

Per implementare il modello Dispose per una classe di base, è necessario predisporre quanto segue:  
  
> [!IMPORTANT]
> È consigliabile implementare questo modello per tutte le classi di base che implementano <xref:System.IDisposable.Dispose> e non sono `sealed` (`NotInheritable` in Visual Basic).  
  
- Un'implementazione <xref:System.IDisposable.Dispose%2A> che chiami il metodo `Dispose(Boolean)`.  
  
- Un metodo `Dispose(Boolean)` che esegua l'effettiva operazione di rilascio delle risorse.  
  
- Una classe derivata da <xref:System.Runtime.InteropServices.SafeHandle> che esegua il wrapping della risorsa non gestita (consigliato) o un override al metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La classe <xref:System.Runtime.InteropServices.SafeHandle> fornisce un finalizzatore, evitando la necessità di codificarne uno.  
  
Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe di base che usa un handle sicuro.  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> L'esempio precedente usa un oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per illustrato il criterio; sarebbe possibile usare invece qualsiasi oggetto derivato da <xref:System.Runtime.InteropServices.SafeHandle>. Si noti che l'esempio non crea correttamente un'istanza del relativo oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.  
  
Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe di base che esegue l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> In C# si esegue l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType> definendo un [distruttore](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Implementazione del modello Dispose per una classe derivata

Una classe derivata da una classe che implementa l'interfaccia <xref:System.IDisposable> non deve implementare <xref:System.IDisposable>, poiché l'implementazione della classe di base di <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> viene ereditata dalle classi derivate. Per rilasciare le risorse di una classe derivata, è invece necessario specificare quanto segue:  
  
- Un metodo `protected Dispose(Boolean)` che esegua l'override del metodo della classe di base ed esegua l'effettiva operazione di rilascio delle risorse della classe derivata. Questo metodo deve anche chiamare il metodo `Dispose(Boolean)` della classe di base e passarne lo stato di eliminazione per l'argomento.  
  
- Una classe derivata da <xref:System.Runtime.InteropServices.SafeHandle> che esegua il wrapping della risorsa non gestita (consigliato) o un override al metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La classe <xref:System.Runtime.InteropServices.SafeHandle> fornisce un finalizzatore, evitando la necessità di codificarne uno. Se si specifica un finalizzatore, questo deve chiamare l'overload di `Dispose(Boolean)` con un argomento *disposing* di `false`.  
  
Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe derivata che usa un handle sicuro:  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> L'esempio precedente usa un oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per illustrato il criterio; sarebbe possibile usare invece qualsiasi oggetto derivato da <xref:System.Runtime.InteropServices.SafeHandle>. Si noti che l'esempio non crea correttamente un'istanza del relativo oggetto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.  
  
Di seguito è illustrato il modello generale per implementare il modello Dispose per una classe derivata che esegue l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> In C# si esegue l'override di <xref:System.Object.Finalize%2A?displayProperty=nameWithType> definendo un [distruttore](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
<a name="SafeHandles"></a>
## <a name="using-safe-handles"></a>Utilizzo degli handle sicuri

La scrittura di codice per il finalizzatore di un oggetto è un'attività complessa che può causare problemi se non eseguita correttamente. È pertanto consigliabile costruire oggetti <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> anziché implementare un finalizzatore.  
  
Le classi derivate dalla classe <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> semplificano i problemi di durata degli oggetti assegnando e rilasciando handle senza interruzione. Contengono un finalizzatore critico la cui esecuzione è garantita durante lo scaricamento di un dominio dell'applicazione. Per altre informazioni sui vantaggi dell'utilizzo di un handle sicuro, vedere <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>. Le seguenti classi derivate nello spazio dei nomi <xref:Microsoft.Win32.SafeHandles> forniscono handle sicuri:  
  
- Le classi <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> e <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> per file, file mappati alla memoria e pipe.  
  
- La classe <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> per visualizzazioni di memoria.  
  
- Le classi <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> e <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> per i costrutti di crittografia.  
  
- La classe <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> per le chiavi del Registro di sistema.  
  
- La classe <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> per gli handle di attesa.  
  
<a name="base"></a>
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Uso di un handle sicuro per implementare il modello Dispose per una classe di base

L'esempio seguente illustra il modello Dispose per una classe di base, `DisposableStreamResource`, che usa handle sicuri per incapsulare le risorse non gestite. Viene definita una classe `DisposableResource` che usa <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> per eseguire il wrapping di un oggetto <xref:System.IO.Stream> che rappresenta un file aperto. Il metodo `DisposableResource` include anche una singola proprietà, `Size`, che restituisce il numero totale di byte nel flusso di file.  
  
[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Utilizzo di un handle sicuro per implementare il modello Dispose per una classe derivata

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
- [Procedura: Definire e usare classi e struct (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
- [Criterio Dispose](implementing-dispose.md)
