---
title: Installare un assembly nella Global Assembly Cache
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584581"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Procedura: Installare un assembly nella Global Assembly Cache

Esistono due modi per installare un assembly con nome sicuro nella Global Assembly Cache.

> [!IMPORTANT]
> Nella GAC possono essere installati solo assembly con nome sicuro. Per informazioni su come creare un assembly con nome sicuro, vedere [Procedura: Firmare un assembly con un nome sicuro](how-to-sign-an-assembly-with-a-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache. Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità. È possibile usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) per creare un pacchetto di installazione per Windows Installer.

## <a name="global-assembly-cache-tool"></a>Strumento Global Assembly Cache

È possibile usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly con nome sicuro alla Global Assembly Cache e visualizzare il contenuto di tale cache.

   > [!NOTE]
   > È necessario usare Gacutil.exe solo in fase di sviluppo e non se ne consiglia l'uso per l'installazione di assembly di produzione nella Global Assembly Cache.

La sintassi di gacutil è la seguente:

```shell
gacutil -i <assembly name>
```

In questo comando *nome assembly* è il nome dell'assembly da installare nella Global Assembly Cache.

L'esempio seguente consente di installare un assembly con nome file `hello.dll` nella Global Assembly Cache.

```shell
gacutil -i hello.dll
```

> [!NOTE]
> Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows Shfusion.dll consente di installare gli assembly trascinandoli in **Esplora file**. A partire da .NET Framework 4, Shfusion.dll è obsoleto.

## <a name="see-also"></a>Vedere anche

- [Uso di assembly e della Global Assembly Cache](working-with-assemblies-and-the-gac.md)
- [Procedura: Rimuovere un assembly dalla Global Assembly Cache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md)
- [Procedura: Firmare un assembly con un nome sicuro](how-to-sign-an-assembly-with-a-strong-name.md)