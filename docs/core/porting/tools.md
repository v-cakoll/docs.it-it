---
title: Strumenti per la portabilità in .NET Core
description: Informazioni su alcuni degli strumenti che è possibile usare per la portabilità in .NET Core
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 64bad7600d8e17ada83d4bd8bc56762fd1789f43
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989129"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="710a6-103">Strumenti di supporto per la portabilità in .NET Core</span><span class="sxs-lookup"><span data-stu-id="710a6-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="710a6-104">Gli strumenti descritti in questo articolo possono risultare utili per la portabilità di:</span><span class="sxs-lookup"><span data-stu-id="710a6-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="710a6-105">[.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) una catena di strumenti che può generare un report sulla portabilità del codice tra .NET Framework e .NET Core:</span><span class="sxs-lookup"><span data-stu-id="710a6-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="710a6-106">Come [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="710a6-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="710a6-107">Come [estensione](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="710a6-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="710a6-108">[Analizzatore di API .NET:](../../standard/analyzers/api-analyzer.md) analizzatore Roslyn che individua i potenziali rischi di compatibilità per le API di C' su piattaforme diverse e rileva le chiamate alle API deprecate.</span><span class="sxs-lookup"><span data-stu-id="710a6-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="710a6-109">È anche possibile provare a convertire soluzioni più piccole o singoli progetti al formato di file di progetto .NET Core con lo strumento [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).</span><span class="sxs-lookup"><span data-stu-id="710a6-109">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING]
> <span data-ttu-id="710a6-110">CsprojToVs2017 è uno strumento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="710a6-110">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="710a6-111">Non è garantito che funzioni per tutti i progetti e potrebbe causare lievi modifiche del comportamento di cui si dipende.</span><span class="sxs-lookup"><span data-stu-id="710a6-111">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="710a6-112">CsprojToVs2017 deve essere usato come _punto iniziale_ che automatizza gli elementi di base che possono essere automatizzati.</span><span class="sxs-lookup"><span data-stu-id="710a6-112">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="710a6-113">Non è una soluzione garantita per la migrazione dei formati di file di progetto.</span><span class="sxs-lookup"><span data-stu-id="710a6-113">It is not a guaranteed solution to migrating project file formats.</span></span>
