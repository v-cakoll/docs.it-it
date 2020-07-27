---
title: Ilasm.exe (Assembler IL)
description: Iniziare a usare Ilasm.exe, l'assembler IL. Questo strumento genera un file eseguibile di tipo PE da Intermediate Language (IL).
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
ms.openlocfilehash: 1a85b3bf9509ffba6c2331d14196a6bef2bfa080
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166983"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="9e284-104">Ilasm.exe (Assembler IL)</span><span class="sxs-lookup"><span data-stu-id="9e284-104">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="9e284-105">L'assembler IL genera un file eseguibile di tipo PE dal linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="9e284-105">The IL Assembler generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="9e284-106">Per ulteriori informazioni su IL, vedere [processo di esecuzione gestita](../../standard/managed-execution-process.md). È possibile eseguire l'eseguibile risultante, che contiene il e i metadati necessari, per determinare se il linguaggio il viene eseguito come previsto.</span><span class="sxs-lookup"><span data-stu-id="9e284-106">(For more information on IL, see [Managed Execution Process](../../standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="9e284-107">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e284-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="9e284-108">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="9e284-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="9e284-109">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9e284-109">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="9e284-110">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9e284-110">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="9e284-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e284-111">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a><span data-ttu-id="9e284-112">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e284-112">Parameters</span></span>

