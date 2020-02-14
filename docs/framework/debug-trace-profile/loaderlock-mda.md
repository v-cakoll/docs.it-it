---
title: MDA loaderLock
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- LoaderLock MDA
- MDAs (managed debugging assistants), loader locks
- managed debugging assistants (MDAs), loader locks
- operating system loader locks
- loader locks
- locks, threads
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
ms.openlocfilehash: cd77640a6566f3fd94631dac184ae5bc3ffab5d1
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217346"
---
# <a name="loaderlock-mda"></a>MDA loaderLock
L'assistente al debug gestito `loaderLock` rileva i tentativi di esecuzione di codice gestito in un thread che contiene il blocco del caricatore del sistema operativo Microsoft Windows.  Qualsiasi esecuzione di questo tipo non è valida perché può comportare il verificarsi di deadlock e l'uso di DLL prima che siano state inizializzate dal caricatore del sistema operativo.  
  
## <a name="symptoms"></a>Sintomi  
 L'errore più comune durante l'esecuzione di codice all'interno del blocco di caricamento del sistema operativo consiste nel deadlock dei thread durante il tentativo di chiamare altre funzioni Win32 che richiedono anch'esse il blocco del caricatore.  Alcuni esempi di queste funzioni includono `LoadLibrary`, `GetProcAddress`, `FreeLibrary` e `GetModuleHandle`.  L'applicazione potrebbe non chiamare direttamente queste funzioni. Common Language Runtime (CLR) può chiamare queste funzioni come risultato di una chiamata di livello superiore come <xref:System.Reflection.Assembly.Load%2A> o la prima chiamata a un metodo di platform invoke.  
  
 Possono verificarsi deadlock anche se un thread è in attesa dell'avvio o del completamento di un altro thread.  Quando l'esecuzione di un thread viene avviata o completata, il thread deve acquisire il blocco del caricatore del sistema operativo per recapitare gli eventi alle DLL interessate.  
  
 Infine, vi sono casi in cui possono verificarsi chiamate nelle DLL prima che le DLL siano state inizializzate correttamente dal caricatore del sistema operativo.  Diversamente dagli errori di deadlock, che possono essere diagnosticati esaminando gli stack di tutti i thread inclusi nel deadlock, è molto difficile diagnosticare l'uso di DLL non inizializzate con questo assistente al debug gestito.  
  
## <a name="cause"></a>Causa  
 Assembly C++ gestiti/non gestiti misti creati per .NET Framework versione 1.0 o 1.1 tentano in genere di eseguire codice gestito all'interno del blocco del caricatore, se non è stata adottata particolare attenzione, ad esempio tramite il collegamento a **/NOENTRY**.
  
 Gli assembly C++ gestiti/non gestiti misti creati per .NET Framework versione 2.0 sono meno soggetti a questi problemi, in quanto sono associati allo stesso rischio minimo delle applicazioni che usano DLL non gestite che violano le regole del sistema operativo.  Ad esempio, se un punto di ingresso `DllMain` di una DLL non gestita chiama `CoCreateInstance` per ottenere un oggetto gestito che è stato esposto a COM, il risultato è un tentativo di eseguire codice gestito all'interno del blocco del caricatore. Per altre informazioni sui problemi relativi al blocco del caricatore in .NET Framework 2.0 e versioni successive, vedere [Initialization of Mixed Assemblies](/cpp/dotnet/initialization-of-mixed-assemblies) (Inizializzazione di assembly misti).  
  
## <a name="resolution"></a>Risoluzione  
 In Visual C++ .NET 2002 e Visual C++ .NET 2003 le DLL compilate con l'opzione del compilatore `/clr` non possono causare un deadlock in modo non deterministico durante il caricamento. Questo problema è noto come blocco del caricatore o problema di caricamento di DLL miste. In Visual C++ 2005 e versioni successive sono stato rimossi quasi tutti gli aspetti non deterministici dal processo di caricamento di DLL miste. Tuttavia, esistono ancora alcuni scenari nei quali il blocco del caricatore può ancora verificarsi in modo deterministico. Per una descrizione dettagliata delle cause e delle soluzioni per i problemi relativi al blocco del caricatore rimanenti, vedere [Initialization of Mixed Assemblies](/cpp/dotnet/initialization-of-mixed-assemblies) (Inizializzazione di assembly misti). Se l'argomento non comprende il problema specifico relativo al blocco del caricatore, è necessario esaminare lo stack del thread per determinare il motivo per cui si verifica il blocco del caricatore e come correggere il problema. Esaminare l'analisi dello stack per il thread che ha attivato questo assistente al debug gestito.  Il thread sta tentando di eseguire una chiamata non valida nel codice gestito mentre mantiene il blocco del caricatore del sistema operativo.  Probabilmente si noterà un punto di ingresso `DllMain`, o uno equivalente, della DLL nello stack.  Le regole del sistema operativo per le attività valide all'interno di un punto di ingresso di questo tipo sono piuttosto limitate.  Queste regole impediscono qualsiasi esecuzione di codice gestito.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 In genere, si verifica il deadlock di diversi thread all'interno del processo.  Poiché è probabile che uno di questi thread sia responsabile dell'esecuzione di un'operazione di Garbage Collection, questo deadlock può avere un impatto notevole sull'intero processo.  Inoltre, impedirà qualsiasi altra operazione che richiede il blocco del caricatore del sistema operativo, come il caricamento o lo scaricamento di assembly o DLL e l'avvio o l'arresto di thread.  
  
 In alcuni rari casi, possono anche verificarsi violazioni di accesso o problemi simili nelle DLL chiamate prima di essere state inizializzate.  
  
## <a name="output"></a>Output  
 Questo assistente al debug gestito segnala che è in corso un tentativo di esecuzione di codice gestito non valida.  È necessario esaminare lo stack del thread per determinare il motivo per cui si verifica il blocco del caricatore e come risolvere il problema.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
