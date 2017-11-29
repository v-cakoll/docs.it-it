---
title: Lc.exe (Compilatore licenze)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0175b14f556a68f9c289d84d79ce10a6982ffb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="03ee7-102">Lc.exe (Compilatore licenze)</span><span class="sxs-lookup"><span data-stu-id="03ee7-102">Lc.exe (License Compiler)</span></span>
<span data-ttu-id="03ee7-103">Il Compilatore licenze legge file di testo contenenti informazioni sulla licenza e produce un file binario che è possibile incorporare come risorsa in un eseguibile di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="03ee7-103">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="03ee7-104">Un file LICX viene generato o aggiornato automaticamente mediante Progettazione Windows Form ogni volta che un controllo concesso in licenza viene aggiunto al form.</span><span class="sxs-lookup"><span data-stu-id="03ee7-104">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="03ee7-105">Durante la compilazione, il file di testo LICX viene convertito in una risorsa binaria con estensione licenses che fornisce il supporto per la gestione delle licenze dei controlli .NET.</span><span class="sxs-lookup"><span data-stu-id="03ee7-105">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="03ee7-106">La risorsa binaria verrà quindi incorporata nell'output del progetto.</span><span class="sxs-lookup"><span data-stu-id="03ee7-106">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="03ee7-107">La compilazione incrociata fra 32 bit e 64 bit non è supportata quando si usa il Compilatore licenze nel corso della compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="03ee7-107">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="03ee7-108">Questo avviene perché il Compilatore licenze deve caricare assembly e non è consentito caricare assembly a 64 bit da un'applicazione a 32 bit e viceversa.</span><span class="sxs-lookup"><span data-stu-id="03ee7-108">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="03ee7-109">In questo caso, usare il Compilatore licenze dalla riga di comando per compilare manualmente la licenza e specificare l'architettura corrispondente.</span><span class="sxs-lookup"><span data-stu-id="03ee7-109">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="03ee7-110">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="03ee7-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="03ee7-111">Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="03ee7-111">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="03ee7-112">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="03ee7-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="03ee7-113">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="03ee7-113">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ee7-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03ee7-114">Syntax</span></span>  
  
