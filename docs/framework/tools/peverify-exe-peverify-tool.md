---
title: Peverify.exe (strumento PEVerify)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0423946ab32c04274bb3d5656ed8603ec4314d88
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128739"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="9bfd5-102">Peverify.exe (strumento PEVerify)</span><span class="sxs-lookup"><span data-stu-id="9bfd5-102">Peverify.exe (PEVerify Tool)</span></span>
<span data-ttu-id="9bfd5-103">Lo strumento PEVerify aiuta gli sviluppatori che utilizzano il linguaggio MSIL (Microsoft Intermediate Language) per creare compilatori, motori di script e così via, a determinare se il codice MSIL creato e i metadati associati soddisfano i requisiti di indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-103">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers, script engine developers, and so on) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="9bfd5-104">Alcuni compilatori generano codice di cui è verificabile l'indipendenza dai tipi solo se si evita di utilizzare determinati costrutti del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-104">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="9bfd5-105">Se, in qualità di sviluppatore, si utilizza un compilatore di questo tipo, sarà opportuno verificare di non aver compromesso l'indipendenza dai tipi del codice.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-105">If, as a developer, you are using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="9bfd5-106">In questa situazione è possibile eseguire lo strumento PEVerify sui file per controllare il codice MSIL e i metadati.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-106">In this situation, you can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="9bfd5-107">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="9bfd5-108">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="9bfd5-109">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="9bfd5-110">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9bfd5-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bfd5-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bfd5-111">Syntax</span></span>  
  
