---
title: 'Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio'
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
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
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="85e77-102">Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85e77-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="85e77-103">Il file VsDevCmd.bat imposta le variabili di ambiente appropriate per abilitare le compilazioni da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="85e77-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="85e77-104">Per ulteriori informazioni su VsDevCmd.bat, vedere [della Knowledge Base Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="85e77-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  

> [!NOTE]
> <span data-ttu-id="85e77-105">Il file VsDevCmd.bat è un nuovo file fornito con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="85e77-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="85e77-106">Visual Studio 2015 e versioni precedenti utilizzato VSVARS32.bat allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="85e77-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="85e77-107">Questo file è stato archiviato in \Programmi\Microsoft Visual Studio\\*versione*\Common7\Tools o programmi (x86) \Microsoft Visual Studio\\*versione*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="85e77-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="85e77-108">Se la versione corrente di Visual Studio è installata in un computer che dispone anche di una versione precedente di Visual Studio, è necessario eseguire non VsDevCmd.bat e VSVARS32. BAT da diverse versioni nella stessa finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="85e77-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="85e77-109">In alternativa, è necessario eseguire il comando per ogni versione nella propria finestra.</span><span class="sxs-lookup"><span data-stu-id="85e77-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="85e77-110">Per eseguire VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="85e77-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="85e77-111">Dal **avviare** menu, aprire il **prompt dei comandi per sviluppatori per Visual Studio 2017**.</span><span class="sxs-lookup"><span data-stu-id="85e77-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="85e77-112">È il **Visual Studio 2017** cartella.</span><span class="sxs-lookup"><span data-stu-id="85e77-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="85e77-113">Modificare in \Programmi\Microsoft Visual Studio\\*versione*\\*offerta*\Common7\Tools o \Programmi file (x86) \Microsoft Visual Studio\\ *Versione*\\*offerta*\Common7\Tools sottodirectory dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="85e77-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="85e77-114">(*Versione* è *2017* per la versione corrente.</span><span class="sxs-lookup"><span data-stu-id="85e77-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="85e77-115">*Offerta* è uno dei *Enterprise*, *Professional* o *Community*.)</span><span class="sxs-lookup"><span data-stu-id="85e77-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="85e77-116">Eseguire VsDevCmd.bat digitando **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="85e77-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="85e77-117">VsDevCmd.bat può variare da computer a computer.</span><span class="sxs-lookup"><span data-stu-id="85e77-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="85e77-118">Non sostituire un file VsDevCmd.bat mancante o danneggiato con un VsDevCmd.bat da un altro computer.</span><span class="sxs-lookup"><span data-stu-id="85e77-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="85e77-119">Rieseguire invece l'installazione per sostituire il file mancante.</span><span class="sxs-lookup"><span data-stu-id="85e77-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e77-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85e77-120">See Also</span></span>  
 [<span data-ttu-id="85e77-121">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="85e77-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
