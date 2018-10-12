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
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Procedura: Visualizzare il contenuto della Global Assembly Cache

Usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.

## <a name="view-the-assemblies-in-the-gac"></a>Visualizzare gli assembly nella Global Assembly Cache

Per visualizzare un elenco degli assembly nella Global Assembly Cache, aprire [Prompt dei comandi per gli sviluppatori per Visual Studio](../tools/developer-command-prompt-for-vs.md) e quindi immettere il comando seguente:

```shell
gacutil -l
```

oppure

```shell
gacutil /l
```

> [!NOTE]
> Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) consente di visualizzare la Global Assembly Cache in Esplora risorse. A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.

## <a name="see-also"></a>Vedere anche

- [Uso di assembly e della Global Assembly Cache](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md)