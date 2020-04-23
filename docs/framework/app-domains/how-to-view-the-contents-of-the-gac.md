---
title: 'Procedura: visualizzare il contenuto della Global Assembly Cache'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: b5d8b31e7eb23789878da620f3a4517056a1ee3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119825"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="bfcdd-102">Procedura: Visualizzare il contenuto della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="bfcdd-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="bfcdd-103">Usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="bfcdd-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="bfcdd-104">Visualizzare gli assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="bfcdd-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="bfcdd-105">Per visualizzare un elenco degli assembly nella Global Assembly Cache, aprire [Prompt dei comandi per gli sviluppatori per Visual Studio](../tools/developer-command-prompt-for-vs.md) e quindi immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bfcdd-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="bfcdd-106">-oppure-</span><span class="sxs-lookup"><span data-stu-id="bfcdd-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="bfcdd-107">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) consente di visualizzare la Global Assembly Cache in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="bfcdd-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="bfcdd-108">A partire da .NET Framework 4, Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="bfcdd-108">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfcdd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfcdd-109">See also</span></span>

- [<span data-ttu-id="bfcdd-110">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="bfcdd-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="bfcdd-111">Gacutil. exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="bfcdd-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
