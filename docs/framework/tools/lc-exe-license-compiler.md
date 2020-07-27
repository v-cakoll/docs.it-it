---
title: Lc.exe (Compilatore licenze)
description: Utilizzare Lc.exe, il compilatore delle licenze. Questo strumento legge i file di testo che contengono informazioni sulla licenza e crea un file binario da incorporare in un eseguibile CLR come risorsa.
ms.date: 03/30/2017
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
ms.openlocfilehash: 45a80ba7c3e24c0f419758315b2d2daafd3890f4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164248"
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="9e883-104">Lc.exe (Compilatore licenze)</span><span class="sxs-lookup"><span data-stu-id="9e883-104">Lc.exe (License Compiler)</span></span>
<span data-ttu-id="9e883-105">Il Compilatore licenze legge file di testo contenenti informazioni sulla licenza e produce un file binario che è possibile incorporare come risorsa in un eseguibile di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9e883-105">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="9e883-106">Un file LICX viene generato o aggiornato automaticamente mediante Progettazione Windows Form ogni volta che un controllo concesso in licenza viene aggiunto al form.</span><span class="sxs-lookup"><span data-stu-id="9e883-106">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="9e883-107">Durante la compilazione, il file di testo LICX viene convertito in una risorsa binaria con estensione licenses che fornisce il supporto per la gestione delle licenze dei controlli .NET.</span><span class="sxs-lookup"><span data-stu-id="9e883-107">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="9e883-108">La risorsa binaria verrà quindi incorporata nell'output del progetto.</span><span class="sxs-lookup"><span data-stu-id="9e883-108">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="9e883-109">La compilazione incrociata fra 32 bit e 64 bit non è supportata quando si usa il Compilatore licenze nel corso della compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="9e883-109">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="9e883-110">Questo avviene perché il Compilatore licenze deve caricare assembly e non è consentito caricare assembly a 64 bit da un'applicazione a 32 bit e viceversa.</span><span class="sxs-lookup"><span data-stu-id="9e883-110">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="9e883-111">In questo caso, usare il Compilatore licenze dalla riga di comando per compilare manualmente la licenza e specificare l'architettura corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9e883-111">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="9e883-112">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e883-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="9e883-113">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="9e883-113">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="9e883-114">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9e883-114">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="9e883-115">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9e883-115">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e883-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e883-116">Syntax</span></span>  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="9e883-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="9e883-117">Option</span></span>|<span data-ttu-id="9e883-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e883-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9e883-119">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="9e883-119">**/complist:** *filename*</span></span>|<span data-ttu-id="9e883-120">Specifica il nome di un file contenente l'elenco dei componenti provvisti di licenza da includere nel file LICENSES.</span><span class="sxs-lookup"><span data-stu-id="9e883-120">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="9e883-121">A ciascun componente viene fatto riferimento mediante il nome completo, specificando un solo componente per riga.</span><span class="sxs-lookup"><span data-stu-id="9e883-121">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="9e883-122">Se si usa la riga di comando sarà possibile specificare un file separato per ciascun form del progetto.</span><span class="sxs-lookup"><span data-stu-id="9e883-122">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="9e883-123">Lc.exe accetta più file di input e produce un unico file LICENSES.</span><span class="sxs-lookup"><span data-stu-id="9e883-123">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="9e883-124">**/h**[**ELP**]</span><span class="sxs-lookup"><span data-stu-id="9e883-124">**/h**[**elp**]</span></span>|<span data-ttu-id="9e883-125">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="9e883-125">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="9e883-126">**/i:** *modulo*</span><span class="sxs-lookup"><span data-stu-id="9e883-126">**/i:** *module*</span></span>|<span data-ttu-id="9e883-127">Specifica i moduli contenenti i componenti elencati nel file **/complist**.</span><span class="sxs-lookup"><span data-stu-id="9e883-127">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="9e883-128">Per specificare più moduli, usare più flag **/i**.</span><span class="sxs-lookup"><span data-stu-id="9e883-128">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="9e883-129">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="9e883-129">**/nologo**</span></span>|<span data-ttu-id="9e883-130">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e883-130">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="9e883-131">**/outDir:** *percorso*</span><span class="sxs-lookup"><span data-stu-id="9e883-131">**/outdir:** *path*</span></span>|<span data-ttu-id="9e883-132">Specifica la directory in cui inserire il file LICENSES di output.</span><span class="sxs-lookup"><span data-stu-id="9e883-132">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="9e883-133">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="9e883-133">**/target:** *targetPE*</span></span>|<span data-ttu-id="9e883-134">Specifica l'eseguibile per cui viene generato il file LICENSES.</span><span class="sxs-lookup"><span data-stu-id="9e883-134">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="9e883-135">**/v**</span><span class="sxs-lookup"><span data-stu-id="9e883-135">**/v**</span></span>|<span data-ttu-id="9e883-136">Specifica la modalità dettagliata. Visualizza le informazioni sullo stato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="9e883-136">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="9e883-137">\**@\*\*\*file*</span><span class="sxs-lookup"><span data-stu-id="9e883-137">**@** *file*</span></span>|<span data-ttu-id="9e883-138">Specifica il file di risposta (.rsp).</span><span class="sxs-lookup"><span data-stu-id="9e883-138">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="9e883-139">**/?**</span><span class="sxs-lookup"><span data-stu-id="9e883-139">**/?**</span></span>|<span data-ttu-id="9e883-140">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="9e883-140">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9e883-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e883-141">Example</span></span>  
  
