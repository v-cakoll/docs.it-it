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
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43394465"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="0d416-102">Procedura: visualizzare il contenuto della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="0d416-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="0d416-103">Usare lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="0d416-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="0d416-104">Per visualizzare un elenco degli assembly presenti nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="0d416-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="0d416-105">Al [prompt dei comandi di Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0d416-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="0d416-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="0d416-106">**gacutil -l** </span></span>  
     <span data-ttu-id="0d416-107">oppure</span><span class="sxs-lookup"><span data-stu-id="0d416-107">-or-</span></span>  
    <span data-ttu-id="0d416-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="0d416-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="0d416-109">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) consente di visualizzare la Global Assembly Cache in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="0d416-109">In earlier versions of the .NET Framework, the [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="0d416-110">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0d416-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d416-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d416-111">See Also</span></span>  
 [<span data-ttu-id="0d416-112">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="0d416-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="0d416-113">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="0d416-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
