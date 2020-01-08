---
title: Come impostare le variabili di ambiente per la riga di comando di Visual Studio
ms.date: 12/20/2019
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 99e2a837877494dd4c7e0106047bce3cc39a9282
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342358"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="6c9e2-102">Come impostare le variabili di ambiente per la riga di comando di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6c9e2-102">How to set environment variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="6c9e2-103">Il file VsDevCmd.bat imposta le variabili di ambiente appropriate per abilitare le compilazioni da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="6c9e2-104">Visual Studio 2015 e versioni precedenti usavano VSVARS32. bat, non VsDevCmd. bat per lo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-104">Visual Studio 2015 and earlier versions used VSVARS32.bat, not VsDevCmd.bat for the same purpose.</span></span> <span data-ttu-id="6c9e2-105">Il file era archiviato in \Programmi\Microsoft Visual Studio\\*Versione*\Common7\Tools o Programmi (x86)\Microsoft Visual Studio\\*Versione*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-105">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="6c9e2-106">Se la versione corrente di Visual Studio è installata in un computer che include anche la versione precedente di Visual Studio, non eseguire VsDevCmd.bat e VSVARS32.BAT da diverse versioni nella stessa finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-106">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="6c9e2-107">È invece necessario eseguire il comando per ogni versione in una finestra specifica.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-107">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="6c9e2-108">Per eseguire VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="6c9e2-108">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="6c9e2-109">Dal menu **Start** aprire il **Prompt dei comandi per gli sviluppatori per vs 2019**.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-109">From the **Start** menu, open the **Developer Command Prompt for VS 2019**.</span></span>  <span data-ttu-id="6c9e2-110">Si trova nella cartella **Visual Studio 2019** .</span><span class="sxs-lookup"><span data-stu-id="6c9e2-110">It's in the **Visual Studio 2019** folder.</span></span>

2. <span data-ttu-id="6c9e2-111">Passare alla sottodirectory di installazione \Programmi\Microsoft Visual Studio\\*Versione*\\*Offerta*\Common7\Tools o \Programmi (x86)\Microsoft Visual Studio\\*Versione*\\*Offerta*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-111">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="6c9e2-112">(La*versione* è *2019* per la versione corrente.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-112">(*Version* is *2019* for the current version.</span></span> <span data-ttu-id="6c9e2-113">*Offerta* è *Enterprise*, *Professional* o *Community*.)</span><span class="sxs-lookup"><span data-stu-id="6c9e2-113">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="6c9e2-114">Eseguire VsDevCmd.bat digitando **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-114">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="6c9e2-115">Il file VsDevCmd.bat può variare da computer a computer.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-115">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="6c9e2-116">Non sostituire un file VsDevCmd.bat mancante o danneggiato con un file VsDevCmd.bat da un altro computer.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-116">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="6c9e2-117">Rieseguire invece l'installazione per sostituire il file mancante.</span><span class="sxs-lookup"><span data-stu-id="6c9e2-117">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="6c9e2-118">Opzioni disponibili per VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="6c9e2-118">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="6c9e2-119">Per visualizzare le opzioni disponibili per VsDevCmd.BAT, eseguire il comando con l'opzione `-help`:</span><span class="sxs-lookup"><span data-stu-id="6c9e2-119">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="6c9e2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c9e2-120">See also</span></span>

- [<span data-ttu-id="6c9e2-121">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="6c9e2-121">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
