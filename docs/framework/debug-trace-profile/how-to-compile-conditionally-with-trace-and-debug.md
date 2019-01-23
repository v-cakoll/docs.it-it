---
title: 'Procedura: Eseguire la compilazione condizionale con traccia e Debug'
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1738d73cf99c8b5a8131bd5e018a799c3a7780c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523558"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="eb3bf-102">Procedura: Eseguire la compilazione condizionale con traccia e Debug</span><span class="sxs-lookup"><span data-stu-id="eb3bf-102">How to: Compile Conditionally with Trace and Debug</span></span>
<span data-ttu-id="eb3bf-103">Quando si sottopone a debug l'applicazione durante la fase di sviluppo, sia l'output di tracciatura che l'output di debug vengono inviati alla finestra di output in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-103">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="eb3bf-104">Tuttavia, per includere funzionalità di tracciatura in un'applicazione distribuita, è necessario compilare le applicazioni instrumentate con la direttiva del compilatore **TRACE** abilitata.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-104">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="eb3bf-105">In questo modo è possibile tracciare il codice da compilare nella versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-105">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="eb3bf-106">Se non si abilita la direttiva **TRACE**, tutto il codice di tracciatura verrà ignorato durante la compilazione e non sarà incluso nel codice eseguibile da distribuire.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-106">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="eb3bf-107">Sia i metodi di debug che di tracciatura sono dotati di attributi condizionali associati.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-107">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="eb3bf-108">Ad esempio, se l'attributo condizionale per la traccia è **true**, tutte le istruzioni di traccia verranno incluse all'interno di un assembly, ovvero un file EXE o DLL compilato. Se l'attributo condizionale **Trace** è **false**, le istruzioni di traccia non verranno incluse.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-108">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="eb3bf-109">In una build è possibile attivare uno degli attributi condizionali **Trace** o **Debug**, entrambi gli attributi o nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-109">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="eb3bf-110">Di conseguenza, esistono quattro tipi di compilazione: **Eseguire il debug**, **traccia**, entrambi o nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-110">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="eb3bf-111">Alcune build di rilascio per la distribuzione della produzione non contengono alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-111">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="eb3bf-112">Le impostazioni del compilatore per l'applicazione possono essere specificate in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="eb3bf-112">You can specify the compiler settings for your application in several ways:</span></span>  
  
-   <span data-ttu-id="eb3bf-113">Pagine delle proprietà</span><span class="sxs-lookup"><span data-stu-id="eb3bf-113">The property pages</span></span>  
  
-   <span data-ttu-id="eb3bf-114">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="eb3bf-114">The command line</span></span>  
  
-   <span data-ttu-id="eb3bf-115">**#CONST** (per Visual Basic) e **#define** (per C#)</span><span class="sxs-lookup"><span data-stu-id="eb3bf-115">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="eb3bf-116">Per modificare le impostazioni di compilazione dalla finestra di dialogo delle pagine delle proprietà</span><span class="sxs-lookup"><span data-stu-id="eb3bf-116">To change compile settings from the property pages dialog box</span></span>  
  
1.  <span data-ttu-id="eb3bf-117">Fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-117">Right-click the project node in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="eb3bf-118">Scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-118">Choose **Properties** from the shortcut menu.</span></span>  
  
    -   <span data-ttu-id="eb3bf-119">In Visual Basic fare clic sulla scheda **Compila** nel riquadro sinistro della pagina delle proprietà e quindi fare clic sul pulsante **Opzioni di compilazione avanzate** per visualizzare la finestra di dialogo **Impostazioni del compilatore avanzate**.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-119">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="eb3bf-120">Selezionare le caselle di controllo per le impostazioni del compilatore che si vogliono attivare.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-120">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="eb3bf-121">Deselezionare le caselle di controllo per le impostazioni che si vogliono disabilitare.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-121">Clear the check boxes for settings you want to disable.</span></span>  
  
    -   <span data-ttu-id="eb3bf-122">In C# fare clic sulla scheda **Compila** nel riquadro sinistro della pagina delle proprietà e quindi selezionare le caselle di controllo per le impostazioni del compilatore che si vogliono abilitare.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-122">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="eb3bf-123">Deselezionare le caselle di controllo per le impostazioni che si vogliono disabilitare.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-123">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="eb3bf-124">Per compilare il codice instrumentato usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="eb3bf-124">To compile instrumented code using the command line</span></span>  
  
