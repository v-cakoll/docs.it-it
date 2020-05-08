---
title: Ilasm.exe (Assembler IL)
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
ms.openlocfilehash: cb995e78e534048043886070536ef0dd0a45c057
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73105096"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="f5d6b-102">Ilasm.exe (Assembler IL)</span><span class="sxs-lookup"><span data-stu-id="f5d6b-102">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="f5d6b-103">L'assembler IL genera un file eseguibile di tipo PE dal linguaggio intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-103">The IL Assembler generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="f5d6b-104">Per ulteriori informazioni su IL, vedere [processo di esecuzione gestita](../../standard/managed-execution-process.md). È possibile eseguire l'eseguibile risultante, che contiene il e i metadati necessari, per determinare se il linguaggio il viene eseguito come previsto.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-104">(For more information on IL, see [Managed Execution Process](../../standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="f5d6b-105">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f5d6b-106">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-106">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="f5d6b-107">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-107">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="f5d6b-108">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f5d6b-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="f5d6b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5d6b-109">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a><span data-ttu-id="f5d6b-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5d6b-110">Parameters</span></span>

| <span data-ttu-id="f5d6b-111">Argomento</span><span class="sxs-lookup"><span data-stu-id="f5d6b-111">Argument</span></span> | <span data-ttu-id="f5d6b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5d6b-112">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="f5d6b-113">Nome del file di origine .il.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-113">The name of the .il source file.</span></span> <span data-ttu-id="f5d6b-114">Questo file è formato da direttive di dichiarazione di metadati e istruzioni IL simboliche.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-114">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="f5d6b-115">È possibile fornire più argomenti di file di origine per produrre un unico file PE con *Ilasm. exe*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-115">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="f5d6b-116">**Nota:** Verificare che l'ultima riga di codice nel file di origine con estensione il includa uno spazio vuoto finale o un carattere di fine riga.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-116">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="f5d6b-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="f5d6b-117">Option</span></span> | <span data-ttu-id="f5d6b-118">Description</span><span class="sxs-lookup"><span data-stu-id="f5d6b-118">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="f5d6b-119">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-119">**/32bitpreferred**</span></span>|<span data-ttu-id="f5d6b-120">Crea un'immagine con preferenza per i 32 bit (PE32).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-120">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="f5d6b-121">**/Alignment:**`integer`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-121">**/alignment:** `integer`</span></span>|<span data-ttu-id="f5d6b-122">Imposta FileAlignment sul valore specificato da `integer` nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-122">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="f5d6b-123">Se la direttiva IL .alignment è specificata nel file, questa opzione ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-123">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="f5d6b-124">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-124">**/appcontainer**</span></span>|<span data-ttu-id="f5d6b-125">Produce un file *. dll* o *. exe* che viene eseguito nel contenitore dell'app Windows come output.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-125">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="f5d6b-126">**/arm**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-126">**/arm**</span></span>|<span data-ttu-id="f5d6b-127">Specifica Advanced RISC Machine (ARM) come processore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-127">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="f5d6b-128">Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/32bitpreferred**.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-128">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="f5d6b-129">**/base:**`integer`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-129">**/base:** `integer`</span></span>|<span data-ttu-id="f5d6b-130">Imposta ImageBase sul valore specificato da `integer` nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-130">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="f5d6b-131">Se la direttiva IL .imagebase è specificata nel file, questa opzione ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-131">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="f5d6b-132">**/clock**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-132">**/clock**</span></span>|<span data-ttu-id="f5d6b-133">Misura e segnala i seguenti tempi di compilazione in millisecondi per il file di origine .il specificato:</span><span class="sxs-lookup"><span data-stu-id="f5d6b-133">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="f5d6b-134">**Total Run**: tempo totale impiegato per l'esecuzione di tutte le operazioni specifiche che seguono.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-134">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="f5d6b-135">**Startup**: caricamento e apertura del file.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-135">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="f5d6b-136">**Emitting MD**: emissione di metadati.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-136">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="f5d6b-137">**Ref to Def Resolution**: risoluzione dei riferimenti nelle definizioni nel file.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-137">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="f5d6b-138">**CEE File Generation**: generazione dell'immagine del file in memoria.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-138">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="f5d6b-139">**PE File Writing**: scrittura dell'immagine in un file PE.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-139">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="f5d6b-140">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="f5d6b-140">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="f5d6b-141">Include informazioni di debug (nomi di variabili locali e di argomenti e numeri di riga).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-141">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="f5d6b-142">Crea un file PDB.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-142">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="f5d6b-143">Se si specifica **/debug** senza altri valori, viene disabilitata l'ottimizzazione JIT e vengono utilizzati i punti di sequenza dal file PDB.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-143">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="f5d6b-144">**IMPL** disabilita l'ottimizzazione JIT e utilizza punti di sequenza impliciti.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-144">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="f5d6b-145">**OPT** abilita l'ottimizzazione JIT e utilizza punti di sequenza impliciti.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-145">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="f5d6b-146">**/dll**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-146">**/dll**</span></span>|<span data-ttu-id="f5d6b-147">Produce un file con *estensione dll* come output.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-147">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="f5d6b-148">**/enc:**`file`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-148">**/enc:** `file`</span></span>|<span data-ttu-id="f5d6b-149">Crea file differenziali di Modifica e continuazione a partire dal file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-149">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="f5d6b-150">Questo argomento è esclusivamente per utilizzo didattico e non è supportato per un utilizzo commerciale.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-150">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="f5d6b-151">**/exe**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-151">**/exe**</span></span>|<span data-ttu-id="f5d6b-152">Produce un file eseguibile come output.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-152">Produces an executable file as output.</span></span> <span data-ttu-id="f5d6b-153">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-153">This is the default.</span></span>|
|<span data-ttu-id="f5d6b-154">**/flags:**`integer`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-154">**/flags:** `integer`</span></span>|<span data-ttu-id="f5d6b-155">Imposta ImageFlags sul valore specificato da `integer` nell'intestazione Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-155">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="f5d6b-156">Se la direttiva IL .corflags è specificata nel file, questa opzione ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-156">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="f5d6b-157">Per un elenco di valori validi per *integer*, vedere CorHdr.h, COMIMAGE_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-157">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="f5d6b-158">**/fold**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-158">**/fold**</span></span>|<span data-ttu-id="f5d6b-159">Raggruppa corpi di metodo identici in uno solo.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-159">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="f5d6b-160">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-160">/**highentropyva**</span></span>|<span data-ttu-id="f5d6b-161">Genera in output un file eseguibile che supporta ASLR (Address Space Layout Randomization) a entropia elevata.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-161">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="f5d6b-162">Impostazione predefinita per **/appcontainer**.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-162">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="f5d6b-163">**/include:**`includePath`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-163">**/include:** `includePath`</span></span>|<span data-ttu-id="f5d6b-164">Imposta un percorso per la ricerca di file inclusi con `#include`.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-164">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="f5d6b-165">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-165">**/itanium**</span></span>|<span data-ttu-id="f5d6b-166">Specifica Intel Itanium come processore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-166">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="f5d6b-167">Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-167">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="f5d6b-168">**/Key:**`keyFile`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-168">**/key:** `keyFile`</span></span>|<span data-ttu-id="f5d6b-169">Compila `filename` con una firma sicura usando la chiave privata contenuta in `keyFile`.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-169">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="f5d6b-170">**/Key** @`keySource`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-170">**/key:** @`keySource`</span></span>|<span data-ttu-id="f5d6b-171">Compila `filename` con una firma sicura usando la chiave privata prodotta in `keySource`.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-171">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="f5d6b-172">**/Listing**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-172">**/listing**</span></span>|<span data-ttu-id="f5d6b-173">Produce un file di elenco sull'output standard.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-173">Produces a listing file on the standard output.</span></span> <span data-ttu-id="f5d6b-174">Se si omette questa opzione, non verrà prodotto alcun file di elenco.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-174">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="f5d6b-175">Questo parametro non è supportato in .NET Framework 2.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-175">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="f5d6b-176">**/MDV:**`versionString`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-176">**/mdv:** `versionString`</span></span>|<span data-ttu-id="f5d6b-177">Imposta la stringa di versione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-177">Sets the metadata version string.</span></span>|
|<span data-ttu-id="f5d6b-178">**/MSV:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-178">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="f5d6b-179">Imposta la versione del flusso di metadati, dove `major` e `minor` sono numeri interi.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-179">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="f5d6b-180">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-180">**/noautoinherit**</span></span>|<span data-ttu-id="f5d6b-181">Disabilita l'ereditarietà predefinita da <xref:System.Object> quando non è specificata alcuna classe base.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-181">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="f5d6b-182">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-182">**/nocorstub**</span></span>|<span data-ttu-id="f5d6b-183">Elimina la generazione dello stub CORExeMain.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-183">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="f5d6b-184">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-184">**/nologo**</span></span>|<span data-ttu-id="f5d6b-185">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-185">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="f5d6b-186">**/output:**`file.ext`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-186">**/output:** `file.ext`</span></span>|<span data-ttu-id="f5d6b-187">Specifica il nome e l'estensione del file di output.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-187">Specifies the output file name and extension.</span></span> <span data-ttu-id="f5d6b-188">Per impostazione predefinita, il nome del file di output corrisponde al nome del primo file di origine.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-188">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="f5d6b-189">L'estensione predefinita è *. exe*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-189">The default extension is *.exe*.</span></span> <span data-ttu-id="f5d6b-190">Se si specifica l'opzione **/dll** , l'estensione predefinita sarà *. dll*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-190">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="f5d6b-191">**Nota:** Se si specifica **/output**: myfile. dll, non viene impostata l'opzione **/dll** .</span><span class="sxs-lookup"><span data-stu-id="f5d6b-191">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="f5d6b-192">Se non si specifica **/dll**, il risultato sarà un file eseguibile denominato *MyFile. dll*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-192">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="f5d6b-193">**/Optimize**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-193">**/optimize**</span></span>|<span data-ttu-id="f5d6b-194">Ottimizza le istruzioni long convertendole in short.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-194">Optimizes long instructions to short.</span></span> <span data-ttu-id="f5d6b-195">Ad esempio, `br` viene convertito in `br.s`.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-195">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="f5d6b-196">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-196">**/pe64**</span></span>|<span data-ttu-id="f5d6b-197">Crea un'immagine a 64 bit (PE32+).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-197">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="f5d6b-198">Se non è specificato il processore di destinazione, l'impostazione predefinita è `/itanium`.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-198">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="f5d6b-199">**/PDB**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-199">**/pdb**</span></span>|<span data-ttu-id="f5d6b-200">Crea un file PDB senza abilitare la traccia delle informazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-200">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="f5d6b-201">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-201">**/quiet**</span></span>|<span data-ttu-id="f5d6b-202">Specifica la modalità non interattiva. Non visualizza informazioni sullo stato dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-202">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="f5d6b-203">**/Resource:**`file.res`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-203">**/resource:** `file.res`</span></span>|<span data-ttu-id="f5d6b-204">Include il file di risorse specificato \*nel formato res nel file con *estensione exe* o *dll* risultante.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-204">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="f5d6b-205">È possibile specificare un unico file .res con l'opzione **/resource** .</span><span class="sxs-lookup"><span data-stu-id="f5d6b-205">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="f5d6b-206">**/ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-206">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="f5d6b-207">Imposta il numero di versione del sottosistema nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-207">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="f5d6b-208">Per **/appcontainer** e **/arm** il numero minimo di versione è 6.02.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-208">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="f5d6b-209">**/stack:**`stackSize`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-209">**/stack:** `stackSize`</span></span>|<span data-ttu-id="f5d6b-210">Imposta su `stackSize`il valore di SizeOfStackReserve nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-210">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="f5d6b-211">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-211">**/stripreloc**</span></span>|<span data-ttu-id="f5d6b-212">Specifica che non sono necessarie rilocazioni di base.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-212">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="f5d6b-213">**/SUBSYSTEM:**`integer`</span><span class="sxs-lookup"><span data-stu-id="f5d6b-213">**/subsystem:** `integer`</span></span>|<span data-ttu-id="f5d6b-214">Imposta il sottosistema sul valore specificato da `integer` nell'intestazione NT facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-214">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="f5d6b-215">Se la direttiva IL .subsystem è specificata nel file, questo comando ne esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-215">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="f5d6b-216">Per un elenco di valori validi per `integer`, vedere winnt.h, IMAGE_SUBSYSTEM.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-216">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="f5d6b-217">**/x64**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-217">**/x64**</span></span>|<span data-ttu-id="f5d6b-218">Specifica un processore AMD a 64 bit come processore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-218">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="f5d6b-219">Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-219">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="f5d6b-220">**/?**</span><span class="sxs-lookup"><span data-stu-id="f5d6b-220">**/?**</span></span>|<span data-ttu-id="f5d6b-221">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-221">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="f5d6b-222">Tutte le opzioni per *Ilasm. exe* non fanno distinzione tra maiuscole e minuscole e vengono riconosciute dalle prime tre lettere.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-222">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="f5d6b-223">Ad esempio, **/LIS** è equivalente a **/Listing** e **/res**: myresfile. res è equivalente a **/Resource**: myresfile. res. Le opzioni che specificano gli argomenti accettano due punti (:) o un segno di uguale (=) come separatore tra l'opzione e l'argomento.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-223">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="f5d6b-224">Ad esempio, **/output**:*file. ext* equivale a **/output**=*file. ext*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-224">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5d6b-225">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f5d6b-225">Remarks</span></span>

