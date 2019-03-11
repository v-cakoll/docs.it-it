---
title: Regsvcs.exe (strumento di installazione dei servizi .NET)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b80df56c9f45f7dd195e1f7bbd03063fa30abb3a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466748"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="2ef4e-102">Regsvcs.exe (strumento di installazione dei servizi .NET)</span><span class="sxs-lookup"><span data-stu-id="2ef4e-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="2ef4e-103">Lo strumento di installazione dei servizi .NET effettua le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="2ef4e-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
-   <span data-ttu-id="2ef4e-104">Carica e registra un assembly.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-104">Loads and registers an assembly.</span></span>  
  
-   <span data-ttu-id="2ef4e-105">Genera, registra e installa una libreria dei tipi in un'applicazione COM+ specificata.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
-   <span data-ttu-id="2ef4e-106">Configura i servizi aggiunti alla classe a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="2ef4e-107">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="2ef4e-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="2ef4e-108">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2ef4e-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="2ef4e-109">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2ef4e-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef4e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ef4e-110">Syntax</span></span>  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
## <a name="parameters"></a><span data-ttu-id="2ef4e-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ef4e-111">Parameters</span></span>  
  
|<span data-ttu-id="2ef4e-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="2ef4e-112">Argument</span></span>|<span data-ttu-id="2ef4e-113">Description</span><span class="sxs-lookup"><span data-stu-id="2ef4e-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2ef4e-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="2ef4e-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="2ef4e-115">File di assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-115">The source assembly file.</span></span> <span data-ttu-id="2ef4e-116">L'assembly deve essere firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="2ef4e-117">Per altre informazioni, vedere [Firma di un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="2ef4e-117">For more information, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>|  
  
|<span data-ttu-id="2ef4e-118">Opzione</span><span class="sxs-lookup"><span data-stu-id="2ef4e-118">Option</span></span>|<span data-ttu-id="2ef4e-119">Description</span><span class="sxs-lookup"><span data-stu-id="2ef4e-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2ef4e-120">**/appdir:** *percorso*</span><span class="sxs-lookup"><span data-stu-id="2ef4e-120">**/appdir:** *path*</span></span>|<span data-ttu-id="2ef4e-121">Specifica la directory radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="2ef4e-122">**/appname:** *nomeApplicazione*</span><span class="sxs-lookup"><span data-stu-id="2ef4e-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="2ef4e-123">Specifica il nome dell'applicazione COM+ da trovare o creare.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="2ef4e-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-124">**/c**</span></span>|<span data-ttu-id="2ef4e-125">Crea l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-125">Creates the target application.</span></span>|  
|<span data-ttu-id="2ef4e-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-126">**/componly**</span></span>|<span data-ttu-id="2ef4e-127">Configura solo i componenti, ignorando metodi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="2ef4e-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-128">**/exapp**</span></span>|<span data-ttu-id="2ef4e-129">Indica allo strumento di prevedere un'applicazione esistente.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="2ef4e-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-130">**/extlb**</span></span>|<span data-ttu-id="2ef4e-131">Utilizza una libreria dei tipi esistente.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="2ef4e-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-132">**/fc**</span></span>|<span data-ttu-id="2ef4e-133">Trova o crea l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="2ef4e-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-134">**/help**</span></span>|<span data-ttu-id="2ef4e-135">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="2ef4e-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-136">**/noreconfig**</span></span>|<span data-ttu-id="2ef4e-137">Non riconfigura un'applicazione di destinazione esistente.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="2ef4e-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-138">**/nologo**</span></span>|<span data-ttu-id="2ef4e-139">Evita la visualizzazione del messaggio di avvio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="2ef4e-140">**/parname:** *nome*</span><span class="sxs-lookup"><span data-stu-id="2ef4e-140">**/parname:** *name*</span></span>|<span data-ttu-id="2ef4e-141">Specifica il nome o l'ID dell'applicazione COM+ da trovare o creare.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="2ef4e-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-142">**/reconfig**</span></span>|<span data-ttu-id="2ef4e-143">Riconfigura un'applicazione di destinazione esistente.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="2ef4e-144">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-144">This is the default.</span></span>|  
|<span data-ttu-id="2ef4e-145">**/tlb:** *filelibreriatipi*</span><span class="sxs-lookup"><span data-stu-id="2ef4e-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="2ef4e-146">Specifica il file della libreria dei tipi da installare.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="2ef4e-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-147">**/u**</span></span>|<span data-ttu-id="2ef4e-148">Disinstalla l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="2ef4e-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-149">**/quiet**</span></span>|<span data-ttu-id="2ef4e-150">Specifica la modalità non interattiva; non visualizza il logo e i messaggi di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="2ef4e-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="2ef4e-151">**/?**</span></span>|<span data-ttu-id="2ef4e-152">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ef4e-153">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2ef4e-153">Remarks</span></span>  
 <span data-ttu-id="2ef4e-154">Regsvcs.exe richiede un file di assembly di origine specificato da *FileAssembly.dll*.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="2ef4e-155">L'assembly deve essere firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="2ef4e-156">Per altre informazioni sulla firma con un nome sicuro, vedere [Firma di un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="2ef4e-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span> <span data-ttu-id="2ef4e-157">I nomi dell'applicazione di destinazione e del file della libreria dei tipi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="2ef4e-158">L'argomento *nomeApplicazione* può essere generato dal file di assembly di origine e, se non esiste già, viene creato da Regsvcs.exe.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="2ef4e-159">L'argomento *filelibreriatipi* può specificare il nome di una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="2ef4e-160">Se non lo si specifica, come impostazione predefinita verrà usato il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="2ef4e-161">Quando Regsvcs.exe registra i metodi di un componente, lo strumento è soggetto a [richieste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) e [richieste di collegamento](../../../docs/framework/misc/link-demands.md) su tali metodi.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="2ef4e-162">Poiché lo strumento viene eseguito in un ambiente completamente attendibile, molte richieste di autorizzazione vengono completate.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="2ef4e-163">Regsvcs.exe non è tuttavia in grado di registrare componenti con metodi protetti da una richiesta o una richiesta di collegamento per <xref:System.Security.Permissions.StrongNameIdentityPermission> o <xref:System.Security.Permissions.PublisherIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="2ef4e-164">Per usare Regsvcs.exe, è necessario disporre dei privilegi amministrativi sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="2ef4e-165">Se durante una di queste operazioni l'esecuzione di Regsvcs.exe si interrompe, verranno visualizzati messaggi di errore pertinenti.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2ef4e-166">Esempi</span><span class="sxs-lookup"><span data-stu-id="2ef4e-166">Examples</span></span>  
 <span data-ttu-id="2ef4e-167">Il comando che segue aggiunge a `myTest.dll` (un'applicazione COM+ esistente) tutte le classi pubbliche contenute in `myTargetApp` e produce la libreria dei tipi `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="2ef4e-168">Il comando che segue aggiunge a `myTest.dll` (un'applicazione COM+ esistente) tutte le classi pubbliche contenute in `myTargetApp` e produce la libreria dei tipi `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="2ef4e-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ef4e-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ef4e-169">See also</span></span>
- [<span data-ttu-id="2ef4e-170">Strumenti</span><span class="sxs-lookup"><span data-stu-id="2ef4e-170">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="2ef4e-171">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="2ef4e-171">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [<span data-ttu-id="2ef4e-172">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="2ef4e-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
