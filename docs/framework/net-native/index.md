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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6900bca2bd94f52ea5603c752681163cde52ce19
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="compiling-apps-with-net-native"></a>Compilazione di app con .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] è una tecnologia di precompilazione per la compilazione e distribuzione di App di Windows è inclusa con Visual Studio 2015 e versioni successive. che compila automaticamente la versione finale delle app scritte in codice gestito (C# o Visual Basic) e destina .NET Framework e Windows 10 al codice nativo.  
  
 In genere, le applicazioni che usano .NET Framework vengono compilate in Microsoft Intermediate Language (IL). In fase di esecuzione, il compilatore just-in-time (JIT) traduce IL in codice nativo. Al contrario, [!INCLUDE[net_native](../../../includes/net-native-md.md)] consente di compilare applicazioni Windows direttamente in codice nativo. Per gli sviluppatori, questo significa che:  
  
-   Le app offrono le prestazioni del codice nativo. In genere, le prestazioni sono superiori al codice che viene innanzitutto compilato a livello di integrità e quindi compilato in codice nativo dal compilatore JIT. 
  
-   È possibile continuare a programmare in c# o Visual Basic.  
  
-   È possibile continuare a sfruttare le risorse fornite da .NET Framework, tra cui la libreria di classi, gestione della memoria e Garbage Collection automatiche e la gestione delle eccezioni.  
  
 Per gli utenti delle applicazioni, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offre i seguenti vantaggi:  
  
-   Tempi di esecuzione per la maggior parte delle applicazioni e degli scenari.
  
-   Tempi di avvio per la maggior parte delle applicazioni e degli scenari. 
  
-   Bassi costi di distribuzione e aggiornamento.  
  
-   Utilizzo della memoria app ottimizzato.  

> [!IMPORTANT]
> Per la maggior parte delle applicazioni e degli scenari, .NET Native offre tempi di avvio molto più rapide e prestazioni superiori rispetto a un'app compilata a livello di integrità o a un'immagine NGEN. Tuttavia, i risultati possono variare. Per garantire che i miglioramenti delle prestazioni di .NET Native è stato oggetto di applicazione, è necessario confrontare le prestazioni con quello della versione dell'app non - .NET Native. Per ulteriori informazioni, vedere [Cenni preliminari sulle sessioni di prestazioni](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).
 
Ma [!INCLUDE[net_native](../../../includes/net-native-md.md)] prevede molto più di una semplice compilazione in codice nativo: trasforma il modo in cui le applicazioni di .NET Framework vengono compilate ed eseguite. In particolare:  
  
-   Durante la precompilazione, le parti necessarie di .NET Framework vengono collegate staticamente nell'applicazione. Ciò consente di eseguire l'applicazione con le librerie app-local di .NET Framework e di effettuare l'analisi globale per offrire prestazioni ottimali del compilatore. Di conseguenza, l'avvio delle applicazioni sarà più rapido e coerente dopo l'aggiornamento di .NET Framework.  
  
-   Il [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime è ottimizzato per la precompilazione statica e nella maggior parte dei casi offre prestazioni superiori. Allo stesso tempo, mantiene le funzionalità di reflection di base che gli sviluppatori troveranno estremamente produttive.  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)] usa lo stesso back-end del compilatore C++, che è ottimizzato per scenari di precompilazione statici.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] può offrire i vantaggi delle prestazioni di C++ agli sviluppatori di codice gestito perché usa strumenti identici o simili come C++ dietro le quinte, come illustrato in questa tabella.  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|C++|  
|-|----------------------------------------------------------------|-----------|  
|Librerie|.NET Framework + Windows Runtime|Win32 + Windows Runtime|  
|Compilatore|Compilatore di ottimizzazione UTC|Compilatore di ottimizzazione UTC|  
|Distribuito|File binari Ready to run|File binari Ready to run (ASM)|  
|Runtime|MRT.dll (Runtime CLR minimo)|CRT.dll (C Runtime)|  
  
 Per le app Windows per Windows 10, caricare i file binari per la compilazione con .NET Native in pacchetti di applicazioni (file APPX) in Windows Store.  
  
## <a name="in-this-section"></a>In questa sezione  
 Per altre informazioni sullo sviluppo di applicazioni con la compilazione con .NET Native, vedere i seguenti argomenti:  
  
-   [Introduzione alla compilazione con .NET Native: procedura dettagliata dell'esperienza di sviluppatore](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   [Compilazione e .NET Native:](../../../docs/framework/net-native/net-native-and-compilation.md) compilazione di un progetto in codice nativo con .NET Native.  
  
-   [Reflection e .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [API basate sulla reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [Riferimento all'API Reflection](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md) (Serializzazione e metadati)  
  
-   [Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) (Migrazione dell'app di Windows Store a .NET Native)  
  
-   [Risoluzione dei problemi generale per .NET Native](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
