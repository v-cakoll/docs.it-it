---
title: 'Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
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
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 569683169c6d7ae50c33ed06d3b365a663f16715
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="65d24-102">Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="65d24-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>
<span data-ttu-id="65d24-103">Il file vsvars32.bat imposta le variabili di ambiente necessarie per abilitare le compilazioni da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="65d24-103">The vsvars32.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="65d24-104">Per altre informazioni su vsvars32.bat, vedere l[articolo della Knowledge Base Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="65d24-104">For more information about vsvars32.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  
  
 <span data-ttu-id="65d24-105">Se la versione corrente di Visual Studio è installata in un computer che include anche la versione precedente di Visual Studio, non eseguire vsvars32.bat o vcvars32.bat da diverse versioni nella stessa finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="65d24-105">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run vsvars32.bat or vcvars32.bat from different versions in the same Command Prompt window.</span></span>  
  
### <a name="to-run-vsvars32bat"></a><span data-ttu-id="65d24-106">Per eseguire VSVARS32.BAT</span><span class="sxs-lookup"><span data-stu-id="65d24-106">To run VSVARS32.BAT</span></span>  
  
1.  <span data-ttu-id="65d24-107">Dal menu **Start** aprire il **Prompt dei comandi per gli sviluppatori per VS2012**.</span><span class="sxs-lookup"><span data-stu-id="65d24-107">From the **Start** menu, open the **Developer Command Prompt for VS2012**.</span></span>  
  
2.  <span data-ttu-id="65d24-108">Passare alla sottodirectory di installazione Programmi\Microsoft Visual Studio *Version*\Common7\Tools o Programmi (x86)\Microsoft Visual Studio *Version*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="65d24-108">Change to the Program Files\Microsoft Visual Studio *Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools subdirectory of your installation.</span></span>  
  
3.  <span data-ttu-id="65d24-109">Eseguire VSVARS32.bat digitando **VSVARS32**.</span><span class="sxs-lookup"><span data-stu-id="65d24-109">Run VSVARS32.bat by typing **VSVARS32**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="65d24-110">Il file VSVARS32.bat può variare da computer a computer.</span><span class="sxs-lookup"><span data-stu-id="65d24-110">VSVARS32.bat can vary from computer to computer.</span></span> <span data-ttu-id="65d24-111">Non sostituire un file VSVARS32.bat mancante o danneggiato con un file VSVARS32.bat da un altro computer.</span><span class="sxs-lookup"><span data-stu-id="65d24-111">Do not replace a missing or damaged VSVARS32.bat file with a VSVARS32.bat from another computer.</span></span> <span data-ttu-id="65d24-112">Rieseguire invece l'installazione per sostituire il file mancante.</span><span class="sxs-lookup"><span data-stu-id="65d24-112">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d24-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65d24-113">See Also</span></span>  
 [<span data-ttu-id="65d24-114">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="65d24-114">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