| <span data-ttu-id="9e284-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="9e284-113">Argument</span></span> | <span data-ttu-id="9e284-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e284-114">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="9e284-115">Nome del file di origine .il.</span><span class="sxs-lookup"><span data-stu-id="9e284-115">The name of the .il source file.</span></span> <span data-ttu-id="9e284-116">Questo file è formato da direttive di dichiarazione di metadati e istruzioni IL simboliche.</span><span class="sxs-lookup"><span data-stu-id="9e284-116">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="9e284-117">È possibile fornire più argomenti di file di origine per produrre un unico file PE con *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="9e284-117">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="9e284-118">**Nota:** Verificare che l'ultima riga di codice nel file di origine con estensione il includa uno spazio vuoto finale o un carattere di fine riga.</span><span class="sxs-lookup"><span data-stu-id="9e284-118">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="9e284-119">Opzione</span><span class="sxs-lookup"><span data-stu-id="9e284-119">Option</span></span> | <span data-ttu-id="9e284-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e284-120">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="9e284-121">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="9e284-121">**/32bitpreferred**</span></span>|<span data-ttu-id="9e284-122">Crea un'immagine con preferenza per i 32 bit (PE32).</span><span class="sxs-lookup"><span data-stu-id="9e284-122">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="9e284-123">**/Alignment:**`integer`</span><span class="sxs-lookup"><span data-stu-id="9e284-123">**/alignment:** `integer`</span></span>|<span data-ttu-id="9e284-124">Imposta FileAlignment sul valore specificato da `integer` nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e284-124">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="9e284-125">Se la direttiva IL .alignment è specificata nel file, questa opzione ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="9e284-125">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="9e284-126">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="9e284-126">**/appcontainer**</span></span>|<span data-ttu-id="9e284-127">Produce un file *. dll* o *. exe* che viene eseguito nel contenitore dell'app Windows come output.</span><span class="sxs-lookup"><span data-stu-id="9e284-127">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="9e284-128">**/arm**</span><span class="sxs-lookup"><span data-stu-id="9e284-128">**/arm**</span></span>|<span data-ttu-id="9e284-129">Specifica Advanced RISC Machine (ARM) come processore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9e284-129">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="9e284-130">Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/32bitpreferred**.</span><span class="sxs-lookup"><span data-stu-id="9e284-130">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="9e284-131">**/base:**`integer`</span><span class="sxs-lookup"><span data-stu-id="9e284-131">**/base:** `integer`</span></span>|<span data-ttu-id="9e284-132">Imposta ImageBase sul valore specificato da `integer` nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e284-132">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="9e284-133">Se la direttiva IL .imagebase è specificata nel file, questa opzione ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="9e284-133">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="9e284-134">**/clock**</span><span class="sxs-lookup"><span data-stu-id="9e284-134">**/clock**</span></span>|<span data-ttu-id="9e284-135">Misura e segnala i seguenti tempi di compilazione in millisecondi per il file di origine .il specificato:</span><span class="sxs-lookup"><span data-stu-id="9e284-135">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="9e284-136">**Total Run**: tempo totale impiegato per l'esecuzione di tutte le operazioni specifiche che seguono.</span><span class="sxs-lookup"><span data-stu-id="9e284-136">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="9e284-137">**Startup**: caricamento e apertura del file.</span><span class="sxs-lookup"><span data-stu-id="9e284-137">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="9e284-138">**Emitting MD**: emissione di metadati.</span><span class="sxs-lookup"><span data-stu-id="9e284-138">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="9e284-139">**Ref to Def Resolution**: risoluzione dei riferimenti nelle definizioni nel file.</span><span class="sxs-lookup"><span data-stu-id="9e284-139">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="9e284-140">**CEE File Generation**: generazione dell'immagine del file in memoria.</span><span class="sxs-lookup"><span data-stu-id="9e284-140">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="9e284-141">**PE File Writing**: scrittura dell'immagine in un file PE.</span><span class="sxs-lookup"><span data-stu-id="9e284-141">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="9e284-142">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="9e284-142">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="9e284-143">Include informazioni di debug (nomi di variabili locali e di argomenti e numeri di riga).</span><span class="sxs-lookup"><span data-stu-id="9e284-143">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="9e284-144">Crea un file PDB.</span><span class="sxs-lookup"><span data-stu-id="9e284-144">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="9e284-145">Se si specifica **/debug** senza altri valori, viene disabilitata l'ottimizzazione JIT e vengono utilizzati i punti di sequenza dal file PDB.</span><span class="sxs-lookup"><span data-stu-id="9e284-145">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="9e284-146">**IMPL** disabilita l'ottimizzazione JIT e utilizza punti di sequenza impliciti.</span><span class="sxs-lookup"><span data-stu-id="9e284-146">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="9e284-147">**OPT** abilita l'ottimizzazione JIT e utilizza punti di sequenza impliciti.</span><span class="sxs-lookup"><span data-stu-id="9e284-147">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="9e284-148">**/dll**</span><span class="sxs-lookup"><span data-stu-id="9e284-148">**/dll**</span></span>|<span data-ttu-id="9e284-149">Produce un file con *estensione dll* come output.</span><span class="sxs-lookup"><span data-stu-id="9e284-149">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="9e284-150">**/enc:**`file`</span><span class="sxs-lookup"><span data-stu-id="9e284-150">**/enc:** `file`</span></span>|<span data-ttu-id="9e284-151">Crea file differenziali di Modifica e continuazione a partire dal file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="9e284-151">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="9e284-152">Questo argomento è esclusivamente per utilizzo didattico e non è supportato per un utilizzo commerciale.</span><span class="sxs-lookup"><span data-stu-id="9e284-152">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="9e284-153">**/exe**</span><span class="sxs-lookup"><span data-stu-id="9e284-153">**/exe**</span></span>|<span data-ttu-id="9e284-154">Produce un file eseguibile come output.</span><span class="sxs-lookup"><span data-stu-id="9e284-154">Produces an executable file as output.</span></span> <span data-ttu-id="9e284-155">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="9e284-155">This is the default.</span></span>|
|<span data-ttu-id="9e284-156">**/flags:**`integer`</span><span class="sxs-lookup"><span data-stu-id="9e284-156">**/flags:** `integer`</span></span>|<span data-ttu-id="9e284-157">Imposta ImageFlags sul valore specificato da `integer` nell'intestazione Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9e284-157">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="9e284-158">Se la direttiva IL .corflags è specificata nel file, questa opzione ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="9e284-158">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="9e284-159">Per un elenco di valori validi per *integer*, vedere CorHdr.h, COMIMAGE_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="9e284-159">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="9e284-160">**/fold**</span><span class="sxs-lookup"><span data-stu-id="9e284-160">**/fold**</span></span>|<span data-ttu-id="9e284-161">Raggruppa corpi di metodo identici in uno solo.</span><span class="sxs-lookup"><span data-stu-id="9e284-161">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="9e284-162">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="9e284-162">/**highentropyva**</span></span>|<span data-ttu-id="9e284-163">Genera in output un file eseguibile che supporta ASLR (Address Space Layout Randomization) a entropia elevata.</span><span class="sxs-lookup"><span data-stu-id="9e284-163">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="9e284-164">Impostazione predefinita per **/appcontainer**.</span><span class="sxs-lookup"><span data-stu-id="9e284-164">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="9e284-165">**/include:**`includePath`</span><span class="sxs-lookup"><span data-stu-id="9e284-165">**/include:** `includePath`</span></span>|<span data-ttu-id="9e284-166">Imposta un percorso per la ricerca di file inclusi con `#include`.</span><span class="sxs-lookup"><span data-stu-id="9e284-166">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="9e284-167">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="9e284-167">**/itanium**</span></span>|<span data-ttu-id="9e284-168">Specifica Intel Itanium come processore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9e284-168">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="9e284-169">Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="9e284-169">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="9e284-170">**/Key:**`keyFile`</span><span class="sxs-lookup"><span data-stu-id="9e284-170">**/key:** `keyFile`</span></span>|<span data-ttu-id="9e284-171">Compila `filename` con una firma sicura usando la chiave privata contenuta in `keyFile`.</span><span class="sxs-lookup"><span data-stu-id="9e284-171">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="9e284-172">**/Key** @`keySource`</span><span class="sxs-lookup"><span data-stu-id="9e284-172">**/key:** @`keySource`</span></span>|<span data-ttu-id="9e284-173">Compila `filename` con una firma sicura usando la chiave privata prodotta in `keySource`.</span><span class="sxs-lookup"><span data-stu-id="9e284-173">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="9e284-174">**/Listing**</span><span class="sxs-lookup"><span data-stu-id="9e284-174">**/listing**</span></span>|<span data-ttu-id="9e284-175">Produce un file di elenco sull'output standard.</span><span class="sxs-lookup"><span data-stu-id="9e284-175">Produces a listing file on the standard output.</span></span> <span data-ttu-id="9e284-176">Se si omette questa opzione, non verrà prodotto alcun file di elenco.</span><span class="sxs-lookup"><span data-stu-id="9e284-176">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="9e284-177">Questo parametro non è supportato in .NET Framework 2.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="9e284-177">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="9e284-178">**/MDV:**`versionString`</span><span class="sxs-lookup"><span data-stu-id="9e284-178">**/mdv:** `versionString`</span></span>|<span data-ttu-id="9e284-179">Imposta la stringa di versione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="9e284-179">Sets the metadata version string.</span></span>|
|<span data-ttu-id="9e284-180">**/MSV:** `major` .`minor`</span><span class="sxs-lookup"><span data-stu-id="9e284-180">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="9e284-181">Imposta la versione del flusso di metadati, dove `major` e `minor` sono numeri interi.</span><span class="sxs-lookup"><span data-stu-id="9e284-181">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="9e284-182">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="9e284-182">**/noautoinherit**</span></span>|<span data-ttu-id="9e284-183">Disabilita l'ereditarietà predefinita da <xref:System.Object> quando non è specificata alcuna classe base.</span><span class="sxs-lookup"><span data-stu-id="9e284-183">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="9e284-184">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="9e284-184">**/nocorstub**</span></span>|<span data-ttu-id="9e284-185">Elimina la generazione dello stub CORExeMain.</span><span class="sxs-lookup"><span data-stu-id="9e284-185">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="9e284-186">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="9e284-186">**/nologo**</span></span>|<span data-ttu-id="9e284-187">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e284-187">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="9e284-188">**/output:**`file.ext`</span><span class="sxs-lookup"><span data-stu-id="9e284-188">**/output:** `file.ext`</span></span>|<span data-ttu-id="9e284-189">Specifica il nome e l'estensione del file di output.</span><span class="sxs-lookup"><span data-stu-id="9e284-189">Specifies the output file name and extension.</span></span> <span data-ttu-id="9e284-190">Per impostazione predefinita, il nome del file di output corrisponde al nome del primo file di origine.</span><span class="sxs-lookup"><span data-stu-id="9e284-190">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="9e284-191">L'estensione predefinita è *. exe*.</span><span class="sxs-lookup"><span data-stu-id="9e284-191">The default extension is *.exe*.</span></span> <span data-ttu-id="9e284-192">Se si specifica l'opzione **/dll** , l'estensione predefinita sarà *. dll*.</span><span class="sxs-lookup"><span data-stu-id="9e284-192">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="9e284-193">**Nota:** Se si specifica **/output**:myfile.dll non viene impostata l'opzione **/dll** .</span><span class="sxs-lookup"><span data-stu-id="9e284-193">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="9e284-194">Se non si specifica **/dll**, il risultato sarà un file eseguibile denominato *myfile.dll*.</span><span class="sxs-lookup"><span data-stu-id="9e284-194">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="9e284-195">**/Optimize**</span><span class="sxs-lookup"><span data-stu-id="9e284-195">**/optimize**</span></span>|<span data-ttu-id="9e284-196">Ottimizza le istruzioni long convertendole in short.</span><span class="sxs-lookup"><span data-stu-id="9e284-196">Optimizes long instructions to short.</span></span> <span data-ttu-id="9e284-197">Ad esempio, `br` viene convertito in `br.s`.</span><span class="sxs-lookup"><span data-stu-id="9e284-197">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="9e284-198">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="9e284-198">**/pe64**</span></span>|<span data-ttu-id="9e284-199">Crea un'immagine a 64 bit (PE32+).</span><span class="sxs-lookup"><span data-stu-id="9e284-199">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="9e284-200">Se non è specificato il processore di destinazione, l'impostazione predefinita è `/itanium`.</span><span class="sxs-lookup"><span data-stu-id="9e284-200">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="9e284-201">**/PDB**</span><span class="sxs-lookup"><span data-stu-id="9e284-201">**/pdb**</span></span>|<span data-ttu-id="9e284-202">Crea un file PDB senza abilitare la traccia delle informazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="9e284-202">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="9e284-203">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="9e284-203">**/quiet**</span></span>|<span data-ttu-id="9e284-204">Specifica la modalità non interattiva. Non visualizza informazioni sullo stato dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9e284-204">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="9e284-205">**/Resource:**`file.res`</span><span class="sxs-lookup"><span data-stu-id="9e284-205">**/resource:** `file.res`</span></span>|<span data-ttu-id="9e284-206">Include il file di risorse specificato nel \* formato res nel file con *estensione exe* o *dll* risultante.</span><span class="sxs-lookup"><span data-stu-id="9e284-206">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="9e284-207">È possibile specificare un unico file .res con l'opzione **/resource** .</span><span class="sxs-lookup"><span data-stu-id="9e284-207">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="9e284-208">**/ssver:** `int` .`int`</span><span class="sxs-lookup"><span data-stu-id="9e284-208">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="9e284-209">Imposta il numero di versione del sottosistema nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e284-209">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="9e284-210">Per **/appcontainer** e **/arm** il numero minimo di versione è 6.02.</span><span class="sxs-lookup"><span data-stu-id="9e284-210">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="9e284-211">**/stack:**`stackSize`</span><span class="sxs-lookup"><span data-stu-id="9e284-211">**/stack:** `stackSize`</span></span>|<span data-ttu-id="9e284-212">Imposta su `stackSize`il valore di SizeOfStackReserve nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e284-212">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="9e284-213">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="9e284-213">**/stripreloc**</span></span>|<span data-ttu-id="9e284-214">Specifica che non sono necessarie rilocazioni di base.</span><span class="sxs-lookup"><span data-stu-id="9e284-214">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="9e284-215">**/SUBSYSTEM:**`integer`</span><span class="sxs-lookup"><span data-stu-id="9e284-215">**/subsystem:** `integer`</span></span>|<span data-ttu-id="9e284-216">Imposta il sottosistema sul valore specificato da `integer` nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e284-216">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="9e284-217">Se la direttiva IL .subsystem è specificata nel file, questo comando ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="9e284-217">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="9e284-218">Per un elenco di valori validi per `integer`, vedere winnt.h, IMAGE_SUBSYSTEM.</span><span class="sxs-lookup"><span data-stu-id="9e284-218">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="9e284-219">**/x64**</span><span class="sxs-lookup"><span data-stu-id="9e284-219">**/x64**</span></span>|<span data-ttu-id="9e284-220">Specifica un processore AMD a 64 bit come processore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9e284-220">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="9e284-221">Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="9e284-221">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="9e284-222">**/?**</span><span class="sxs-lookup"><span data-stu-id="9e284-222">**/?**</span></span>|<span data-ttu-id="9e284-223">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="9e284-223">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="9e284-224">Tutte le opzioni per *Ilasm.exe* non fanno distinzione tra maiuscole e minuscole e vengono riconosciute dalle prime tre lettere.</span><span class="sxs-lookup"><span data-stu-id="9e284-224">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="9e284-225">Ad esempio, **/LIS** è equivalente a **/Listing** e **/res**: myresfile. res è equivalente a **/Resource**: myresfile. res. Le opzioni che specificano gli argomenti accettano due punti (:) o un segno di uguale (=) come separatore tra l'opzione e l'argomento.</span><span class="sxs-lookup"><span data-stu-id="9e284-225">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="9e284-226">Ad esempio, **/output**:*file. ext* equivale a **/output** = *file. ext*.</span><span class="sxs-lookup"><span data-stu-id="9e284-226">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e284-227">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9e284-227">Remarks</span></span>

