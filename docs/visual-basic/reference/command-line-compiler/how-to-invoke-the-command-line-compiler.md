---
title: 'Procedura: Richiamare il compilatore della riga di comando (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: dd5fadb9c9f248b5fb4f289bb2d24f1b085a79a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503729"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="9f1a6-102">Procedura: Richiamare il compilatore della riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f1a6-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="9f1a6-103">È possibile richiamare il compilatore della riga di comando digitando il nome del relativo file eseguibile nella riga di comando, noto anche come il prompt dei comandi MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="9f1a6-104">Se si esegue la compilazione dal prompt dei comandi di Windows predefinito, è necessario digitare il percorso completo del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="9f1a6-105">Per eseguire l'override di questo comportamento predefinito, è possibile usare il prompt dei comandi per gli sviluppatori per Visual Studio, o modificare la variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="9f1a6-106">Entrambi consentono di compilare da qualsiasi directory, è sufficiente digitare il nome del compilatore.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="9f1a6-107">Per richiamare il compilatore tramite il prompt dei comandi per gli sviluppatori per Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9f1a6-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>  
  
1.  <span data-ttu-id="9f1a6-108">Aprire la cartella di programma strumenti di Visual Studio all'interno del gruppo di programmi Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="9f1a6-109">È possibile utilizzare il prompt dei comandi per gli sviluppatori per Visual Studio per accedere al compilatore da qualsiasi directory nel computer, se è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="9f1a6-110">Richiamare il prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>  
  
4.  <span data-ttu-id="9f1a6-111">Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="9f1a6-112">Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="9f1a6-113">Se la directory contiene un file di origine denominato `Source.vb`, è possibile compilarlo digitando `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="9f1a6-114">Per impostare la variabile di ambiente PATH al compilatore per il prompt dei comandi di Windows</span><span class="sxs-lookup"><span data-stu-id="9f1a6-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="9f1a6-115">Usare la funzionalità di Windows Search per trovare Vbc.exe sul disco locale.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="9f1a6-116">Il nome esatto della directory in cui si trova il compilatore dipende la posizione della directory di Windows e la versione di "Installato .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="9f1a6-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="9f1a6-117">Se si dispone di più di una versione di ".NET Framework" installato, è necessario determinare la versione da usare (in genere la versione più recente).</span><span class="sxs-lookup"><span data-stu-id="9f1a6-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="9f1a6-118">Dalle **avviare** Menu, fare doppio clic su **risorse del Computer**e quindi fare clic su **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="9f1a6-119">Scegliere il **avanzate** scheda e quindi fare clic su **variabili di ambiente**.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="9f1a6-120">Nel **System** riquadro variabili, seleziona **Path** dall'elenco e fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="9f1a6-121">Nel **modifica sistema** sposta il punto di inserimento alla fine della stringa nella finestra di dialogo variabile il **il valore della variabile** campo e digitare un punto e virgola (;) seguito dal nome completo della directory trovato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="9f1a6-122">Fare clic su **OK** per confermare le modifiche e chiudere le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="9f1a6-123">Dopo aver modificato la variabile di ambiente PATH, è possibile eseguire il compilatore Visual Basic al prompt dei comandi di Windows da qualsiasi directory nel computer.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="9f1a6-124">Per richiamare il compilatore utilizzando il prompt dei comandi di Windows</span><span class="sxs-lookup"><span data-stu-id="9f1a6-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="9f1a6-125">Dal **avviare** menu, fare clic sui **Accessori** cartella e quindi aprire il **prompt dei comandi di Windows**.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="9f1a6-126">Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="9f1a6-127">Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="9f1a6-128">Se la directory contiene un file di origine denominato `Source.vb`, è possibile compilarlo digitando `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="9f1a6-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1a6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f1a6-129">See also</span></span>
- [<span data-ttu-id="9f1a6-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f1a6-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9f1a6-131">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="9f1a6-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
