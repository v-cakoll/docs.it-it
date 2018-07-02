---
title: Novità di C# - Guida a C#
description: Informazioni sull'evoluzione del linguaggio C#
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 399550178a12ff520dff033f0f1dc4a7cdfb9591
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314672"
---
# <a name="whats-new-in-c"></a>Novità di C# #

Questa pagina offre un riepilogo delle nuove funzionalità in ogni versione principale del linguaggio C#. I collegamenti seguenti forniscono informazioni dettagliate sulle principali funzionalità aggiunte in ogni versione.

> [!IMPORTANT]
> Il linguaggio C# si basa sui tipi e metodi in una *libreria standard* per alcune delle funzionalità. Un esempio è l'elaborazione delle eccezioni. Ogni istruzione o espressione `throw` viene controllata per assicurarsi che l'oggetto generato derivi da <xref:System.Exception>. Analogamente, ogni istruzione `catch` viene controllata per verificare che il tipo intercettato derivi da <xref:System.Exception>. In ogni versione potrebbero essere aggiunti nuovi requisiti. Per usare le funzionalità del linguaggio più recenti in ambienti meno recenti, potrebbe essere necessario installare librerie specifiche. Queste dipendenze sono documentate nella pagina per ogni versione specifica. Le informazioni sulle [relazioni tra linguaggio e libreria](relationships-between-language-and-library.md) possono essere utili per comprendere meglio questa dipendenza. 

Per usare le funzionalità più recenti in una versione a punti, è necessario [configurare la versione in lingua del compilatore](../language-reference/configure-language-version.md) e selezionare la versione.

* [C# 7.3](csharp-7-3.md):
  - Questa pagina descrive le funzionalità più recenti del linguaggio C#. C# 7.3 è attualmente disponibile in [Visual Studio 2017 versione 15.7](https://visualstudio.microsoft.com/vs/whatsnew/) e in [.NET Core 2.1 SDK 2.1.300 RC1](../../core/whats-new/index.md).
* [C# 7.2](csharp-7-2.md):
  - Questa pagina descrive le funzionalità aggiunte nel linguaggio C#. C# 7.2 è attualmente disponibile in [Visual Studio 2017 versione 15.5](https://visualstudio.microsoft.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).
* [C# 7.1](csharp-7-1.md):
  - Questa pagina descrive le funzionalità aggiunte in C# 7.1. Queste funzionalità sono state aggiunte in [Visual Studio 2017 versione 15.3](https://visualstudio.microsoft.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).
* [C# 7.0](csharp-7.md):
  - Questa pagina descrive le funzionalità aggiunte in C# 7.0. Queste funzionalità sono state aggiunte in [Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) e [.NET Core 1.0](../../core/whats-new/index.md) e versioni successive
* [C# 6](csharp-6.md):
  - Questa pagina descrive le funzionalità che sono state aggiunte in C# 6. Queste funzionalità sono disponibili in Visual Studio 2015 per gli sviluppatori Windows e in .NET Core 1.0 per gli sviluppatori che vogliono esplorare il linguaggio C# in macOS e Linux.
* [Supporto per più piattaforme](../../core/index.md):
  - Grazie al supporto per .NET Core, è possibile eseguire C# su diverse piattaforme. Gli utenti interessati a provare C# in macOS o su una delle diverse distribuzioni Linux supportate possono leggere le informazioni relative a .NET Core.
* [.NET Compiler Platform SDK](../roslyn-sdk/index.md):
  - .NET Compiler Platform SDK consente di scrivere codice che esegue analisi statiche nel codice C#. È possibile usare queste API per individuare potenziali errori o procedure sconsigliate, per suggerire correzioni e anche implementarle.

## <a name="previous-versions"></a>Versioni precedenti

Di seguito sono elencate le principali funzionalità introdotte in versioni precedenti del linguaggio C# e Visual Studio .NET.

* Visual Studio .NET 2013:
  - Questa versione di Visual Studio include correzioni di bug, miglioramenti delle prestazioni e Technology Preview di .NET Compiler Platform ("Roslyn") che è diventato [.NET Compiler Platform SDK](../roslyn-sdk/index.md).
* C# 5, Visual Studio .NET 2012:
  - `Async` / `await` e attributi delle [informazioni sul chiamante](../programming-guide/concepts/caller-information.md).
* C# 4, Visual Studio .NET 2010:
  - `Dynamic`, [argomenti denominati](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parametri facoltativi, [covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md) generiche.
* C# 3, Visual Studio .NET 2008:
  - Inizializzatori di oggetto e di raccolta, espressioni lambda, metodi di estensione, tipi anonimi, proprietà automatiche, inferenza del tipo `var` locale e [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).
* C# 2, Visual Studio .NET 2005:
  - Metodi anonimi, generics, tipi nullable, iteratori/yield, classi `static`, covarianza e controvarianza per i delegati.
* C# 1.1, Visual Studio .NET 2003:
  - Pragma `#line` e commenti documento xml.
* C# 1, Visual Studio .NET 2002:
  - La prima versione di [C#](../csharp.md).
