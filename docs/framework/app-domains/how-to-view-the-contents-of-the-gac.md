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
ms.openlocfilehash: 3650de934cb3d2940d0e8e971d03aff856bddfd7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515479"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="6e464-102">Procedura: visualizzare il contenuto della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6e464-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="6e464-103">Usare lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6e464-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="6e464-104">Per visualizzare un elenco degli assembly presenti nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6e464-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="6e464-105">Al [prompt dei comandi di Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6e464-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="6e464-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="6e464-106">**gacutil -l** </span></span>  
     <span data-ttu-id="6e464-107">oppure</span><span class="sxs-lookup"><span data-stu-id="6e464-107">-or-</span></span>  
    <span data-ttu-id="6e464-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="6e464-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="6e464-109">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) consente di visualizzare la Global Assembly Cache in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="6e464-109">In earlier versions of the .NET Framework, the [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="6e464-110">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6e464-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e464-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e464-111">See Also</span></span>  
 [<span data-ttu-id="6e464-112">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6e464-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="6e464-113">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="6e464-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
