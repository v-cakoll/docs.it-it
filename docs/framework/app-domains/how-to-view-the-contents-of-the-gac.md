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
ms.openlocfilehash: d6e582f86eac03a51437b965f87f1bc7f29294eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="547f2-102">Procedura: visualizzare il contenuto della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="547f2-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="547f2-103">Usare lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="547f2-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="547f2-104">Per visualizzare un elenco degli assembly presenti nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="547f2-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="547f2-105">Al [prompt dei comandi di Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="547f2-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="547f2-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="547f2-106">**gacutil -l** </span></span>  
     <span data-ttu-id="547f2-107">oppure</span><span class="sxs-lookup"><span data-stu-id="547f2-107">-or-</span></span>  
    <span data-ttu-id="547f2-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="547f2-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="547f2-109">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) consente di visualizzare la Global Assembly Cache in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="547f2-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="547f2-110">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="547f2-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547f2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="547f2-111">See Also</span></span>  
 [<span data-ttu-id="547f2-112">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="547f2-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="547f2-113">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="547f2-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
