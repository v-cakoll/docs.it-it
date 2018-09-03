---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sull'output pubblicato con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: e99000996f5dfa9f9d4f9b823e36ecbe325da835
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936026"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="0ef19-103">Testare l'output pubblicato con dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="0ef19-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="0ef19-104">È possibile eseguire test sull'output già pubblicato usando il comando `dotnet vstest`,</span><span class="sxs-lookup"><span data-stu-id="0ef19-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="0ef19-105">che funzionerà per i test xUnit, MSTest e NUnit.</span><span class="sxs-lookup"><span data-stu-id="0ef19-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="0ef19-106">È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="0ef19-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="0ef19-107">dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.</span><span class="sxs-lookup"><span data-stu-id="0ef19-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="0ef19-108">Esempio di esecuzione di test in una DLL pubblicata</span><span class="sxs-lookup"><span data-stu-id="0ef19-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="0ef19-109">Nota: se l'app specifica come destinazione un framework diverso da `netcoreapp`, è possibile eseguire il comando `dotnet vstest` passando il framework di destinazione con un flag framework.</span><span class="sxs-lookup"><span data-stu-id="0ef19-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="0ef19-110">Ad esempio `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="0ef19-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="0ef19-111">In Visual Studio 2017 Update 5 il framework desiderato viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0ef19-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ef19-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef19-112">See also</span></span>
- [<span data-ttu-id="0ef19-113">Unit test con test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="0ef19-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="0ef19-114">Unit test con test dotnet e NUnit</span><span class="sxs-lookup"><span data-stu-id="0ef19-114">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="0ef19-115">Unit test con test dotnet e MSTest</span><span class="sxs-lookup"><span data-stu-id="0ef19-115">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
