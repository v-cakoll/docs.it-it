---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352349"
---
# <a name="-platform-visual-basic"></a><span data-ttu-id="ce244-102">-platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce244-102">-platform (Visual Basic)</span></span>
<span data-ttu-id="ce244-103">Consente di specificare la versione di Common Language Runtime (CLR) in grado di eseguire il file di output.</span><span class="sxs-lookup"><span data-stu-id="ce244-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce244-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce244-104">Syntax</span></span>  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce244-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="ce244-105">Arguments</span></span>  
  
|<span data-ttu-id="ce244-106">Termine</span><span class="sxs-lookup"><span data-stu-id="ce244-106">Term</span></span>|<span data-ttu-id="ce244-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="ce244-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="ce244-108">Compila l'assembly in modo da essere eseguito da CLR a 32 bit, compatibile con x86.</span><span class="sxs-lookup"><span data-stu-id="ce244-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="ce244-109">Compila l'assembly l'assemby in modo da essere eseguito da CLR a 64 bit su un computer che supporta il set di istruzioni AMD64 o EM64T.</span><span class="sxs-lookup"><span data-stu-id="ce244-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="ce244-110">Compila l'assembly in modo da essere eseguito da CLR a 64 bit su un computer dotato di processore Itanium.</span><span class="sxs-lookup"><span data-stu-id="ce244-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="ce244-111">Compila l'assembly in modo da essere eseguito su un computer con processore ARM (Advanced RISC Machine).</span><span class="sxs-lookup"><span data-stu-id="ce244-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="ce244-112">Compila l'assembly in modo da essere eseguito su qualsiasi piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ce244-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="ce244-113">L'applicazione verrà eseguita come applicazione a 32 bit su versioni di Windows a 32 bit e come applicazione a 64 bit su versioni di Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ce244-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="ce244-114">Questo flag è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ce244-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="ce244-115">Compila l'assembly in modo da essere eseguito su qualsiasi piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ce244-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="ce244-116">L'applicazione verrà eseguita come applicazione a 32 bit sia nelle versioni di Windows a 32 bit che in quelle a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ce244-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="ce244-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ce244-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce244-118">Note</span><span class="sxs-lookup"><span data-stu-id="ce244-118">Remarks</span></span>  
 <span data-ttu-id="ce244-119">Per specificare il tipo di processore di destinazione del file di output, usare l'opzione `-platform`.</span><span class="sxs-lookup"><span data-stu-id="ce244-119">Use the `-platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="ce244-120">In genere, gli assembly .NET Framework scritti in Visual Basic vengono sempre eseguiti, indipendentemente dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ce244-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="ce244-121">L'elaborazione di alcuni elementi può tuttavia risultare influenzata dalla piattaforma in uso.</span><span class="sxs-lookup"><span data-stu-id="ce244-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="ce244-122">I casi più comuni sono:</span><span class="sxs-lookup"><span data-stu-id="ce244-122">These common cases are:</span></span>  
  
- <span data-ttu-id="ce244-123">Strutture contenenti membri che cambiano dimensione in base alla piattaforma, ad esempio tutti i tipi puntatore.</span><span class="sxs-lookup"><span data-stu-id="ce244-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
- <span data-ttu-id="ce244-124">Operazioni aritmetiche che includono dimensioni costanti.</span><span class="sxs-lookup"><span data-stu-id="ce244-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
- <span data-ttu-id="ce244-125">Dichiarazioni pInvoke o COM non corrette che usano `Integer` anziché <xref:System.IntPtr> per gli handle.</span><span class="sxs-lookup"><span data-stu-id="ce244-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
- <span data-ttu-id="ce244-126">Casting di <xref:System.IntPtr> su `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ce244-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
- <span data-ttu-id="ce244-127">Uso dell'interoperabilità pInvoke o COM con componenti non disponibili in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="ce244-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="ce244-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span><span class="sxs-lookup"><span data-stu-id="ce244-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="ce244-129">In particolare:</span><span class="sxs-lookup"><span data-stu-id="ce244-129">Specifically:</span></span>  
  
- <span data-ttu-id="ce244-130">Se si specifica l'opzione per una piattaforma a 64 bit e l'applicazione viene eseguita su un computer a 32 bit, il messaggio di errore verrà visualizzato con maggiore anticipo e sarà maggiormente descrittivo del problema specifico rispetto all'errore che si verifica senza usare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ce244-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
- <span data-ttu-id="ce244-131">Se si imposta il flag `x86` e successivamente si usa un computer a 64 bit per l'elaborazione dell'applicazione, questa verrà eseguita nel sottosistema WOW e non a livello nativo.</span><span class="sxs-lookup"><span data-stu-id="ce244-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="ce244-132">In un sistema operativo Windows a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="ce244-132">On a 64-bit Windows operating system:</span></span>  
  
- <span data-ttu-id="ce244-133">Gli assembly compilati con l'opzione `-platform:x86` potranno essere eseguiti da CLR a 32 bit in WOW64.</span><span class="sxs-lookup"><span data-stu-id="ce244-133">Assemblies compiled with `-platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
- <span data-ttu-id="ce244-134">Gli eseguibili compilati con l'opzione `-platform:anycpu` potranno essere eseguiti da CLR a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ce244-134">Executables compiled with the `-platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
- <span data-ttu-id="ce244-135">Una DLL compilata con l'opzione `-platform:anycpu` potrà essere eseguita dallo stesso CLR del processo in cui viene caricata.</span><span class="sxs-lookup"><span data-stu-id="ce244-135">A DLL compiled with the `-platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
- <span data-ttu-id="ce244-136">Gli eseguibili compilati con l'opzione `-platform:anycpu32bitpreferred` potranno essere eseguiti da CLR a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="ce244-136">Executables that are compiled with `-platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="ce244-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ce244-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a><span data-ttu-id="ce244-138">To set -platform in the Visual Studio IDE</span><span class="sxs-lookup"><span data-stu-id="ce244-138">To set -platform in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="ce244-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span><span class="sxs-lookup"><span data-stu-id="ce244-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="ce244-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span><span class="sxs-lookup"><span data-stu-id="ce244-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="ce244-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ce244-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce244-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce244-142">Example</span></span>  
 <span data-ttu-id="ce244-143">L'esempio seguente mostra come usare l'opzione del compilatore `-platform`.</span><span class="sxs-lookup"><span data-stu-id="ce244-143">The following example illustrates how to use the `-platform` compiler option.</span></span>  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce244-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce244-144">See also</span></span>

- [<span data-ttu-id="ce244-145">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce244-145">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ce244-146">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce244-146">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ce244-147">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="ce244-147">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