1. <span data-ttu-id="9e883-142">Se si usa un controllo con licenza `MyCompany.Samples.LicControl1` contenuto in `Samples.DLL` all'interno di un'applicazione denominata `HostApp.exe`*,* è possibile creare il file `HostAppLic.txt` includendo gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e883-142">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. <span data-ttu-id="9e883-143">Creare il file LICENSES denominato `HostApp.exe.licenses` usando il comando che segue.</span><span class="sxs-lookup"><span data-stu-id="9e883-143">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. <span data-ttu-id="9e883-144">Compilare `HostApp.exe` includendo il file LICENSES come risorsa.</span><span class="sxs-lookup"><span data-stu-id="9e883-144">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="9e883-145">Se l'applicazione fosse in C#, si utilizzerebbe il seguente comando per compilarla:</span><span class="sxs-lookup"><span data-stu-id="9e883-145">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="9e883-146">Il comando che segue compila `myApp.licenses` sulla base degli elenchi di componenti provvisti di licenza specificati da `hostapplic.txt`, `hostapplic2.txt` e `hostapplic3.txt`.</span><span class="sxs-lookup"><span data-stu-id="9e883-146">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="9e883-147">L'argomento `modulesList` specifica i moduli contenenti i componenti provvisti di licenza.</span><span class="sxs-lookup"><span data-stu-id="9e883-147">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="9e883-148">Esempio di file di risposta</span><span class="sxs-lookup"><span data-stu-id="9e883-148">Response File Example</span></span>  
 <span data-ttu-id="9e883-149">Nell'elenco seguente è riportato un esempio di file di risposta, `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="9e883-149">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="9e883-150">Per altre informazioni sui file di risposta, vedere [File di risposta](/visualstudio/msbuild/msbuild-response-files).</span><span class="sxs-lookup"><span data-stu-id="9e883-150">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt
/i:WFCPrj.dll
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="9e883-151">La riga di comando seguente usa il file `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="9e883-151">The following command line uses the `response.rsp` file.</span></span>  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e883-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e883-152">See also</span></span>

- [<span data-ttu-id="9e883-153">Strumenti</span><span class="sxs-lookup"><span data-stu-id="9e883-153">Tools</span></span>](index.md)
- [<span data-ttu-id="9e883-154">Al.exe (assembly linker)</span><span class="sxs-lookup"><span data-stu-id="9e883-154">Al.exe (Assembly Linker)</span></span>](al-exe-assembly-linker.md)
- [<span data-ttu-id="9e883-155">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="9e883-155">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