<span data-ttu-id="9e284-228">L'assembler IL consente ai fornitori di strumenti di progettare e implementare generatori IL.</span><span class="sxs-lookup"><span data-stu-id="9e284-228">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="9e284-229">Utilizzando *Ilasm.exe*, gli sviluppatori di strumenti e compilatori possono concentrarsi su il e sulla generazione di metadati senza preoccuparsi di emettere il nel formato di file PE.</span><span class="sxs-lookup"><span data-stu-id="9e284-229">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="9e284-230">Analogamente ad altri compilatori destinati al runtime, ad esempio C# e Visual Basic, *Ilasm.exe* non produce file oggetto intermedi e non richiede una fase di collegamento per creare un file PE.</span><span class="sxs-lookup"><span data-stu-id="9e284-230">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="9e284-231">L'assembler IL è in grado di esprimere tutte le funzionalità esistenti per IL e i metadati dei linguaggi di programmazione destinati al runtime.</span><span class="sxs-lookup"><span data-stu-id="9e284-231">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="9e284-232">In questo modo, il codice gestito scritto in uno qualsiasi di questi linguaggi di programmazione può essere espresso in modo adeguato nell'assembler IL e compilato con *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="9e284-232">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="9e284-233">È possibile che la compilazione abbia esito negativo se nell'ultima riga di codice del file di origine con estensione il non è presente uno spazio vuoto finale o un carattere di fine riga.</span><span class="sxs-lookup"><span data-stu-id="9e284-233">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="9e284-234">È possibile utilizzare *Ilasm.exe* insieme allo strumento complementare, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="9e284-234">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="9e284-235">*Ildasm.exe* accetta un file PE che contiene IL codice il e crea un file di testo appropriato come input per *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="9e284-235">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="9e284-236">Questo è utile, ad esempio, quando si compila codice in un linguaggio di programmazione che non supporta tutti gli attributi dei metadati del runtime.</span><span class="sxs-lookup"><span data-stu-id="9e284-236">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="9e284-237">Dopo aver compilato il codice ed eseguito l'output tramite *Ildasm.exe*, il file di testo il risultante può essere modificato manualmente per aggiungere gli attributi mancanti.</span><span class="sxs-lookup"><span data-stu-id="9e284-237">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="9e284-238">È quindi possibile eseguire questo file di testo tramite il *Ilasm.exe* per produrre un file eseguibile finale.</span><span class="sxs-lookup"><span data-stu-id="9e284-238">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="9e284-239">È inoltre possibile ricorrere a questa tecnica per produrre un unico file PE sulla base di più file PE generati da diversi compilatori.</span><span class="sxs-lookup"><span data-stu-id="9e284-239">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="9e284-240">Attualmente non è possibile avvalersi di questa tecnica con file PE contenenti codice nativo incorporato, ad esempio file PE prodotti da Visual C++.</span><span class="sxs-lookup"><span data-stu-id="9e284-240">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="9e284-241">Per fare in modo che questo utilizzo combinato di *Ildasm.exe* e *Ilasm.exe* il più accurato possibile, per impostazione predefinita l'assembler non sostituisce le codifiche brevi per quelle lunghe che potrebbero essere state scritte nelle origini il (o che potrebbero essere emesse da un altro compilatore).</span><span class="sxs-lookup"><span data-stu-id="9e284-241">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="9e284-242">Utilizzare l'opzione **/optimize** per sostituire le codifiche short quando possibile.</span><span class="sxs-lookup"><span data-stu-id="9e284-242">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="9e284-243">*Ildasm.exe* funziona solo su file su disco.</span><span class="sxs-lookup"><span data-stu-id="9e284-243">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="9e284-244">e non su file installati nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9e284-244">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="9e284-245">Per altre informazioni sulla grammatica di IL, vedere il file asmparse.grammar in Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9e284-245">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="version-information"></a><span data-ttu-id="9e284-246">Informazioni sulla versione</span><span class="sxs-lookup"><span data-stu-id="9e284-246">Version Information</span></span>

