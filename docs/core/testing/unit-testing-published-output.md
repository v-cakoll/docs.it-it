---
title: Eseguire il test pubblicati di output con vstest dotnet
description: Informazioni su come eseguire test su output pubblicato con il comando di vstest dotnet.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="d60ab-103">Eseguire il test pubblicati di output con vstest dotnet</span><span class="sxs-lookup"><span data-stu-id="d60ab-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="d60ab-104">È possibile eseguire test nell'output già pubblicato tramite il `dotnet vstest` comando.</span><span class="sxs-lookup"><span data-stu-id="d60ab-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="d60ab-105">Questa impostazione funziona su xUnit, MSTest e NUnit test.</span><span class="sxs-lookup"><span data-stu-id="d60ab-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="d60ab-106">È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="d60ab-106">Simply locate the DLL file that was part of your published output and run:</span></span>
```
dotnet vstest <MyPublishedTests>.dll
```
<span data-ttu-id="d60ab-107">dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.</span><span class="sxs-lookup"><span data-stu-id="d60ab-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

### <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="d60ab-108">Esempio di esecuzione di test in una DLL pubblicata</span><span class="sxs-lookup"><span data-stu-id="d60ab-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] <span data-ttu-id="d60ab-109">Nota: Se l'app è destinato a un framework diverso da `netcoreapp` è comunque possibile eseguire il `dotnet vstest` comando passando il framework di destinazione con un flag di framework.</span><span class="sxs-lookup"><span data-stu-id="d60ab-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="d60ab-110">Ad esempio `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="d60ab-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="d60ab-111">In Visual Studio 2017 aggiornamento 5 viene rilevato automaticamente il framework desiderato.</span><span class="sxs-lookup"><span data-stu-id="d60ab-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

### <a name="related-topics"></a><span data-ttu-id="d60ab-112">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d60ab-112">Related topics</span></span>
- [<span data-ttu-id="d60ab-113">Unit test con test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="d60ab-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="d60ab-114">Unit test con test dotnet e MSTest</span><span class="sxs-lookup"><span data-stu-id="d60ab-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
