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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4142c3f12cc5a0e2277cc8dba28a281d5cf0ba55
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198215"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="a4634-102">Procedura: Visualizzare il contenuto della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a4634-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="a4634-103">Usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a4634-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="a4634-104">Visualizzare gli assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a4634-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="a4634-105">Per visualizzare un elenco degli assembly nella Global Assembly Cache, aprire [Prompt dei comandi per gli sviluppatori per Visual Studio](../tools/developer-command-prompt-for-vs.md) e quindi immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a4634-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="a4634-106">oppure</span><span class="sxs-lookup"><span data-stu-id="a4634-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="a4634-107">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) consente di visualizzare la Global Assembly Cache in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="a4634-107">In earlier versions of the .NET Framework, the [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="a4634-108">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a4634-108">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4634-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4634-109">See also</span></span>

- [<span data-ttu-id="a4634-110">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a4634-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="a4634-111">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="a4634-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)