<span data-ttu-id="f5d6b-226">L'assembler IL consente ai fornitori di strumenti di progettare e implementare generatori IL.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-226">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="f5d6b-227">Con *Ilasm. exe*, gli sviluppatori di strumenti e compilatori possono concentrarsi su il e sulla generazione di metadati senza preoccuparsi di emettere il nel formato di file PE.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-227">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="f5d6b-228">Analogamente ad altri compilatori destinati al runtime, ad esempio C# e Visual Basic, *Ilasm. exe* non produce file oggetto intermedi e non richiede una fase di collegamento per creare un file PE.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-228">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="f5d6b-229">L'assembler IL è in grado di esprimere tutte le funzionalità esistenti per IL e i metadati dei linguaggi di programmazione destinati al runtime.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-229">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="f5d6b-230">In questo modo il codice gestito scritto in uno qualsiasi di questi linguaggi di programmazione può essere espresso in modo adeguato nell'assembler IL e compilato con *Ilasm. exe*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-230">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="f5d6b-231">È possibile che la compilazione abbia esito negativo se nell'ultima riga di codice del file di origine con estensione il non è presente uno spazio vuoto finale o un carattere di fine riga.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-231">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="f5d6b-232">È possibile utilizzare *Ilasm. exe* insieme allo strumento complementare Ildasm. [*exe*](ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-232">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="f5d6b-233">*Ildasm. exe* accetta un file PE che contiene IL codice il e crea un file di testo adatto come input per *Ilasm. exe*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-233">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="f5d6b-234">Questo è utile, ad esempio, quando si compila codice in un linguaggio di programmazione che non supporta tutti gli attributi dei metadati del runtime.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-234">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="f5d6b-235">Dopo aver compilato il codice ed eseguito l'output tramite *Ildasm. exe*, il file di testo il risultante può essere modificato manualmente per aggiungere gli attributi mancanti.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-235">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="f5d6b-236">È quindi possibile eseguire questo file di testo tramite *Ilasm. exe* per produrre un file eseguibile finale.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-236">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="f5d6b-237">È inoltre possibile ricorrere a questa tecnica per produrre un unico file PE sulla base di più file PE generati da diversi compilatori.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-237">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="f5d6b-238">Attualmente non è possibile avvalersi di questa tecnica con file PE contenenti codice nativo incorporato, ad esempio file PE prodotti da Visual C++.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-238">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="f5d6b-239">Per fare in modo che questo utilizzo combinato di *Ildasm. exe* e *Ilasm. exe* sia il più accurato possibile, per impostazione predefinita l'assembler non sostituisce le codifiche brevi per quelle lunghe che potrebbero essere state scritte nelle origini il (o che potrebbero essere emesse da un altro compilatore).</span><span class="sxs-lookup"><span data-stu-id="f5d6b-239">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="f5d6b-240">Utilizzare l'opzione **/optimize** per sostituire le codifiche short quando possibile.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-240">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="f5d6b-241">*Ildasm. exe* opera solo su file su disco.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-241">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="f5d6b-242">e non su file installati nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-242">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="f5d6b-243">Per altre informazioni sulla grammatica di IL, vedere il file asmparse.grammar in Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-243">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="version-information"></a><span data-ttu-id="f5d6b-244">Informazioni sulla versione</span><span class="sxs-lookup"><span data-stu-id="f5d6b-244">Version Information</span></span>

