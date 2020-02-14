---
title: MDA bindingFailure
ms.date: 03/30/2017
helpviewer_keywords:
- binding failure
- binding, failures
- MDAs (managed debugging assistants), binding failures
- assemblies [.NET Framework], binding failures
- managed debugging assistants (MDAs), binding failures
- BindingFailure MDA
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
ms.openlocfilehash: e3a9a915d25cbe5f052f039055167cf3ae4bf424
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216923"
---
# <a name="bindingfailure-mda"></a>MDA bindingFailure

L'assistente al debug gestito `bindingFailure` viene attivato quando si verifica un errore nel caricamento di un assembly.

## <a name="symptoms"></a>Sintomi

Il codice ha tentato di caricare un assembly usando un riferimento statico o uno dei metodi loader, ad esempio <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>. L'assembly non viene caricato e viene generata un'eccezione <xref:System.IO.FileNotFoundException> o <xref:System.IO.FileLoadException>.

## <a name="cause"></a>Causa

Quando il runtime non è in grado di caricare un assembly, si verifica un errore di binding, che può essere il risultato di una delle situazioni descritte di seguito.

- Common Language Runtime (CLR) non è in grado di trovare l'assembly richiesto. I motivi, in questo caso, possono essere diversi: è possibile, ad esempio, che l'assembly non sia stata installata o che l'applicazione non sia stata correttamente configurata per trovare l'assembly.

- Uno scenario comune relativo a questo problema è il passaggio di un tipo a un altro dominio applicazione, in cui viene richiesto a CLR di caricare l'assembly contenente il tipo nell'altro dominio applicazione. Se questo è configurato diversamente dal dominio applicazione originale, è possibile che il runtime non riesca a caricare l'assembly. È possibile, ad esempio, che i due domini applicazione abbiano valori diversi per la proprietà <xref:System.AppDomain.BaseDirectory%2A>.

- L'assembly richiesto è danneggiato o non è un assembly.

- Il codice con cui si tenta di caricare l'assembly non ha le autorizzazioni di sicurezza dell'accesso al codice necessarie per caricare assembly.

- Nelle credenziali utente non sono infatti incluse le autorizzazioni necessarie per la lettura del file.

## <a name="resolution"></a>Risoluzione

La prima cosa da fare è determinare il motivo per cui CLR non è stato in grado di eseguire il binding all'assembly richiesto. Possono essere molti i motivi per cui il runtime non è riuscito a trovare o a caricare l'assembly richiesto, come illustrato negli scenari elencati nella sezione Causa. Per eliminare la causa dell'errore di binding, sono consigliate le azioni seguenti.

- Determinare la causa usando i dati forniti dall'assistente al debug gestito `bindingFailure`:

  - Eseguire [Fuslogvw.exe (Visualizzatore log binding assembly)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) per leggere i log degli errori prodotti dal binder di assembly.

  - Determinare se l'assembly si trova nella posizione richiesta. Nel caso dei metodi <xref:System.Reflection.Assembly.LoadFrom%2A> e <xref:System.Reflection.Assembly.LoadFile%2A>, la posizione richiesta può essere determinata facilmente. Nel caso del metodo <xref:System.Reflection.Assembly.Load%2A>, che esegue il binding usando l'identità dell'assembly, è necessario cercare gli assembly corrispondenti all'identità specificata nella Global Assembly Cache e nel percorso di analisi della proprietà <xref:System.AppDomain.BaseDirectory%2A> del dominio applicazione.

- Risolvere la causa in base ai risultati del passaggio precedente. Di seguito sono elencate le possibili opzioni di risoluzione:

  - Installare l'assembly richiesto nella Global Assembly Cache e chiamare il metodo <xref:System.Reflection.Assembly.Load%2A> per caricare l'assembly in base all'identità.

  - Copiare l'assembly richiesto nella directory dell'applicazione e chiamare il metodo <xref:System.Reflection.Assembly.Load%2A> per caricare l'assembly in base all'identità.

  - Riconfigurare il dominio applicazione in cui si è verificato l'errore di binding per includere il percorso dell'assembly modificando la proprietà <xref:System.AppDomain.BaseDirectory%2A> o aggiungendo percorsi di analisi privati.

  - Modificare l'elenco di controllo di accesso per il file in modo da consentirne la lettura all'utente connesso.

## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione

L'assistente al debug gestito non ha alcun effetto su CLR. Si limita a generare un report dei dati relativi agli errori di binding.

## <a name="output"></a>Output

L'assistente al debug gestito segnala l'assembly in cui si è verificato l'errore di caricamento, inclusi il percorso richiesto e/o il nome visualizzato, il contesto di binding, il dominio applicazione in cui è stato richiesto il caricamento e il motivo dell'errore.

È possibile che, se non è disponibile in CLR, il nome visualizzato o il percorso richiesto non sia definito. Se la chiamata non riuscita faceva riferimento al metodo <xref:System.Reflection.Assembly.Load%2A>, è probabile che il runtime non sia stato in grado di determinare il nome visualizzato dell'assembly.

## <a name="configuration"></a>Configurazione

```xml
<mdaConfig>
  <assistants>
    <bindingFailure />
  </assistants>
</mdaConfig>
```

## <a name="example"></a>Esempio

L'esempio di codice seguente mostra una situazione che può comportare l'attivazione dell'assistente al debug gestito:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Reflection;
namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            // This call attempts to load a nonexistent assembly.
            // The call will throw a System.IO.FileNotFound exception
            // and cause the activation of the bindingFailure MDA
            // if it is registered.
            Assembly.Load("NonExistentAssembly");
        }
    }
}
```

## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
