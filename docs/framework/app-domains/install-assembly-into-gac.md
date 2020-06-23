---
title: 'Procedura: Installare un assembly nella Global Assembly Cache'
description: Installare un assembly nel Global Assembly Cache (GAC) in .NET in modo che possa essere condiviso da molte applicazioni. Utilizzare Windows Installer o l'utilità GAC.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 08a5475d74327265f28b65676ae56be15afb57d3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104671"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Procedura: Installare un assembly nella Global Assembly Cache

Gli assembly condivisi da più applicazioni vengono archiviati nella Global Assembly Cache (GAC). Installare un assembly nella [Global Assembly Cache](gac.md) con uno dei componenti seguenti:

- [Windows Installer](#windows-installer)
- [Strumento Global assembly cache](#global-assembly-cache-tool)

> [!IMPORTANT]
> È possibile installare solo assembly con nome sicuro in Global Assembly Cache. Per informazioni su come creare un assembly con nome sicuro, vedere [procedura: firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache. Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità. Per creare un pacchetto di installazione per Windows Installer, usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Global Assembly Cache (strumento)

È possibile utilizzare l' [utilità Global Assembly Cache (gacutil.exe) di .NET](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly al Global assembly cache e visualizzare il contenuto del Global assembly cache.

   > [!NOTE]
   > *Gacutil.exe* è progettato esclusivamente per lo sviluppo. Non usarlo per installare assembly di produzione nella Global Assembly Cache.

La sintassi per usare *gacutil.exe* per installare un assembly nella Global Assembly Cache è la seguente:

```cmd
gacutil -i <assembly name>
```

In questo comando *\<assembly name>* è il nome dell'assembly da installare nel Global assembly cache.

Se *gacutil.exe* non è presente nel percorso di sistema, usare il [prompt dei comandi *\<version>* per gli sviluppatori per Visual ](../tools/developer-command-prompt-for-vs.md)Studio.

L'esempio seguente consente di installare un assembly con nome file *hello.dll* nella Global Assembly Cache.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows *Shfusion.dll* consente di installare gli assembly trascinandoli in Esplora file. A partire da .NET Framework 4, *Shfusion.dll* è obsoleto.

## <a name="see-also"></a>Vedere anche

- [Usare gli assembly e i Global Assembly Cache](working-with-assemblies-and-the-gac.md)
- [Procedura: rimuovere un assembly dalla Global Assembly Cache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (strumento Global assembly cache)](../tools/gacutil-exe-gac-tool.md)
- [Procedura: firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md)
