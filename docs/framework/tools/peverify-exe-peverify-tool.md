---
title: Peverify.exe (strumento PEVerify)
description: Utilizzare Peverify.exe (verifica eseguibile portatile) per determinare se il codice MSIL (Microsoft Intermediate Language) & i metadati soddisfano gli standard di indipendenza dai tipi in .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
ms.openlocfilehash: 478c04a45c7f9d3ad568a6bc4a12a89fe786583a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325619"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="b0390-103">Peverify.exe (strumento PEVerify)</span><span class="sxs-lookup"><span data-stu-id="b0390-103">Peverify.exe (PEVerify tool)</span></span>

<span data-ttu-id="b0390-104">Lo strumento PEVerify consente agli sviluppatori che generano codice MSIL (Microsoft Intermediate Language), ad esempio Writer del compilatore e sviluppatori del motore di script, di determinare se il codice MSIL e i metadati associati soddisfano i requisiti di indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="b0390-104">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers and script engine developers) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="b0390-105">Alcuni compilatori generano codice di cui è verificabile l'indipendenza dai tipi solo se si evita di utilizzare determinati costrutti del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b0390-105">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="b0390-106">Se si usa un compilatore di questo tipo, è consigliabile verificare di non aver compromesso l'indipendenza dai tipi del codice.</span><span class="sxs-lookup"><span data-stu-id="b0390-106">If you're using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="b0390-107">È possibile eseguire lo strumento PEVerify sui file per controllare il codice MSIL e i metadati.</span><span class="sxs-lookup"><span data-stu-id="b0390-107">You can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="b0390-108">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0390-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b0390-109">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="b0390-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="b0390-110">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b0390-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b0390-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0390-111">Syntax</span></span>  
  
