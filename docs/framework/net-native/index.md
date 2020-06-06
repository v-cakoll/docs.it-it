---
title: Compilazione di app con .NET Native
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
ms.openlocfilehash: 1f176e81905fe68c6d740a13240fe814659a7a59
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128380"
---
# <a name="compiling-apps-with-net-native"></a>Compilazione di app con .NET Native

.NET Native è una tecnologia di precompilazione per la compilazione e la distribuzione di app di Windows incluse in Visual Studio 2015 e versioni successive. che compila automaticamente la versione finale delle app scritte in codice gestito (C# o Visual Basic) e destina .NET Framework e Windows 10 al codice nativo.

In genere, le applicazioni che usano .NET Framework vengono compilate in Microsoft Intermediate Language (IL). In fase di esecuzione, il compilatore just-in-time (JIT) traduce IL in codice nativo. Al contrario, .NET Native compila le app di Windows direttamente nel codice nativo. Per gli sviluppatori, questo significa che:

- Le app offrono le prestazioni del codice nativo. In genere, le prestazioni saranno superiori a quelle del codice prima compilato in IL e quindi compilate in codice nativo dal compilatore JIT.

- È possibile continuare a programmare in c# o Visual Basic.

- È possibile continuare a sfruttare le risorse fornite da .NET Framework, tra cui la libreria di classi, gestione della memoria e Garbage Collection automatiche e la gestione delle eccezioni.

Per gli utenti delle app, .NET Native offre i vantaggi seguenti:

- Tempi di esecuzione più rapidi per la maggior parte delle app e degli scenari.

- Tempi di avvio più rapidi per la maggior parte delle app e degli scenari.

- Riduzione dei costi di distribuzione e aggiornamento.

- Utilizzo ottimizzato della memoria dell'app.

> [!IMPORTANT]
> Per la maggior parte delle app e degli scenari, .NET Native offre tempi di avvio notevolmente più veloci e prestazioni superiori rispetto a un'app compilata con IL o a un'immagine NGEN. Tuttavia, i risultati possono variare. Per assicurarsi che l'app abbia tratto vantaggio dai miglioramenti apportati alle prestazioni di .NET Native, è necessario confrontarne le prestazioni con quella della versione nativa di non-.NET dell'app. Per ulteriori informazioni, vedere [Cenni preliminari sulle sessioni di prestazioni](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).

Tuttavia .NET Native implica più di una compilazione in codice nativo. trasforma il modo in cui le applicazioni di .NET Framework vengono compilate ed eseguite. In particolare:

- Durante la precompilazione, le parti necessarie di .NET Framework vengono collegate staticamente nell'applicazione. Ciò consente di eseguire l'applicazione con le librerie app-local di .NET Framework e di effettuare l'analisi globale per offrire prestazioni ottimali del compilatore. Di conseguenza, l'avvio delle applicazioni sarà più rapido e coerente dopo l'aggiornamento di .NET Framework.

- Il runtime di .NET Native è ottimizzato per la precompilazione statica e nella maggior parte dei casi offre prestazioni superiori. Allo stesso tempo, mantiene le funzionalità di reflection di base che gli sviluppatori troveranno estremamente produttive.

- .NET Native usa lo stesso back-end del compilatore C++, che è ottimizzato per scenari di precompilazione statici.

.NET Native è in grado di sfruttare i vantaggi delle prestazioni di C++ agli sviluppatori di codice gestito, perché usa gli stessi strumenti o analoghi di C++ sotto la cappa, come illustrato in questa tabella.

||.NET Native|C++|
|-|----------------------------------------------------------------|-----------|
|Librerie|.NET Framework + Windows Runtime|Win32 + Windows Runtime|
|Compilatore|Compilatore di ottimizzazione UTC|Compilatore di ottimizzazione UTC|
|Distribuito|File binari Ready to run|File binari Ready to run (ASM)|
|Runtime|MRT.dll (Runtime CLR minimo)|CRT.dll (C Runtime)|

Per le app Windows per Windows 10, caricare i file binari per la compilazione con .NET Native in pacchetti di applicazioni (file APPX) in Windows Store.

## <a name="in-this-section"></a>Contenuto della sezione

Per altre informazioni sullo sviluppo di applicazioni con la compilazione con .NET Native, vedere i seguenti argomenti:

- [Introduzione alla compilazione con .NET Native: procedura dettagliata dell'esperienza di sviluppatore](getting-started-with-net-native.md)

- [Compilazione e .NET Native:](net-native-and-compilation.md) compilazione di un progetto in codice nativo con .NET Native.

- [Reflection e .NET Native](reflection-and-net-native.md)

  - [API basate sulla reflection](apis-that-rely-on-reflection.md)

  - [Riferimento all'API Reflection](net-native-reflection-api-reference.md)

  - [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)

- [Serializzazione e metadati](serialization-and-metadata.md)

- [Migrazione dell'app di Windows Store a .NET Native](migrating-your-windows-store-app-to-net-native.md)

- [Risoluzione dei problemi generale per .NET Native](net-native-general-troubleshooting.md)