1.  <span data-ttu-id="eb3bf-125">Impostare un'opzione del compilatore condizionale sulla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-125">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="eb3bf-126">Il compilatore includerà il codice di traccia o di debug nell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-126">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="eb3bf-127">Ad esempio, l'istruzione del compilatore che segue, immessa sulla riga di comando, includerà il codice di tracciatura in un eseguibile compilato:</span><span class="sxs-lookup"><span data-stu-id="eb3bf-127">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="eb3bf-128">Per Visual Basic: **vbc-r:System.dll -d: TRACE = TRUE -d: DEBUG = FALSE MyApplication. vb**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-128">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="eb3bf-129">Per C#: **csc-r:System.dll -d: traccia -d: DEBUG = FALSE MyApplication.cs**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-129">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eb3bf-130">Per compilare più file dell'applicazione, lasciare uno spazio vuoto tra i nomi dei file, ad esempio: **MyApplication1.vb MyApplication2.vb MyApplication3.vb** o **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-130">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="eb3bf-131">Il significato delle direttive di compilazione condizionale usate nell'esempio precedente è riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eb3bf-131">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="eb3bf-132">Direttiva</span><span class="sxs-lookup"><span data-stu-id="eb3bf-132">Directive</span></span>|<span data-ttu-id="eb3bf-133">Significato</span><span class="sxs-lookup"><span data-stu-id="eb3bf-133">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="eb3bf-134">Visual Basic (compilatore)</span><span class="sxs-lookup"><span data-stu-id="eb3bf-134">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="eb3bf-135">Compilatore C#</span><span class="sxs-lookup"><span data-stu-id="eb3bf-135">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="eb3bf-136">Riferimenti a un assembly esterno (EXE o DLL)</span><span class="sxs-lookup"><span data-stu-id="eb3bf-136">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="eb3bf-137">Definizione di un simbolo di compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="eb3bf-137">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="eb3bf-138">È necessario scrivere TRACE o DEBUG con le lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-138">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="eb3bf-139">Per altre informazioni sui comandi di compilazione condizionale, immettere `vbc /?` (per Visual Basic) o `csc /?` (per C#) al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-139">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="eb3bf-140">Per altre informazioni, vedere [Compilazione dalla riga di comando (C#)](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) o [Utilizzo del compilatore dalla riga di comando (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md).</span><span class="sxs-lookup"><span data-stu-id="eb3bf-140">For more information, see [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) or [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="eb3bf-141">Per eseguire la compilazione condizionale con #CONST o #define</span><span class="sxs-lookup"><span data-stu-id="eb3bf-141">To perform conditional compilation using #CONST or #define</span></span>  
  
1.  <span data-ttu-id="eb3bf-142">Digitare l'istruzione adatta per il linguaggio di programmazione usato all'inizio del file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-142">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="eb3bf-143">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="eb3bf-143">Language</span></span>|<span data-ttu-id="eb3bf-144">Istruzione</span><span class="sxs-lookup"><span data-stu-id="eb3bf-144">Statement</span></span>|<span data-ttu-id="eb3bf-145">Risultato</span><span class="sxs-lookup"><span data-stu-id="eb3bf-145">Result</span></span>|  
    |--------------|---------------|------------|  
    |<span data-ttu-id="eb3bf-146">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-146">**Visual Basic**</span></span>|<span data-ttu-id="eb3bf-147">**#CONST TRACE = true**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-147">**#CONST TRACE = true**</span></span>|<span data-ttu-id="eb3bf-148">Abilita la traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-148">Enables tracing</span></span>|  
    ||<span data-ttu-id="eb3bf-149">**#CONST TRACE = false**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-149">**#CONST TRACE = false**</span></span>|<span data-ttu-id="eb3bf-150">Disabilita la traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-150">Disables tracing</span></span>|  
    ||<span data-ttu-id="eb3bf-151">**#CONST DEBUG = true**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-151">**#CONST DEBUG = true**</span></span>|<span data-ttu-id="eb3bf-152">Attiva il debug</span><span class="sxs-lookup"><span data-stu-id="eb3bf-152">Enables debugging</span></span>|  
    ||<span data-ttu-id="eb3bf-153">**#CONST DEBUG = false**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-153">**#CONST DEBUG = false**</span></span>|<span data-ttu-id="eb3bf-154">Disabilita il debug</span><span class="sxs-lookup"><span data-stu-id="eb3bf-154">Disables debugging</span></span>|  
    |<span data-ttu-id="eb3bf-155">**C#**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-155">**C#**</span></span>|<span data-ttu-id="eb3bf-156">**#define TRACE**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-156">**#define TRACE**</span></span>|<span data-ttu-id="eb3bf-157">Abilita la traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-157">Enables tracing</span></span>|  
    ||<span data-ttu-id="eb3bf-158">**#undef TRACE**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-158">**#undef TRACE**</span></span>|<span data-ttu-id="eb3bf-159">Disabilita la traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-159">Disables tracing</span></span>|  
    ||<span data-ttu-id="eb3bf-160">**#define DEBUG**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-160">**#define DEBUG**</span></span>|<span data-ttu-id="eb3bf-161">Attiva il debug</span><span class="sxs-lookup"><span data-stu-id="eb3bf-161">Enables debugging</span></span>|  
    ||<span data-ttu-id="eb3bf-162">**#undef DEBUG**</span><span class="sxs-lookup"><span data-stu-id="eb3bf-162">**#undef DEBUG**</span></span>|<span data-ttu-id="eb3bf-163">Disabilita il debug</span><span class="sxs-lookup"><span data-stu-id="eb3bf-163">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="eb3bf-164">Per disabilitare la traccia o il debug</span><span class="sxs-lookup"><span data-stu-id="eb3bf-164">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="eb3bf-165">Eliminare la direttiva del compilatore dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-165">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="eb3bf-166">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="eb3bf-166">\- or -</span></span>  
  
<span data-ttu-id="eb3bf-167">Impostare come commento la direttiva del compilatore.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-167">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb3bf-168">Al momento di avviare la compilazione è possibile scegliere **Compila** dal menu **Compila** o usare il metodo della riga di comando senza digitare **d:** per definire i simboli di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="eb3bf-168">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3bf-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb3bf-169">See also</span></span>
- [<span data-ttu-id="eb3bf-170">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="eb3bf-170">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="eb3bf-171">Procedura: Creare, inizializzare e configurare opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-171">How to: Create, Initialize and Configure Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="eb3bf-172">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-172">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="eb3bf-173">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="eb3bf-173">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
- [<span data-ttu-id="eb3bf-174">Procedura: Aggiungere istruzioni di traccia al codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="eb3bf-174">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="eb3bf-175">Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eb3bf-175">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [<span data-ttu-id="eb3bf-176">Procedura: Richiamare il compilatore da riga di comando</span><span class="sxs-lookup"><span data-stu-id="eb3bf-176">How to: Invoke the Command-Line Compiler</span></span>](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