```  
peverify filename [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bfd5-112">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bfd5-112">Parameters</span></span>  
  
|<span data-ttu-id="9bfd5-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="9bfd5-113">Argument</span></span>|<span data-ttu-id="9bfd5-114">Description</span><span class="sxs-lookup"><span data-stu-id="9bfd5-114">Description</span></span>|  
|--------------|-----------------|  
|*<span data-ttu-id="9bfd5-115">filename</span><span class="sxs-lookup"><span data-stu-id="9bfd5-115">filename</span></span>*|<span data-ttu-id="9bfd5-116">File eseguibile di tipo PE per il quale controllare il codice MSIL e i metadati.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="9bfd5-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="9bfd5-117">Option</span></span>|<span data-ttu-id="9bfd5-118">Description</span><span class="sxs-lookup"><span data-stu-id="9bfd5-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9bfd5-119">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="9bfd5-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="9bfd5-120">Interrompe la verifica dopo un numero di errori pari a *maxErrorCount*.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="9bfd5-121">Questo parametro non è supportato in .NET Framework 2.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|**<span data-ttu-id="9bfd5-122">/clock</span><span class="sxs-lookup"><span data-stu-id="9bfd5-122">/clock</span></span>**|<span data-ttu-id="9bfd5-123">Misura e segnala i seguenti tempi di verifica in millisecondi:</span><span class="sxs-lookup"><span data-stu-id="9bfd5-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> **<span data-ttu-id="9bfd5-124">MD Val.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-124">MD Val.</span></span> <span data-ttu-id="9bfd5-125">cycle</span><span class="sxs-lookup"><span data-stu-id="9bfd5-125">cycle</span></span>**<br /> <span data-ttu-id="9bfd5-126">Ciclo di convalida dei metadati</span><span class="sxs-lookup"><span data-stu-id="9bfd5-126">Metadata validation cycle</span></span><br /><br /> **<span data-ttu-id="9bfd5-127">MD Val.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-127">MD Val.</span></span> <span data-ttu-id="9bfd5-128">pure</span><span class="sxs-lookup"><span data-stu-id="9bfd5-128">pure</span></span>**<br /> <span data-ttu-id="9bfd5-129">Pure di convalida dei metadati</span><span class="sxs-lookup"><span data-stu-id="9bfd5-129">Metadata validation pure</span></span><br /><br /> **<span data-ttu-id="9bfd5-130">IL Ver.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-130">IL Ver.</span></span> <span data-ttu-id="9bfd5-131">cycle</span><span class="sxs-lookup"><span data-stu-id="9bfd5-131">cycle</span></span>**<br /> <span data-ttu-id="9bfd5-132">Ciclo di verifica di MSIL (Microsoft Intermediate Language)</span><span class="sxs-lookup"><span data-stu-id="9bfd5-132">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> **<span data-ttu-id="9bfd5-133">IL Ver pure</span><span class="sxs-lookup"><span data-stu-id="9bfd5-133">IL Ver pure</span></span>**<br /> <span data-ttu-id="9bfd5-134">Pure di verifica MSIL</span><span class="sxs-lookup"><span data-stu-id="9bfd5-134">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="9bfd5-135">I tempi **MD Val. cycle** e **IL Ver. cycle** includono il tempo richiesto per l'esecuzione delle procedure di avvio e chiusura necessarie.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-135">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="9bfd5-136">I tempi **MD Val. pure** e **IL Ver pure** corrispondono al tempo richiesto solo per l'esecuzione della convalida o della verifica.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-136">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|**<span data-ttu-id="9bfd5-137">/help</span><span class="sxs-lookup"><span data-stu-id="9bfd5-137">/help</span></span>**|<span data-ttu-id="9bfd5-138">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-138">Displays command syntax and options for the tool.</span></span>|  
|**<span data-ttu-id="9bfd5-139">/hresult</span><span class="sxs-lookup"><span data-stu-id="9bfd5-139">/hresult</span></span>**|<span data-ttu-id="9bfd5-140">Visualizza i codici di errore in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-140">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="9bfd5-141">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="9bfd5-141">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="9bfd5-142">Ignora i codici di errore specificati.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-142">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="9bfd5-143">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="9bfd5-143">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="9bfd5-144">Ignora i codici di errore elencati nel file di risposta specificato.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-144">Ignores the error codes listed in the specified response file.</span></span>|  
|**<span data-ttu-id="9bfd5-145">/il</span><span class="sxs-lookup"><span data-stu-id="9bfd5-145">/il</span></span>**|<span data-ttu-id="9bfd5-146">Esegue i controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly specificato da *filename*.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-146">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="9bfd5-147">Vengono restituite descrizioni dettagliate per ogni problema rilevato, a meno che non si specifichi l'opzione **/quiet**.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-147">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|**<span data-ttu-id="9bfd5-148">/md</span><span class="sxs-lookup"><span data-stu-id="9bfd5-148">/md</span></span>**|<span data-ttu-id="9bfd5-149">Esegue controlli di convalida dei metadati sull'assembly specificato da *filename*.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-149">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="9bfd5-150">Esamina l'intera struttura dei metadati nel file e segnala tutti i problemi di convalida rilevati.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-150">This walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|**<span data-ttu-id="9bfd5-151">/nologo</span><span class="sxs-lookup"><span data-stu-id="9bfd5-151">/nologo</span></span>**|<span data-ttu-id="9bfd5-152">Evita la visualizzazione delle informazioni sul copyright e sulla versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-152">Suppresses the display of product version and copyright information.</span></span>|  
|**<span data-ttu-id="9bfd5-153">/nosymbols</span><span class="sxs-lookup"><span data-stu-id="9bfd5-153">/nosymbols</span></span>**|<span data-ttu-id="9bfd5-154">In .NET Framework versione 2.0 evita la visualizzazione dei numeri di riga per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-154">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|**<span data-ttu-id="9bfd5-155">/quiet</span><span class="sxs-lookup"><span data-stu-id="9bfd5-155">/quiet</span></span>**|<span data-ttu-id="9bfd5-156">Specifica la modalità non interattiva. Evita la visualizzazione dell'output dei report dei problemi di verifica.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-156">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="9bfd5-157">Viene comunque indicato se il file è indipendente dai tipi, ma non vengono fornite informazioni sui problemi che impediscono la verifica dell'indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-157">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="9bfd5-158">Verifica solo i metodi trasparenti.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-158">Verify only the transparent methods.</span></span>|  
|**<span data-ttu-id="9bfd5-159">/unique</span><span class="sxs-lookup"><span data-stu-id="9bfd5-159">/unique</span></span>**|<span data-ttu-id="9bfd5-160">Ignora i codici di errore ripetuti.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-160">Ignores repeating error codes.</span></span>|  
|**<span data-ttu-id="9bfd5-161">/verbose</span><span class="sxs-lookup"><span data-stu-id="9bfd5-161">/verbose</span></span>**|<span data-ttu-id="9bfd5-162">In .NET Framework versione 2.0 determina la visualizzazione di informazioni aggiuntive nei messaggi di verifica MSIL.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-162">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|**<span data-ttu-id="9bfd5-163">/?</span><span class="sxs-lookup"><span data-stu-id="9bfd5-163">/?</span></span>**|<span data-ttu-id="9bfd5-164">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-164">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bfd5-165">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9bfd5-165">Remarks</span></span>  
 <span data-ttu-id="9bfd5-166">Common Language Runtime si basa sull'esecuzione indipendente dai tipi del codice dell'applicazione per applicare meccanismi di sicurezza e isolamento.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-166">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="9bfd5-167">In genere il codice di cui non è [verificabile l'indipendenza dai tipi](../../../docs/standard/security/key-security-concepts.md#type-safety-and-security) non può essere eseguito, anche se è possibile impostare criteri di sicurezza per consentire l'esecuzione del codice attendibile ma non verificabile.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-167">Normally, code that is not [verifiably type safe](../../../docs/standard/security/key-security-concepts.md#type-safety-and-security) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="9bfd5-168">Se non sono state specificate né l'opzione **/md** né l'opzione **/il** verranno eseguiti entrambi i tipi di controllo,</span><span class="sxs-lookup"><span data-stu-id="9bfd5-168">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="9bfd5-169">iniziando dai controlli **/md**.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-169">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="9bfd5-170">Se non sono presenti errori vengono effettuati i controlli **/il**.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-170">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="9bfd5-171">Se si specifica sia **/md** sia **/il** i controlli **/il** vengono effettuati anche in presenza di errori nei metadati.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-171">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="9bfd5-172">Pertanto in assenza di errori nei metadati, **peverify** *filename* è equivalente a **peverify** *filename* **/md** **/il**.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-172">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="9bfd5-173">Mediante Peverify.exe vengono eseguiti controlli di verifica completi del codice MSIL sulla base dell'analisi del flusso di dati nonché di un elenco di alcune centinaia di regole sui metadati validi.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-173">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="9bfd5-174">Per informazioni dettagliate sui controlli eseguiti da Peverify.exe, vedere le specifiche di convalida dei metadati e le specifiche del set di istruzioni MSIL nella cartella "Tools Developers Guide" di [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bfd5-174">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="9bfd5-175">Si noti che in .NET Framework 2.0 o versione successiva sono supportate restituzioni `byref` verificabili specificate mediante le seguenti istruzioni MSIL: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` e `unbox`.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-175">Note that the .NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9bfd5-176">Esempi</span><span class="sxs-lookup"><span data-stu-id="9bfd5-176">Examples</span></span>  
 <span data-ttu-id="9bfd5-177">Il comando che segue esegue controlli di convalida dei metadati e controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-177">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="9bfd5-178">Al completamento della richiesta precedente, viene visualizzato il messaggio che segue.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="9bfd5-179">Il comando che segue esegue controlli di convalida dei metadati e controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="9bfd5-180">Viene visualizzato il tempo necessario per l'esecuzione di questi controlli.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-180">The tool displays the time required to perform these checks.</span></span>  
  
