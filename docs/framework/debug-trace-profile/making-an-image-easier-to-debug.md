---
title: Semplificazione del debug di un'immagine in .NET
description: Informazioni su come configurare un'immagine eseguibile per semplificare il debug usando i commutatori IDE e le opzioni della riga di comando.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
ms.openlocfilehash: 44d512a8ebec0e21e33f51c07428331e5e22b7bf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217333"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Semplificazione del debug di un'immagine in .NET

Quando si compila codice non gestito, è possibile configurare un'immagine eseguibile per il debug impostando le opzioni dell'IDE o della riga di comando. Ad esempio, è possibile usare l'opzione della riga di comando /**Zi** in Visual C++ per richiedere di generare file di simboli di debug (file con estensione pdb). In modo analogo, l'opzione della riga di comando /**Od** indica al compilatore di disabilitare l'ottimizzazione. Il codice risultante viene eseguito più lentamente, ma è più facile eseguirne il debug, se necessario.

Quando si compila .NET Framework codice gestito, i compilatori quali C++Visual, Visual Basic e C# compilano il programma di origine in Microsoft Intermediate Language (MSIL). Il codice MSIL viene quindi compilato tramite JIT, appena prima dell'esecuzione, nel codice macchina nativo. Come per il codice non gestito, è possibile configurare un'immagine eseguibile per il debug impostando le opzioni dell'IDE o della riga di comando. È anche possibile configurare la compilazione JIT per il debug in modo analogo.

Questa configurazione JIT presenta due aspetti:

- È possibile richiedere al compilatore JIT di generare informazioni di rilevamento. In questo modo il debugger ha la possibilità di abbinare una catena di codice MSIL alla controparte in codice macchina e di tenere traccia della posizione di archiviazione delle variabili locali e degli argomenti delle funzioni. A partire dalla versione di .NET Framework 2,0, il compilatore JIT genera sempre le informazioni di rilevamento, quindi non è necessario richiederle.

- È possibile richiedere al compilatore JIT di non ottimizzare il codice macchina risultante.

In genere, il compilatore che genera il codice MSIL imposta le opzioni del compilatore JIT in modo appropriato, in base ai commutatori IDE o alle opzioni della riga di comando specificate, ad esempio/**od**.

In alcuni casi, può essere necessario modificare il comportamento del compilatore JIT in modo che sia più semplice eseguire il debug del codice macchina generato. Ad esempio, si potrebbero generare informazioni di rilevamento JIT per una build finale o un'ottimizzazione dei controlli. È possibile farlo con un file di inizializzazione (INI).

Ad esempio, se l'assembly di cui si vuole eseguire il debug è denominato *MyApp. exe*, è possibile creare un file di testo denominato *MyApp. ini*nella stessa cartella di *MyApp. exe*, che contiene le tre righe seguenti:

```ini
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

È possibile impostare il valore di ogni opzione su 0 o 1 e per qualsiasi opzione assente verrà usato il valore predefinito 0. L'impostazione di `GenerateTrackingInfo` su 1 e di `AllowOptimize` su 0 consente di semplificare al massimo il debug.

A partire dalla versione di .NET Framework 2,0, il compilatore JIT genera sempre le informazioni di rilevamento indipendentemente dal valore per `GenerateTrackingInfo`; Tuttavia, il valore `AllowOptimize` ha ancora effetto. Quando si usa [Ngen.exe (generatore di immagini native)](../tools/ngen-exe-native-image-generator.md) per precompilare l'immagine nativa senza ottimizzazione, il file INI deve essere presente nella cartella di destinazione con `AllowOptimize=0` quando viene eseguito Ngen.exe. Se è stato precompilato un assembly senza ottimizzazione, è necessario rimuovere il codice precompilato usando l'opzione **/Uninstall** di Ngen. exe prima di rieseguire Ngen. exe per precompilare il codice come ottimizzato. Se il file ini non è presente nella cartella, per impostazione predefinita Ngen. exe precompila il codice come ottimizzato.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controlla le impostazioni per un assembly. **DebuggableAttribute** include due campi che controllano se il compilatore JIT deve ottimizzare e/o generare informazioni di rilevamento. A partire dalla versione di .NET Framework 2,0, il compilatore JIT genera sempre le informazioni di rilevamento.

Per una compilazione definitiva, i compilatori non impostano l'oggetto **DebuggableAttribute**. Per impostazione predefinita, il compilatore JIT genera le massime prestazioni, più difficili da eseguire il debug del codice macchina. L'abilitazione del rilevamento JIT riduce leggermente le prestazioni e la disabilitazione dell'ottimizzazione le riduce notevolmente.

**DebuggableAttribute** si applica a un intero assembly per volta, non ai singoli moduli all'interno dell'assembly. Gli strumenti di sviluppo devono quindi associare gli attributi personalizzati al token dei metadati di assembly, se un assembly è già stato creato, o alla classe chiamata **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. Lo strumento ALink promuove quindi gli attributi **DebuggableAttribute** da ogni modulo all'assembly di cui fanno parte. Se si verifica un conflitto, l'operazione ALink ha esito negativo.

> [!NOTE]
> Nella versione 1.0 di .NET Framework, il compilatore Microsoft Visual C++ aggiunge **DebuggableAttribute** quando vengono specificate le opzioni del compilatore **/clr** e **/Zi**. Nella versione 1,1 del .NET Framework è necessario aggiungere l'oggetto **DebuggableAttribute** manualmente nel codice oppure usare l'opzione del linker **/ASSEMBLYDEBUG** .

## <a name="see-also"></a>Vedere anche

- [Debug, analisi e profilatura](index.md)
- [Abilitazione del debug ad associazione JIT](enabling-jit-attach-debugging.md)
- [Abilitazione della funzione di profilatura](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
