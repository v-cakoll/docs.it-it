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
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Procedura: visualizzare il contenuto della Global Assembly Cache
Usare lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a>Per visualizzare un elenco degli assembly presenti nella Global Assembly Cache  
  
1.  Al [prompt dei comandi di Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) digitare il comando seguente:  
  
     **gacutil -l**   
     oppure  
    **gacutil /l**  
  
 Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) consente di visualizzare la Global Assembly Cache in Esplora risorse. A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di assembly e della Global Assembly Cache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Gacutil.exe (strumento Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
