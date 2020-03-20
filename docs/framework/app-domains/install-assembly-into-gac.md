---
title: 'Procedura: Installare un assembly nella Global Assembly Cache'
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 64878a795a7c5b790c8991064e32b82505685c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155563"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Procedura: Installare un assembly nella Global Assembly Cache

Gli assembly condivisi da più applicazioni vengono archiviati nella Global Assembly Cache (GAC). Installare un assembly nella [Global Assembly Cache](gac.md) con uno dei componenti seguenti:

- [Programma di installazione di Windows](#windows-installer)
- [Strumento Global Assembly Cache](#global-assembly-cache-tool)

> [!IMPORTANT]
> È possibile installare solo assembly con nome sicuro nella Global Assembly Cache. Per informazioni su come creare un assembly con nome sicuro, vedere [Procedura: firmare un assembly con un nome sicuro.](../../standard/assembly/sign-strong-name.md)

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache. Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità. Per creare un pacchetto di installazione per Windows Installer, usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Global Assembly Cache (strumento)

È possibile utilizzare [l'utilità .NET Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly alla Global Assembly Cache e visualizzare il contenuto della Global Assembly Cache.

   > [!NOTE]
   > *Gacutil.exe* è progettato esclusivamente per lo sviluppo. Non usarlo per installare assembly di produzione nella Global Assembly Cache.

La sintassi per usare *gacutil.exe* per installare un assembly nella Global Assembly Cache è la seguente:

```cmd
gacutil -i <assembly name>
```

In questo comando, * \<nome dell'assembly>* è il nome dell'assembly da installare nella Global Assembly Cache.

Se *gacutil.exe* non è presente nel percorso di sistema, utilizzare il [prompt dei comandi Developer per la versione VS * \<>* ](../tools/developer-command-prompt-for-vs.md).

L'esempio seguente consente di installare un assembly con nome file *hello.dll* nella Global Assembly Cache.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows *Shfusion.dll* consente di installare gli assembly trascinandoli in Esplora file. A partire da .NET Framework 4, *Shfusion.dll* è obsoleto.

## <a name="see-also"></a>Vedere anche

- [Utilizzare gli assembly e la Global Assembly Cache](working-with-assemblies-and-the-gac.md)
- [Procedura: rimuovere un assembly dalla Global Assembly Cache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md)
- [Procedura: firmare un assembly con un nome sicuroHow to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md)
