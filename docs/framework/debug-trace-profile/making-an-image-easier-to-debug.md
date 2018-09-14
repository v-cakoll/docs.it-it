---
title: Semplificazione un'immagine eseguire il debug in .NET
description: Informazioni su come configurare un'immagine eseguibile per semplificare il debug utilizzando l'IDE opzioni e le opzioni della riga di comando.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f25eaaa17d4c4bd2e9522591bb0fd66445cdb6f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45610067"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Semplificazione un'immagine eseguire il debug in .NET

Quando si compila codice non gestito, è possibile configurare un'immagine eseguibile per il debug impostando le opzioni dell'IDE o della riga di comando. Ad esempio, è possibile usare l'opzione della riga di comando /**Zi** in Visual C++ per richiedere di generare file di simboli di debug (file con estensione pdb). In modo analogo, l'opzione della riga di comando /**Od** indica al compilatore di disabilitare l'ottimizzazione. Il codice risultante è molto più lento, ma è più facile eseguire il debug, questo non è necessario.

Quando la compilazione di .NET Framework, codice gestito, i compilatori come Visual C++, Visual Basic e c# compilano il programma di origine in Microsoft intermediate language (MSIL). MSIL viene quindi compilato tramite JIT, appena prima dell'esecuzione, in codice macchina nativo. Come per il codice non gestito, è possibile configurare un'immagine eseguibile per il debug impostando le opzioni dell'IDE o della riga di comando. È anche possibile configurare la compilazione JIT per il debug in modo analogo.

Questa configurazione JIT presenta due aspetti:

- È possibile richiedere al compilatore JIT di generare informazioni di rilevamento. In questo modo il debugger ha la possibilità di abbinare una catena di codice MSIL alla controparte in codice macchina e di tenere traccia della posizione di archiviazione delle variabili locali e degli argomenti delle funzioni. A partire da .NET Framework versione 2.0, il compilatore JIT genera sempre le informazioni di rilevamento, in modo che non è necessario per la richiesta.

- È possibile richiedere al compilatore JIT di non ottimizzare il codice macchina risultante.

In genere, il compilatore che genera il codice MSIL imposta queste opzioni del compilatore JIT in modo appropriato, in base alle opzioni dell'IDE o della riga di comando si specifica, ad esempio, /**Od**.

In alcuni casi, può essere necessario modificare il comportamento del compilatore JIT in modo che sia più semplice eseguire il debug del codice macchina generato. Ad esempio, si potrebbero generare informazioni di rilevamento JIT per una build finale o un'ottimizzazione dei controlli. È possibile farlo con un file di inizializzazione (INI).

Ad esempio, se l'assembly che si desidera eseguire il debug viene chiamato *MyApp.exe*, è possibile creare un file di testo denominato *MyApp*, nella stessa cartella del *MyApp.exe*, che contiene Queste tre righe:

```txt
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

È possibile impostare il valore di ogni opzione su 0 o 1 e per qualsiasi opzione assente verrà usato il valore predefinito 0. L'impostazione di `GenerateTrackingInfo` su 1 e di `AllowOptimize` su 0 consente di semplificare al massimo il debug.

A partire da .NET Framework versione 2.0, il compilatore JIT genera sempre le informazioni di rilevamento indipendentemente dal valore per `GenerateTrackingInfo`; tuttavia, il `AllowOptimize` valore ha ancora effetto. Quando si usa [Ngen.exe (generatore di immagini native)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) per precompilare l'immagine nativa senza ottimizzazione, il file INI deve essere presente nella cartella di destinazione con `AllowOptimize=0` quando viene eseguito Ngen.exe. Se è stato precompilato un assembly senza ottimizzazione, è necessario rimuovere il codice precompilato usando NGen.exe **/Uninstall** opzione prima di eseguire nuovamente Ngen.exe per precompilare il codice ottimizzato. Se il file ini non è presente nella cartella, per impostazione predefinita Ngen.exe precompila il codice come ottimizzato.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controlla le impostazioni per un assembly. **DebuggableAttribute** include due campi che controllano se il compilatore JIT deve ottimizzare e/o generare informazioni di rilevamento. A partire da .NET Framework versione 2.0, il compilatore JIT genera sempre le informazioni di rilevamento.

Per una build finale, i compilatori non impostano eventuali **DebuggableAttribute**. Per impostazione predefinita, il compilatore JIT genera prestazioni più elevate, più difficile il debug del codice macchina. L'abilitazione del rilevamento JIT riduce leggermente le prestazioni e la disabilitazione dell'ottimizzazione le riduce notevolmente.

**DebuggableAttribute** si applica a un intero assembly per volta, non ai singoli moduli all'interno dell'assembly. Gli strumenti di sviluppo devono quindi associare gli attributi personalizzati al token dei metadati di assembly, se un assembly è già stato creato, o alla classe chiamata **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. Lo strumento ALink promuove quindi questi **DebuggableAttribute** attributi da ogni modulo all'assembly diventano una parte di. Se si verifica un conflitto, l'operazione ALink avrà esito negativo.

> [!NOTE]
> Nella versione 1.0 di .NET Framework, il compilatore Microsoft Visual C++ aggiunge **DebuggableAttribute** quando vengono specificate le opzioni del compilatore **/clr** e **/Zi**. Nella versione 1.1 di .NET Framework, è necessario aggiungere manualmente **DebugabbleAttribute** nel codice o usare l'opzione del linker **/ASSEMBLYDEBUG**.

## <a name="see-also"></a>Vedere anche

- [Debug, traccia e profilatura](../../../docs/framework/debug-trace-profile/index.md)
- [Abilitazione del debug ad associazione JIT](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)
- [Abilitazione della funzione di profilatura](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
