---
title: Semplificazione del debug di un'immagine
ms.date: 03/30/2017
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c58008bc621ea95fbb2e4cc5e7d4521576aca37c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391046"
---
# <a name="making-an-image-easier-to-debug"></a>Semplificazione del debug di un'immagine
Quando si compila codice non gestito, è possibile configurare un'immagine eseguibile per il debug impostando le opzioni dell'IDE o della riga di comando. Ad esempio, è possibile usare l'opzione della riga di comando /**Zi** in Visual C++ per richiedere di generare file di simboli di debug (file con estensione pdb). In modo analogo, l'opzione della riga di comando /**Od** indica al compilatore di disabilitare l'ottimizzazione. Il codice risultante viene eseguito più lentamente, ma è più semplice eseguirne il debug all'occorrenza.  
  
 Durante la compilazione di codice gestito di .NET Framework, i compilatori come Visual C++, Visual Basic e C# compilano il programma di origine in linguaggio MSIL (Microsoft Intermediate Language). MSIL viene successivamente compilato tramite JIT, appena prima dell'esecuzione, in codice macchina nativo. Come per il codice non gestito, è possibile configurare un'immagine eseguibile per il debug impostando le opzioni dell'IDE o della riga di comando. Inoltre, è possibile configurare la compilazione JIT per il debug in modo analogo.  
  
 Questa configurazione JIT presenta due aspetti:  
  
-   È possibile richiedere al compilatore JIT di generare informazioni di rilevamento. In questo modo il debugger ha la possibilità di abbinare una catena di codice MSIL alla controparte in codice macchina e di tenere traccia della posizione di archiviazione delle variabili locali e degli argomenti delle funzioni.  In .NET Framework versione 2.0, il compilatore JIT genererà sempre le informazioni di rilevamento, quindi non occorre richiederle.  
  
-   È possibile richiedere al compilatore JIT di non ottimizzare il codice macchina risultante.  
  
 In genere, il compilatore che genera il codice MSIL imposta queste opzioni del compilatore JIT in modo corretto in base ai parametri dell'IDE o alle opzioni della riga di comando specificati, ad esempio /**Od**.  
  
 In alcuni casi, può essere necessario modificare il comportamento del compilatore JIT in modo che sia più semplice eseguire il debug del codice macchina generato. Ad esempio, si potrebbero generare informazioni di rilevamento JIT per una build finale o un'ottimizzazione dei controlli. È possibile farlo con un file di inizializzazione (INI).  
  
 Ad esempio, se l'assembly di cui vuole eseguire il debug è denominata App.exe, è possibile creare un file di testo denominato App, nella stessa cartella di App.exe, che contiene queste tre righe:  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 È possibile impostare il valore di ogni opzione su 0 o 1 e per qualsiasi opzione assente verrà usato il valore predefinito 0. L'impostazione di `GenerateTrackingInfo` su 1 e di `AllowOptimize` su 0 consente di semplificare al massimo il debug.  
  
> [!NOTE]
>  In .NET Framework versione 2.0, il compilatore JIT genera sempre le informazioni di rilevamento indipendentemente dal valore per `GenerateTrackingInfo`. Il valore `AllowOptimize`, comunque, ha ancora un effetto. Quando si usa [Ngen.exe (generatore di immagini native)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) per precompilare l'immagine nativa senza ottimizzazione, il file INI deve essere presente nella cartella di destinazione con `AllowOptimize=0` quando viene eseguito Ngen.exe. Se è stato precompilato un assembly senza ottimizzazione, è necessario rimuovere il codice precompilato usando l'opzione **/uninstall** di NGen.exe prima di rieseguire Ngen.exe per precompilare il codice con l'ottimizzazione. Se il file INI non è presente nella cartella, Ngen.exe precompila il codice come ottimizzato per impostazione predefinita.  
  
> [!NOTE]
>  <xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controlla le impostazioni per un assembly. **DebuggableAttribute** include due campi che registrano le impostazioni che specificano se il compilatore JIT deve ottimizzare e/o generare informazioni di rilevamento. In .NET Framework versione 2.0, il compilatore JIT genererà sempre le informazioni di rilevamento.  
  
> [!NOTE]
>  Per una build finale, i compilatori non impostano alcun **DebuggableAttribute**. Il comportamento predefinito del compilatore JIT consiste nel generare codice macchina con le prestazioni massime e il più difficile da sottoporre a debug. L'abilitazione del rilevamento JIT riduce leggermente le prestazioni e la disabilitazione dell'ottimizzazione le riduce notevolmente.  
  
> [!NOTE]
>  **DebuggableAttribute** si applica a un intero assembly per volta, non ai singoli moduli all'interno dell'assembly. Gli strumenti di sviluppo devono quindi associare gli attributi personalizzati al token dei metadati di assembly, se un assembly è già stato creato, o alla classe chiamata **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. Lo strumento ALink promuoverà quindi questi attributi **DebuggableAttribute** da ogni modulo all'assembly di cui diventano parte. In caso di conflitto, l'operazione ALink avrà esito negativo.  
  
> [!NOTE]
>  Nella versione 1.0 di .NET Framework, il compilatore Microsoft Visual C++ aggiunge **DebuggableAttribute** quando vengono specificate le opzioni del compilatore **/clr** e **/Zi**. Nella versione 1.1 di .NET Framework, è necessario aggiungere manualmente **DebugabbleAttribute** nel codice o usare l'opzione del linker **/ASSEMBLYDEBUG**.  
  
## <a name="see-also"></a>Vedere anche  
 [Debug, traccia e profilatura](../../../docs/framework/debug-trace-profile/index.md)  
 [Abilitazione del debug ad associazione JIT](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 [Abilitazione della funzione di profilatura](http://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
