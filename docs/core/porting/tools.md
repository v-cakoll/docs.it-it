---
title: Strumenti per la portabilità in .NET Core
description: Informazioni su alcuni degli strumenti che è possibile usare per la portabilità in .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795586"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="17378-103">Strumenti di supporto per la portabilità in .NET Core</span><span class="sxs-lookup"><span data-stu-id="17378-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="17378-104">Gli strumenti descritti in questo articolo possono risultare utili per la portabilità di:</span><span class="sxs-lookup"><span data-stu-id="17378-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="17378-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) : una procedura di base che consente di generare un report sulla portabilità del codice tra .NET Framework e .NET Core:</span><span class="sxs-lookup"><span data-stu-id="17378-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="17378-106">Come [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="17378-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="17378-107">Come [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="17378-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="17378-108">[Analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) : un analizzatore Roslyn che individua potenziali rischi di compatibilità per le API C# su piattaforme diverse e rileva le chiamate alle API deprecate.</span><span class="sxs-lookup"><span data-stu-id="17378-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>
- <span data-ttu-id="17378-109">[try-Convert](https://www.nuget.org/packages/try-convert/) : strumento globale .NET Core in grado di convertire un progetto o un'intera soluzione in .NET SDK, incluso lo strumento per lo trasferimento di app desktop a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="17378-109">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="17378-110">Non è consigliabile se è stata stabilita una compilazione più complessa (ad esempio, le attività, le destinazioni o le importazioni personalizzate) e vengono rifiutati molti tipi di progetto non compatibili con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="17378-110">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
