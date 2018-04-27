---
title: 'Procedura: richiamare il compilatore da riga di comando (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="8654d-102">Procedura: richiamare il compilatore da riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8654d-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="8654d-103">È possibile richiamare il compilatore della riga di comando digitando il nome del file eseguibile nella riga di comando, noto anche come finestra MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="8654d-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="8654d-104">Se esegue la compilazione dal prompt dei comandi di Windows predefinito, è necessario digitare il percorso completo del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8654d-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="8654d-105">Per eseguire l'override di questo comportamento predefinito, è possibile utilizzare il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] prompt dei comandi o modificare la variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="8654d-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="8654d-106">Entrambi consentono di eseguire la compilazione da qualsiasi directory digitando il nome del compilatore.</span><span class="sxs-lookup"><span data-stu-id="8654d-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="8654d-107">Per richiamare il compilatore utilizzando il prompt dei comandi di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8654d-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="8654d-108">Aprire la cartella di programma strumenti di Visual Studio all'interno del gruppo di programmi Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8654d-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="8654d-109">È possibile utilizzare il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] prompt dei comandi per accedere al compilatore da qualsiasi directory sul computer, se è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8654d-109">You can use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="8654d-110">Richiamare il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8654d-110">Invoke the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="8654d-111">Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8654d-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="8654d-112">Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory.</span><span class="sxs-lookup"><span data-stu-id="8654d-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="8654d-113">Se la directory contiene un file di origine denominato `Source.vb`, sarebbe possibile compilarlo digitando `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="8654d-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="8654d-114">Per impostare la variabile di ambiente PATH per il compilatore per il prompt dei comandi di Windows</span><span class="sxs-lookup"><span data-stu-id="8654d-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="8654d-115">Utilizzare la funzionalità di ricerca di Windows per trovare Vbc.exe sul disco locale.</span><span class="sxs-lookup"><span data-stu-id="8654d-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="8654d-116">Il nome esatto della directory in cui si trova il compilatore dipende dal percorso della directory di Windows e la versione di "Installato .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="8654d-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="8654d-117">Se si dispone di più di una versione di "Installato .NET Framework", è necessario determinare la versione da usare (in genere la versione più recente).</span><span class="sxs-lookup"><span data-stu-id="8654d-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="8654d-118">Dal **avviare** Menu, fare doppio clic su **risorse del Computer**e quindi fare clic su **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="8654d-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="8654d-119">Fare clic su di **avanzate** scheda e quindi fare clic su **le variabili di ambiente**.</span><span class="sxs-lookup"><span data-stu-id="8654d-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="8654d-120">Nel **sistema** riquadro variabili, seleziona **percorso** dall'elenco e fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="8654d-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="8654d-121">Nel **modifica sistema** variabili della finestra di dialogo spostare il punto di inserimento alla fine della stringa nel **valore della variabile** campo e digitare un punto e virgola (;) seguito dal nome completo della directory trovato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="8654d-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="8654d-122">Fare clic su **OK** per confermare le modifiche e chiudere le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8654d-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="8654d-123">Dopo aver modificato la variabile di ambiente PATH, è possibile eseguire il compilatore Visual Basic nel prompt dei comandi di Windows da qualsiasi directory nel computer.</span><span class="sxs-lookup"><span data-stu-id="8654d-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="8654d-124">Per richiamare il compilatore utilizzando il prompt dei comandi di Windows</span><span class="sxs-lookup"><span data-stu-id="8654d-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="8654d-125">Dal **avviare** menu, fare clic su di **Accessori** cartella e quindi aprire il **prompt dei comandi di Windows**.</span><span class="sxs-lookup"><span data-stu-id="8654d-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="8654d-126">Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8654d-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="8654d-127">Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory.</span><span class="sxs-lookup"><span data-stu-id="8654d-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="8654d-128">Se la directory contiene un file di origine denominato `Source.vb`, sarebbe possibile compilarlo digitando `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="8654d-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8654d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8654d-129">See Also</span></span>  
 [<span data-ttu-id="8654d-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8654d-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8654d-131">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="8654d-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
