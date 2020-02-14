---
title: Strumenti per la portabilità in .NET Core
description: Informazioni su alcuni degli strumenti che è possibile usare per la portabilità in .NET Core
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 3b71c31b4f26b278b2bd1088adc8e9f64d28ab7b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215188"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="ad053-103">Strumenti di supporto per la portabilità in .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad053-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="ad053-104">Gli strumenti descritti in questo articolo possono risultare utili per la portabilità di:</span><span class="sxs-lookup"><span data-stu-id="ad053-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="ad053-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) : una procedura di base che consente di generare un report sulla portabilità del codice tra .NET Framework e .NET Core:</span><span class="sxs-lookup"><span data-stu-id="ad053-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="ad053-106">Come [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="ad053-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="ad053-107">Come [estensione di Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span><span class="sxs-lookup"><span data-stu-id="ad053-107">As a [Visual Studio extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="ad053-108">[Analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) - Analizzatore Roslyn che individua potenziali rischi di compatibilità per le API C# in piattaforme diverse e rileva le chiamate alle API deprecate.</span><span class="sxs-lookup"><span data-stu-id="ad053-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="ad053-109">È anche possibile provare a convertire soluzioni più piccole o singoli progetti al formato di file di progetto .NET Core con lo strumento [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).</span><span class="sxs-lookup"><span data-stu-id="ad053-109">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="ad053-110">CsprojToVs2017 è uno strumento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ad053-110">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="ad053-111">Non è garantito che funzioni per tutti i progetti e potrebbe causare lievi modifiche del comportamento di cui si dipende.</span><span class="sxs-lookup"><span data-stu-id="ad053-111">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="ad053-112">CsprojToVs2017 deve essere usato come _punto iniziale_ che automatizza gli elementi di base che possono essere automatizzati.</span><span class="sxs-lookup"><span data-stu-id="ad053-112">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="ad053-113">Non è una soluzione garantita per la migrazione dei formati di file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ad053-113">It is not a guaranteed solution to migrating project file formats.</span></span>