```console  
peverify filename [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0390-112">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0390-112">Parameters</span></span>  
  
|<span data-ttu-id="b0390-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="b0390-113">Argument</span></span>|<span data-ttu-id="b0390-114">Description</span><span class="sxs-lookup"><span data-stu-id="b0390-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b0390-115">*filename*</span><span class="sxs-lookup"><span data-stu-id="b0390-115">*filename*</span></span>|<span data-ttu-id="b0390-116">File eseguibile di tipo PE per il quale controllare il codice MSIL e i metadati.</span><span class="sxs-lookup"><span data-stu-id="b0390-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="b0390-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="b0390-117">Option</span></span>|<span data-ttu-id="b0390-118">Description</span><span class="sxs-lookup"><span data-stu-id="b0390-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b0390-119">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="b0390-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="b0390-120">Interrompe la verifica dopo un numero di errori pari a *maxErrorCount*.</span><span class="sxs-lookup"><span data-stu-id="b0390-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="b0390-121">Questo parametro non è supportato in .NET Framework 2.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b0390-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="b0390-122">**/clock**</span><span class="sxs-lookup"><span data-stu-id="b0390-122">**/clock**</span></span>|<span data-ttu-id="b0390-123">Misura e segnala i seguenti tempi di verifica in millisecondi:</span><span class="sxs-lookup"><span data-stu-id="b0390-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="b0390-124">**MD Val. cycle**</span><span class="sxs-lookup"><span data-stu-id="b0390-124">**MD Val. cycle**</span></span><br /> <span data-ttu-id="b0390-125">Ciclo di convalida dei metadati</span><span class="sxs-lookup"><span data-stu-id="b0390-125">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="b0390-126">**MD Val. pure**</span><span class="sxs-lookup"><span data-stu-id="b0390-126">**MD Val. pure**</span></span><br /> <span data-ttu-id="b0390-127">Pure di convalida dei metadati</span><span class="sxs-lookup"><span data-stu-id="b0390-127">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="b0390-128">**IL Ver. cycle**</span><span class="sxs-lookup"><span data-stu-id="b0390-128">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="b0390-129">Ciclo di verifica di MSIL (Microsoft Intermediate Language)</span><span class="sxs-lookup"><span data-stu-id="b0390-129">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="b0390-130">**IL Ver pure**</span><span class="sxs-lookup"><span data-stu-id="b0390-130">**IL Ver pure**</span></span><br /> <span data-ttu-id="b0390-131">Pure di verifica MSIL</span><span class="sxs-lookup"><span data-stu-id="b0390-131">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="b0390-132">I tempi **MD Val. cycle** e **IL Ver. cycle** includono il tempo richiesto per l'esecuzione delle procedure di avvio e chiusura necessarie.</span><span class="sxs-lookup"><span data-stu-id="b0390-132">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="b0390-133">I tempi **MD Val. pure** e **IL Ver pure** corrispondono al tempo richiesto solo per l'esecuzione della convalida o della verifica.</span><span class="sxs-lookup"><span data-stu-id="b0390-133">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="b0390-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="b0390-134">**/help**</span></span>|<span data-ttu-id="b0390-135">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="b0390-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="b0390-136">**/hresult**</span><span class="sxs-lookup"><span data-stu-id="b0390-136">**/hresult**</span></span>|<span data-ttu-id="b0390-137">Visualizza i codici di errore in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="b0390-137">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="b0390-138">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="b0390-138">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="b0390-139">Ignora i codici di errore specificati.</span><span class="sxs-lookup"><span data-stu-id="b0390-139">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="b0390-140">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="b0390-140">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="b0390-141">Ignora i codici di errore elencati nel file di risposta specificato.</span><span class="sxs-lookup"><span data-stu-id="b0390-141">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="b0390-142">**/il**</span><span class="sxs-lookup"><span data-stu-id="b0390-142">**/il**</span></span>|<span data-ttu-id="b0390-143">Esegue i controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly specificato da *filename*.</span><span class="sxs-lookup"><span data-stu-id="b0390-143">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="b0390-144">Vengono restituite descrizioni dettagliate per ogni problema rilevato, a meno che non si specifichi l'opzione **/quiet**.</span><span class="sxs-lookup"><span data-stu-id="b0390-144">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="b0390-145">**/MD**</span><span class="sxs-lookup"><span data-stu-id="b0390-145">**/md**</span></span>|<span data-ttu-id="b0390-146">Esegue controlli di convalida dei metadati sull'assembly specificato da *filename*.</span><span class="sxs-lookup"><span data-stu-id="b0390-146">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="b0390-147">Questa opzione esamina la struttura completa dei metadati nel file e segnala tutti i problemi di convalida rilevati.</span><span class="sxs-lookup"><span data-stu-id="b0390-147">This option walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="b0390-148">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="b0390-148">**/nologo**</span></span>|<span data-ttu-id="b0390-149">Evita la visualizzazione delle informazioni sul copyright e sulla versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="b0390-149">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="b0390-150">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="b0390-150">**/nosymbols**</span></span>|<span data-ttu-id="b0390-151">In .NET Framework versione 2.0 evita la visualizzazione dei numeri di riga per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b0390-151">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="b0390-152">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="b0390-152">**/quiet**</span></span>|<span data-ttu-id="b0390-153">Specifica la modalità non interattiva. Evita la visualizzazione dell'output dei report dei problemi di verifica.</span><span class="sxs-lookup"><span data-stu-id="b0390-153">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="b0390-154">Viene comunque indicato se il file è indipendente dai tipi, ma non vengono fornite informazioni sui problemi che impediscono la verifica dell'indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="b0390-154">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="b0390-155">Verifica solo i metodi trasparenti.</span><span class="sxs-lookup"><span data-stu-id="b0390-155">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="b0390-156">**—/Unique**</span><span class="sxs-lookup"><span data-stu-id="b0390-156">**/unique**</span></span>|<span data-ttu-id="b0390-157">Ignora i codici di errore ripetuti.</span><span class="sxs-lookup"><span data-stu-id="b0390-157">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="b0390-158">**/Verbose**</span><span class="sxs-lookup"><span data-stu-id="b0390-158">**/verbose**</span></span>|<span data-ttu-id="b0390-159">In .NET Framework versione 2.0 determina la visualizzazione di informazioni aggiuntive nei messaggi di verifica MSIL.</span><span class="sxs-lookup"><span data-stu-id="b0390-159">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="b0390-160">**/?**</span><span class="sxs-lookup"><span data-stu-id="b0390-160">**/?**</span></span>|<span data-ttu-id="b0390-161">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="b0390-161">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0390-162">Commenti</span><span class="sxs-lookup"><span data-stu-id="b0390-162">Remarks</span></span>  
 <span data-ttu-id="b0390-163">Common Language Runtime si basa sull'esecuzione indipendente dai tipi del codice dell'applicazione per applicare meccanismi di sicurezza e isolamento.</span><span class="sxs-lookup"><span data-stu-id="b0390-163">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="b0390-164">In genere il codice di cui non è [verificabile l'indipendenza dai tipi](../../standard/security/key-security-concepts.md#type-safety-and-security) non può essere eseguito, anche se è possibile impostare criteri di sicurezza per consentire l'esecuzione del codice attendibile ma non verificabile.</span><span class="sxs-lookup"><span data-stu-id="b0390-164">Normally, code that is not [verifiably type safe](../../standard/security/key-security-concepts.md#type-safety-and-security) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="b0390-165">Se non sono state specificate né l'opzione **/md** né l'opzione **/il** verranno eseguiti entrambi i tipi di controllo,</span><span class="sxs-lookup"><span data-stu-id="b0390-165">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="b0390-166">iniziando dai controlli **/md**.</span><span class="sxs-lookup"><span data-stu-id="b0390-166">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="b0390-167">Se non sono presenti errori vengono effettuati i controlli **/il**.</span><span class="sxs-lookup"><span data-stu-id="b0390-167">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="b0390-168">Se si specifica sia **/md** sia **/il** i controlli **/il** vengono effettuati anche in presenza di errori nei metadati.</span><span class="sxs-lookup"><span data-stu-id="b0390-168">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="b0390-169">Pertanto in assenza di errori nei metadati, **peverify** *filename* è equivalente a **peverify** *filename* **/md** **/il**.</span><span class="sxs-lookup"><span data-stu-id="b0390-169">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="b0390-170">Mediante Peverify.exe vengono eseguiti controlli di verifica completi del codice MSIL sulla base dell'analisi del flusso di dati nonché di un elenco di alcune centinaia di regole sui metadati validi.</span><span class="sxs-lookup"><span data-stu-id="b0390-170">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="b0390-171">Per informazioni dettagliate sui controlli eseguiti da Peverify.exe, vedere le specifiche di convalida dei metadati e le specifiche del set di istruzioni MSIL nella cartella "Tools Developers Guide" di Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="b0390-171">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the Windows SDK.</span></span>  
  
<span data-ttu-id="b0390-172">.NET Framework versione 2,0 o successiva supporta `byref` le restituzione verificabili specificate mediante le seguenti istruzioni MSIL: `dup` , `ldsflda` , `ldflda` , `ldelema` , `call` e `unbox` .</span><span class="sxs-lookup"><span data-stu-id="b0390-172">.NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call`, and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b0390-173">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0390-173">Examples</span></span>  
 <span data-ttu-id="b0390-174">Il comando che segue esegue controlli di convalida dei metadati e controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="b0390-174">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```console  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="b0390-175">Al completamento della richiesta precedente, viene visualizzato il messaggio che segue.</span><span class="sxs-lookup"><span data-stu-id="b0390-175">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="b0390-176">Il comando che segue esegue controlli di convalida dei metadati e controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="b0390-176">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="b0390-177">Viene visualizzato il tempo necessario per l'esecuzione di questi controlli.</span><span class="sxs-lookup"><span data-stu-id="b0390-177">The tool displays the time required to perform these checks.</span></span>  
  
```console  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="b0390-178">Al completamento della richiesta precedente, viene visualizzato il messaggio che segue.</span><span class="sxs-lookup"><span data-stu-id="b0390-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="b0390-179">Il comando che segue esegue controlli di convalida dei metadati e controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="b0390-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="b0390-180">Tuttavia, Peverify.exe si arresta quando raggiunge il conteggio di errori massimo di 100.</span><span class="sxs-lookup"><span data-stu-id="b0390-180">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="b0390-181">Lo strumento ignora inoltre i codici di errore specificati.</span><span class="sxs-lookup"><span data-stu-id="b0390-181">The tool also ignores the specified error codes.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="b0390-182">Il comando che segue produce lo stesso risultato dell'esempio precedente, ma specifica i codici di errore da ignorare nel file di risposta `ignoreErrors.rsp`.</span><span class="sxs-lookup"><span data-stu-id="b0390-182">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="b0390-183">Il file di risposta può contenere un elenco di codici di errore separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="b0390-183">The response file can contain a comma-separated list of error codes.</span></span>  
  
```text
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="b0390-184">In alternativa, il file di risposta può essere formattato con un codice di errore per riga.</span><span class="sxs-lookup"><span data-stu-id="b0390-184">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```text
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0390-185">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b0390-185">See also</span></span>

- [<span data-ttu-id="b0390-186">Strumenti</span><span class="sxs-lookup"><span data-stu-id="b0390-186">Tools</span></span>](index.md)
- [<span data-ttu-id="b0390-187">Scrittura di codice indipendente dai tipi verificabile</span><span class="sxs-lookup"><span data-stu-id="b0390-187">Writing Verifiably Type-Safe Code</span></span>](../misc/code-access-security-basics.md#typesafe_code)
- [<span data-ttu-id="b0390-188">Indipendenza dai tipi e sicurezza</span><span class="sxs-lookup"><span data-stu-id="b0390-188">Type Safety and Security</span></span>](../../standard/security/key-security-concepts.md#type-safety-and-security)
- [<span data-ttu-id="b0390-189">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b0390-189">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