```  
      lc /target:  
      targetPE /complist:filename [/outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="03ee7-115">Opzione</span><span class="sxs-lookup"><span data-stu-id="03ee7-115">Option</span></span>|<span data-ttu-id="03ee7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03ee7-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="03ee7-117">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="03ee7-117">**/complist:** *filename*</span></span>|<span data-ttu-id="03ee7-118">Specifica il nome di un file contenente l'elenco dei componenti provvisti di licenza da includere nel file LICENSES.</span><span class="sxs-lookup"><span data-stu-id="03ee7-118">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="03ee7-119">A ciascun componente viene fatto riferimento mediante il nome completo, specificando un solo componente per riga.</span><span class="sxs-lookup"><span data-stu-id="03ee7-119">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="03ee7-120">Se si usa la riga di comando sarà possibile specificare un file separato per ciascun form del progetto.</span><span class="sxs-lookup"><span data-stu-id="03ee7-120">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="03ee7-121">Lc.exe accetta più file di input e produce un unico file LICENSES.</span><span class="sxs-lookup"><span data-stu-id="03ee7-121">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="03ee7-122">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="03ee7-122">**/h**[**elp**]</span></span>|<span data-ttu-id="03ee7-123">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="03ee7-123">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="03ee7-124">**/i:** *modulo*</span><span class="sxs-lookup"><span data-stu-id="03ee7-124">**/i:** *module*</span></span>|<span data-ttu-id="03ee7-125">Specifica i moduli contenenti i componenti elencati nel file **/complist**.</span><span class="sxs-lookup"><span data-stu-id="03ee7-125">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="03ee7-126">Per specificare più moduli, usare più flag **/i**.</span><span class="sxs-lookup"><span data-stu-id="03ee7-126">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="03ee7-127">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="03ee7-127">**/nologo**</span></span>|<span data-ttu-id="03ee7-128">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03ee7-128">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="03ee7-129">**/outDir:** *percorso*</span><span class="sxs-lookup"><span data-stu-id="03ee7-129">**/outdir:** *path*</span></span>|<span data-ttu-id="03ee7-130">Specifica la directory in cui inserire il file LICENSES di output.</span><span class="sxs-lookup"><span data-stu-id="03ee7-130">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="03ee7-131">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="03ee7-131">**/target:** *targetPE*</span></span>|<span data-ttu-id="03ee7-132">Specifica l'eseguibile per cui viene generato il file LICENSES.</span><span class="sxs-lookup"><span data-stu-id="03ee7-132">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="03ee7-133">**/v**</span><span class="sxs-lookup"><span data-stu-id="03ee7-133">**/v**</span></span>|<span data-ttu-id="03ee7-134">Specifica la modalità dettagliata. Visualizza le informazioni sullo stato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="03ee7-134">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="03ee7-135">**@** *file*</span><span class="sxs-lookup"><span data-stu-id="03ee7-135">**@** *file*</span></span>|<span data-ttu-id="03ee7-136">Specifica il file di risposta (.rsp).</span><span class="sxs-lookup"><span data-stu-id="03ee7-136">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="03ee7-137">**/?**</span><span class="sxs-lookup"><span data-stu-id="03ee7-137">**/?**</span></span>|<span data-ttu-id="03ee7-138">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="03ee7-138">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03ee7-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="03ee7-139">Example</span></span>  
  
1.  <span data-ttu-id="03ee7-140">Se si usa un controllo con licenza `MyCompany.Samples.LicControl1` contenuto in `Samples.DLL` all'interno di un'applicazione denominata `HostApp.exe`*,* è possibile creare il file `HostAppLic.txt` includendo gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="03ee7-140">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```  
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2.  <span data-ttu-id="03ee7-141">Creare il file LICENSES denominato `HostApp.exe.licenses` usando il comando che segue.</span><span class="sxs-lookup"><span data-stu-id="03ee7-141">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3.  <span data-ttu-id="03ee7-142">Compilare `HostApp.exe` includendo il file LICENSES come risorsa.</span><span class="sxs-lookup"><span data-stu-id="03ee7-142">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="03ee7-143">Se l'applicazione fosse in C#, si utilizzerebbe il seguente comando per compilarla:</span><span class="sxs-lookup"><span data-stu-id="03ee7-143">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```  
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="03ee7-144">Il comando che segue compila `myApp.licenses` sulla base degli elenchi di componenti provvisti di licenza specificati da `hostapplic.txt`, `hostapplic2.txt` e `hostapplic3.txt`.</span><span class="sxs-lookup"><span data-stu-id="03ee7-144">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="03ee7-145">L'argomento `modulesList` specifica i moduli contenenti i componenti provvisti di licenza.</span><span class="sxs-lookup"><span data-stu-id="03ee7-145">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="03ee7-146">Esempio di file di risposta</span><span class="sxs-lookup"><span data-stu-id="03ee7-146">Response File Example</span></span>  
 <span data-ttu-id="03ee7-147">Nell'elenco seguente è riportato un esempio di file di risposta, `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="03ee7-147">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="03ee7-148">Per altre informazioni sui file di risposta, vedere [File di risposta](/visualstudio/msbuild/msbuild-response-files).</span><span class="sxs-lookup"><span data-stu-id="03ee7-148">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```  
/target:hostapp.exe  
/complist:hostapplic.txt   
/i:WFCPrj.dll   
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="03ee7-149">La riga di comando seguente usa il file `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="03ee7-149">The following command line uses the `response.rsp` file.</span></span>  
  
```  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="03ee7-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03ee7-150">See Also</span></span>  
 [<span data-ttu-id="03ee7-151">Strumenti</span><span class="sxs-lookup"><span data-stu-id="03ee7-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="03ee7-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="03ee7-152">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="03ee7-153">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="03ee7-153">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