<span data-ttu-id="9e284-247">A partire da .NET Framework 4.5, è possibile associare un attributo personalizzato a un'implementazione di interfaccia usando codice analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="9e284-247">Starting with the .NET Framework 4.5, you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

```il
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

<span data-ttu-id="9e284-248">A partire da .NET Framework 4.5, è possibile specificare un BLOB (oggetto binario di grandi dimensioni) marshalling arbitrario usando la relativa rappresentazione binaria non elaborata, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9e284-248">Starting with the .NET Framework 4.5, you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="9e284-249">Per altre informazioni sulla grammatica di IL, vedere il file asmparse.grammar in Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9e284-249">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="9e284-250">Esempi</span><span class="sxs-lookup"><span data-stu-id="9e284-250">Examples</span></span>

<span data-ttu-id="9e284-251">Il comando che segue assembla il file IL *myTestFile.il* e produce l'eseguibile *myTestFile.exe*.</span><span class="sxs-lookup"><span data-stu-id="9e284-251">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="9e284-252">Il comando che segue assembla il file IL *myTestFile.il* e produce il file *.dll\*\*myTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="9e284-252">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="9e284-253">Il comando che segue assembla il file IL *myTestFile.il* e produce il file *.dll\*\*myNewTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="9e284-253">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="9e284-254">L'esempio di codice seguente illustra un'applicazione molto semplice che visualizza "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="9e284-254">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="9e284-255">sulla console.</span><span class="sxs-lookup"><span data-stu-id="9e284-255">to the console.</span></span> <span data-ttu-id="9e284-256">È possibile compilare questo codice e quindi utilizzare lo strumento [*Ildasm.exe*](ildasm-exe-il-disassembler.md) per generare un file il.</span><span class="sxs-lookup"><span data-stu-id="9e284-256">You can compile this code and then use the [*Ildasm.exe*](ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

<span data-ttu-id="9e284-257">L'esempio di codice IL riportato di seguito corrisponde al precedente esempio di codice C#.</span><span class="sxs-lookup"><span data-stu-id="9e284-257">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="9e284-258">È possibile compilare questo codice in un assembly mediante lo strumento IL Assembler.</span><span class="sxs-lookup"><span data-stu-id="9e284-258">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="9e284-259">Gli esempi di codice IL e C# visualizzano entrambi "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="9e284-259">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="9e284-260">sulla console.</span><span class="sxs-lookup"><span data-stu-id="9e284-260">to the console.</span></span>

```il
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a><span data-ttu-id="9e284-261">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e284-261">See also</span></span>

- [<span data-ttu-id="9e284-262">Strumenti</span><span class="sxs-lookup"><span data-stu-id="9e284-262">Tools</span></span>](index.md)
- [<span data-ttu-id="9e284-263">*Ildasm.exe* (disassembler il)</span><span class="sxs-lookup"><span data-stu-id="9e284-263">*Ildasm.exe* (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="9e284-264">Processo di esecuzione gestita</span><span class="sxs-lookup"><span data-stu-id="9e284-264">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="9e284-265">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="9e284-265">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