```  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="9bfd5-181">Al completamento della richiesta precedente, viene visualizzato il messaggio che segue.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-181">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="9bfd5-182">Il comando che segue esegue controlli di convalida dei metadati e controlli di verifica dell'indipendenza dai tipi del codice MSIL per i metodi implementati nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-182">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="9bfd5-183">Tuttavia, Peverify.exe si arresta quando raggiunge il conteggio di errori massimo di 100.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-183">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="9bfd5-184">Lo strumento ignora inoltre i codici di errore specificati.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-184">The tool also ignores the specified error codes.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="9bfd5-185">Il comando che segue produce lo stesso risultato dell'esempio precedente, ma specifica i codici di errore da ignorare nel file di risposta `ignoreErrors.rsp`.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-185">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="9bfd5-186">Il file di risposta può contenere un elenco di codici di errore separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-186">The response file can contain a comma-separated list of error codes.</span></span>  
  
```  
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="9bfd5-187">In alternativa, il file di risposta può essere formattato con un codice di errore per riga.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-187">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```  
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bfd5-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bfd5-188">See also</span></span>

- [<span data-ttu-id="9bfd5-189">Strumenti</span><span class="sxs-lookup"><span data-stu-id="9bfd5-189">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="9bfd5-190">Scrittura di codice indipendente dai tipi verificabile</span><span class="sxs-lookup"><span data-stu-id="9bfd5-190">Writing Verifiably Type-Safe Code</span></span>](../../../docs/framework/misc/code-access-security-basics.md#typesafe_code)
- [<span data-ttu-id="9bfd5-191">Indipendenza dai tipi e sicurezza</span><span class="sxs-lookup"><span data-stu-id="9bfd5-191">Type Safety and Security</span></span>](../../../docs/standard/security/key-security-concepts.md#type-safety-and-security)
- [<span data-ttu-id="9bfd5-192">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="9bfd5-192">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