<span data-ttu-id="f5d6b-245">A partire da .NET Framework 4.5, è possibile associare un attributo personalizzato a un'implementazione di interfaccia usando codice analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="f5d6b-245">Starting with the .NET Framework 4.5, you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

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

<span data-ttu-id="f5d6b-246">A partire da .NET Framework 4.5, è possibile specificare un BLOB (oggetto binario di grandi dimensioni) marshalling arbitrario usando la relativa rappresentazione binaria non elaborata, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f5d6b-246">Starting with the .NET Framework 4.5, you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="f5d6b-247">Per altre informazioni sulla grammatica di IL, vedere il file asmparse.grammar in Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-247">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="f5d6b-248">Esempi</span><span class="sxs-lookup"><span data-stu-id="f5d6b-248">Examples</span></span>

<span data-ttu-id="f5d6b-249">Il comando che segue assembla il file IL *myTestFile.il* e produce l'eseguibile *myTestFile.exe*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-249">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="f5d6b-250">Il comando che segue assembla il file IL *myTestFile.il* e produce il file *.dll\*\*myTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-250">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="f5d6b-251">Il comando che segue assembla il file IL *myTestFile.il* e produce il file *.dll\*\*myNewTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-251">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="f5d6b-252">L'esempio di codice seguente illustra un'applicazione molto semplice che visualizza "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="f5d6b-252">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="f5d6b-253">nella console.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-253">to the console.</span></span> <span data-ttu-id="f5d6b-254">È possibile compilare questo codice e quindi utilizzare lo strumento [*Ildasm. exe*](ildasm-exe-il-disassembler.md) per generare un file il.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-254">You can compile this code and then use the [*Ildasm.exe*](ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

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

<span data-ttu-id="f5d6b-255">L'esempio di codice IL riportato di seguito corrisponde al precedente esempio di codice C#.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-255">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="f5d6b-256">È possibile compilare questo codice in un assembly mediante lo strumento IL Assembler.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-256">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="f5d6b-257">Gli esempi di codice IL e C# visualizzano entrambi "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="f5d6b-257">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="f5d6b-258">nella console.</span><span class="sxs-lookup"><span data-stu-id="f5d6b-258">to the console.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f5d6b-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5d6b-259">See also</span></span>

- [<span data-ttu-id="f5d6b-260">Strumenti</span><span class="sxs-lookup"><span data-stu-id="f5d6b-260">Tools</span></span>](index.md)
- [<span data-ttu-id="f5d6b-261">*Ildasm. exe* (disassembler il)</span><span class="sxs-lookup"><span data-stu-id="f5d6b-261">*Ildasm.exe* (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="f5d6b-262">Processo di esecuzione gestita</span><span class="sxs-lookup"><span data-stu-id="f5d6b-262">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="f5d6b-263">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="f5d6b-263">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
