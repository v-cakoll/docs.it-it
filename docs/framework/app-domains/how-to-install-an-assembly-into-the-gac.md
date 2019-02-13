---
title: 'Procedura: Installare un assembly nella Global Assembly Cache'
ms.date: 02/05/2019
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
ms.openlocfilehash: 233a7803cb59f9bfeac15d293dc3fb5a0db449c9
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903751"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Procedura: Installare un assembly nella Global Assembly Cache

Gli assembly condivisi da più applicazioni vengono archiviati nella Global Assembly Cache (GAC). Installare un assembly nella [Global Assembly Cache](gac.md) con uno dei componenti seguenti: 
- [Windows Installer](#windows-installer)
- [Strumento Global Assembly Cache](#global-assembly-cache-tool)

> [!IMPORTANT]
> Nella GAC possono essere installati solo assembly con nome sicuro. Per informazioni sulla creazione di un assembly con nome sicuro, vedere [Procedura: Firmare un assembly con un nome sicuro](how-to-sign-an-assembly-with-a-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache. Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità. Per creare un pacchetto di installazione per Windows Installer, usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Strumento Global Assembly Cache

È possibile usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly alla Global Assembly Cache e visualizzare il contenuto di tale cache.

   > [!NOTE]
   > *Gacutil.exe* è progettato esclusivamente per lo sviluppo. Non usarlo per installare assembly di produzione nella Global Assembly Cache.

La sintassi per usare *gacutil.exe* per installare un assembly nella Global Assembly Cache è la seguente:

```console
gacutil -i <assembly name>
```

In questo comando *\<nome assembly>* è il nome dell'assembly da installare nella Global Assembly Cache.

Se *gacutil.exe* non è presente nel percorso di sistema, usare il [Prompt dei comandi per gli sviluppatori per VS *\<versione>*](../tools/developer-command-prompt-for-vs.md).

L'esempio seguente consente di installare un assembly con nome file *hello.dll* nella Global Assembly Cache.

```console
gacutil -i hello.dll
```

> [!NOTE]
> Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows *Shfusion.dll* consente di installare gli assembly trascinandoli in Esplora file. A partire da .NET Framework 4, *Shfusion.dll* è obsoleto.

## <a name="see-also"></a>Vedere anche

- [Uso di assembly e della Global Assembly Cache](working-with-assemblies-and-the-gac.md)
- [Procedura: Rimuovere un assembly dalla Global Assembly Cache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md)
- [Procedura: Firmare un assembly con un nome sicuro](how-to-sign-an-assembly-with-a-strong-name.md)
