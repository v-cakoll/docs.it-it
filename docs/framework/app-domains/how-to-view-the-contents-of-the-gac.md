---
title: 'Procedura: Visualizzare il contenuto della Global Assembly Cache'
description: Informazioni su come visualizzare il contenuto del Global Assembly Cache in .NET utilizzando lo strumento Global Assembly Cache (GAC) (gacutil.exe).
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
ms.openlocfilehash: 4d775efc073f3aad745eff7a7707efdec06172c2
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104695"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Procedura: Visualizzare il contenuto della Global Assembly Cache

Usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.

## <a name="view-the-assemblies-in-the-gac"></a>Visualizzare gli assembly nella Global Assembly Cache

Per visualizzare un elenco degli assembly nella Global Assembly Cache, aprire [Prompt dei comandi per gli sviluppatori per Visual Studio](../tools/developer-command-prompt-for-vs.md) e quindi immettere il comando seguente:

```shell
gacutil -l
```

-oppure-

```shell
gacutil /l
```

> [!NOTE]
> Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) consente di visualizzare la Global Assembly Cache in Esplora risorse. A partire da .NET Framework 4, Shfusion.dll è obsoleto.

## <a name="see-also"></a>Vedere anche

- [Utilizzo di assembly e della Global Assembly Cache](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md)
