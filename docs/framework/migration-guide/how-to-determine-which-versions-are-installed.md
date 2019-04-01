---
title: 'Procedura: Determinare le versioni di .NET Framework installate'
ms.date: 03/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c4ad3ca5694457637a82a36c8db4534df43a9d7
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504431"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="a64db-102">Procedura: Determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="a64db-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="a64db-103">Gli utenti possono [installare](https://docs.microsoft.com/dotnet/framework/install) ed eseguire nel computer più versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a64db-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="a64db-104">Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a64db-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="a64db-105">.NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:</span><span class="sxs-lookup"><span data-stu-id="a64db-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="a64db-106">Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app.</span><span class="sxs-lookup"><span data-stu-id="a64db-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="a64db-107">.NET Framework e gli assembly condividono lo stesso numero di versione.</span><span class="sxs-lookup"><span data-stu-id="a64db-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="a64db-108">Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app</span><span class="sxs-lookup"><span data-stu-id="a64db-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="a64db-109">e che viene identificato dal relativo numero di versione (vedere [Versioni e dipendenze](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="a64db-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="a64db-110">Ogni nuova versione di .NET Framework conserva funzionalità dalle versioni precedenti e ne aggiunge nuove.</span><span class="sxs-lookup"><span data-stu-id="a64db-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="a64db-111">È possibile caricare più versioni di .NET Framework in un singolo computer contemporaneamente, il che significa che si può installare .NET Framework senza dover disinstallare le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a64db-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="a64db-112">In generale, non è necessario disinstallare alcuna versione precedente di .NET Framework, perché un'applicazione in uso potrebbe dipendere da una versione specifica e smettere di funzionare se quella versione viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="a64db-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="a64db-113">Esiste una differenza tra la versione di .NET Framework e la versione di CLR:</span><span class="sxs-lookup"><span data-stu-id="a64db-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="a64db-114">La versione di .NET Framework è basata sul set di assembly che costituiscono la libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a64db-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="a64db-115">Ad esempio, le versioni di .NET Framework includono 4.5, 4.6.1 e 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="a64db-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="a64db-116">La versione di CLR è basata sul runtime in cui vengono eseguite le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a64db-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="a64db-117">In genere una singola versione di CLR supporta più versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a64db-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="a64db-118">La versione di CLR 4.0.30319.*xxxxx*, ad esempio, supporta le versioni di .NET Framework da 4 a 4.5.2 e la versione di CLR 4.0.30319.42000 supporta le versioni di .NET Framework a partire da .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="a64db-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="a64db-119">Per altre informazioni sulle versioni, vedere [Versioni e dipendenze di .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="a64db-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>


<span data-ttu-id="a64db-120">Per ottenere un elenco delle versioni di .NET Framework installate in un computer, accedere al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a64db-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="a64db-121">È possibile usare l'editor del Registro di sistema per visualizzare il Registro di sistema o eseguire una query tramite codice:</span><span class="sxs-lookup"><span data-stu-id="a64db-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="a64db-122">Trovare le versioni di .NET Framework più recenti (4.5 e successive):</span><span class="sxs-lookup"><span data-stu-id="a64db-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="a64db-123">Usare l'editor del Registro di sistema per trovare le versioni di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="a64db-124">Eseguire una query tramite codice nel Registro di sistema per trovare le versioni di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="a64db-125">Eseguire una query tramite PowerShell nel Registro di sistema per trovare le versioni di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="a64db-126">Trovare le versioni di .NET Framework precedenti (1 - 4):</span><span class="sxs-lookup"><span data-stu-id="a64db-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="a64db-127">Usare l'editor del Registro di sistema per trovare le versioni di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="a64db-128">Eseguire una query tramite codice nel Registro di sistema per trovare le versioni di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="a64db-129">Per ottenere un elenco delle versioni di CLR installate in un computer, usare uno strumento o codice:</span><span class="sxs-lookup"><span data-stu-id="a64db-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
- [<span data-ttu-id="a64db-130">Usare lo strumento Clrver</span><span class="sxs-lookup"><span data-stu-id="a64db-130">Use the Clrver tool</span></span>](#clr_a)  
- [<span data-ttu-id="a64db-131">Eseguire una query tramite codice nella classe Environment</span><span class="sxs-lookup"><span data-stu-id="a64db-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="a64db-132">Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: Determinare gli aggiornamenti di .NET Framework installati](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="a64db-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="a64db-133">Trovare le versioni di .NET Framework più recenti (4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="a64db-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="a64db-134">Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="a64db-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="a64db-135">Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a64db-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="a64db-136">Per eseguire regedit, è necessario avere le credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="a64db-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="a64db-137">Nell'Editor del Registro di sistema aprire la seguente sottochiave: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="a64db-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="a64db-138">Se la sottochiave **Full** non è presente, .NET Framework 4.5 o versioni successive non è installato.</span><span class="sxs-lookup"><span data-stu-id="a64db-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a64db-139">La cartella **NET Framework Setup** nel Registro di sistema non inizia con un punto.</span><span class="sxs-lookup"><span data-stu-id="a64db-139">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

3. <span data-ttu-id="a64db-140">Verificare la presenza di una voce DWORD denominata **Release**.</span><span class="sxs-lookup"><span data-stu-id="a64db-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="a64db-141">Se esiste, .NET Framework 4.5 o versioni successive è installato.</span><span class="sxs-lookup"><span data-stu-id="a64db-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="a64db-142">Il valore è una chiave di rilascio che corrisponde a una particolare versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a64db-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="a64db-143">Nella figura seguente, ad esempio, il valore della voce **Release** è *378389*, ovvero la chiave di rilascio per .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="a64db-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="a64db-144">![Voce del Registro di sistema per .NET Framework 4.5](media/clr-installdir.png "Voce del Registro di sistema per .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="a64db-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="a64db-145">La tabella seguente elenca il valore minimo della voce **Release** per ogni versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a64db-145">The following table lists the minimum value of the **Release** entry for each .NET Framework version.</span></span> <span data-ttu-id="a64db-146">È possibile usare questi valori come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a64db-146">You can use these values as follows:</span></span>

- <span data-ttu-id="a64db-147">Per determinare se è presente una versione minima di .NET Framework, verificare se il valore DWORD della voce **Release** trovato nel Registro di sistema è *maggiore o uguale* al valore elencato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a64db-147">To determine whether a minimum .NET Framework version is present, test whether the **Release** DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="a64db-148">Ad esempio, se l'applicazione richiede .NET Framework 4.7 o versioni successive, eseguire un test per il valore minimo della chiave di rilascio *460798*.</span><span class="sxs-lookup"><span data-stu-id="a64db-148">For example, if your application requires the .NET Framework 4.7 or later, you test for a minimum release key value of *460798*.</span></span>

- <span data-ttu-id="a64db-149">Per eseguire il test per più versioni, iniziare con la versione più recente di .NET Framework e quindi ripetere il test per ogni versione precedente successiva.</span><span class="sxs-lookup"><span data-stu-id="a64db-149">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="a64db-150">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-150">.NET Framework version</span></span>|<span data-ttu-id="a64db-151">Valore DWORD di Release</span><span class="sxs-lookup"><span data-stu-id="a64db-151">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="a64db-152">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a64db-152">.NET Framework 4.5</span></span>|<span data-ttu-id="a64db-153">378389</span><span class="sxs-lookup"><span data-stu-id="a64db-153">378389</span></span>|
|<span data-ttu-id="a64db-154">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="a64db-154">.NET Framework 4.5.1</span></span>|<span data-ttu-id="a64db-155">378675</span><span class="sxs-lookup"><span data-stu-id="a64db-155">378675</span></span>|
|<span data-ttu-id="a64db-156">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a64db-156">.NET Framework 4.5.2</span></span>|<span data-ttu-id="a64db-157">379893</span><span class="sxs-lookup"><span data-stu-id="a64db-157">379893</span></span>|
|<span data-ttu-id="a64db-158">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="a64db-158">.NET Framework 4.6</span></span>|<span data-ttu-id="a64db-159">393295</span><span class="sxs-lookup"><span data-stu-id="a64db-159">393295</span></span>|
|<span data-ttu-id="a64db-160">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="a64db-160">.NET Framework 4.6.1</span></span>|<span data-ttu-id="a64db-161">394254</span><span class="sxs-lookup"><span data-stu-id="a64db-161">394254</span></span>|
|<span data-ttu-id="a64db-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="a64db-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="a64db-163">394802</span><span class="sxs-lookup"><span data-stu-id="a64db-163">394802</span></span>|
|<span data-ttu-id="a64db-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="a64db-164">.NET Framework 4.7</span></span>|<span data-ttu-id="a64db-165">460798</span><span class="sxs-lookup"><span data-stu-id="a64db-165">460798</span></span>|
|<span data-ttu-id="a64db-166">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a64db-166">.NET Framework 4.7.1</span></span>|<span data-ttu-id="a64db-167">461308</span><span class="sxs-lookup"><span data-stu-id="a64db-167">461308</span></span>|
|<span data-ttu-id="a64db-168">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="a64db-168">.NET Framework 4.7.2</span></span>|<span data-ttu-id="a64db-169">461808</span><span class="sxs-lookup"><span data-stu-id="a64db-169">461808</span></span>|

<span data-ttu-id="a64db-170">Per una tabella completa delle chiavi di rilascio per .NET Framework per versioni specifiche del sistema operativo Windows, vedere [Chiavi di rilascio di .NET Framework e versioni del sistema operativo Windows](release-keys-and-os-versions.md).</span><span class="sxs-lookup"><span data-stu-id="a64db-170">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="a64db-171">Trovare le versioni di .NET Framework 4.5 e successive tramite codice</span><span class="sxs-lookup"><span data-stu-id="a64db-171">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="a64db-172">Usare i metodi <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> e <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> per accedere alla sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="a64db-172">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="a64db-173">L'esistenza della voce DWORD **Release** nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** indica che .NET Framework 4.5 o versioni successive è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="a64db-173">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="a64db-174">Verificare il valore della voce **Release** per determinare la versione installata.</span><span class="sxs-lookup"><span data-stu-id="a64db-174">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="a64db-175">Affinché sia compatibile con la versione attualmente installata, è possibile cercare un valore maggiore o uguale ai valori elencati nella [tabella delle versioni di .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="a64db-175">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="a64db-176">L'esempio seguente illustra come verificare il valore della voce **Release** nel Registro di sistema per determinare quale versione di .NET Framework 4.5 e versioni successive è installata:</span><span class="sxs-lookup"><span data-stu-id="a64db-176">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="a64db-177">Questo esempio segue la procedura consigliata per il controllo della versione:</span><span class="sxs-lookup"><span data-stu-id="a64db-177">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="a64db-178">Verifica se il valore della voce **Release** è *maggiore o uguale* al valore delle parole chiave Release note.</span><span class="sxs-lookup"><span data-stu-id="a64db-178">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="a64db-179">Controlla in ordine dalla versione più recente a quella meno recente.</span><span class="sxs-lookup"><span data-stu-id="a64db-179">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="a64db-180">Verificare la presenza di una versione minima richiesta di .NET Framework (4.5 e versioni successive) con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a64db-180">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="a64db-181">Usare i comandi PowerShell per verificare il valore della voce **Release** della sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="a64db-181">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="a64db-182">Gli esempi seguenti illustrano come verificare il valore della voce **Release** per determinare se .NET Framework 4.6.2 o versioni successive è installato.</span><span class="sxs-lookup"><span data-stu-id="a64db-182">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="a64db-183">Questo codice restituisce `True` se è installato e `False` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="a64db-183">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="a64db-184">Per cercare una versione minima richiesta di .NET Framework diversa, sostituire *394802* in questi esempi con un valore **Release** della [tabella delle versioni di .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="a64db-184">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="a64db-185">Trovare le versioni di .NET Framework precedenti (1 - 4)</span><span class="sxs-lookup"><span data-stu-id="a64db-185">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="a64db-186">Trovare le versioni di .NET Framework da 1 a 4 nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="a64db-186">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="a64db-187">Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a64db-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="a64db-188">Per eseguire regedit, è necessario avere le credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="a64db-188">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="a64db-189">Nell'Editor del Registro di sistema aprire la seguente sottochiave: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="a64db-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="a64db-190">Per le versioni di .NET Framework da 1.1 a 3.5, ogni versione installata è elencata come sottochiave nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="a64db-190">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="a64db-191">Ad esempio, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="a64db-191">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="a64db-192">Il numero di versione è archiviato come valore nella voce **Version** della sottochiave della versione.</span><span class="sxs-lookup"><span data-stu-id="a64db-192">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="a64db-193">Per .NET Framework 4, la voce **Version** si trova nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** o in entrambe le sottochiavi.</span><span class="sxs-lookup"><span data-stu-id="a64db-193">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a64db-194">La cartella **NET Framework Setup** nel Registro di sistema non inizia con un punto.</span><span class="sxs-lookup"><span data-stu-id="a64db-194">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="a64db-195">La figura seguente illustra la sottochiave e la relativa voce **Version** per .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="a64db-195">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="a64db-196">![Voce del Registro di sistema per .NET Framework 3.5.](media/net-4-and-earlier.png ".NET framework 3.5 e versioni precedenti")</span><span class="sxs-lookup"><span data-stu-id="a64db-196">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="a64db-197">Trovare le versioni di .NET Framework da 1 a 4 tramite codice</span><span class="sxs-lookup"><span data-stu-id="a64db-197">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="a64db-198">Usare la classe <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> per accedere alla sottochiave **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="a64db-198">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="a64db-199">L'esempio seguente illustra come trovare le versioni .NET Framework da 1 a 4 installate:</span><span class="sxs-lookup"><span data-stu-id="a64db-199">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a><span data-ttu-id="a64db-200">Trovare le versioni di CLR</span><span class="sxs-lookup"><span data-stu-id="a64db-200">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="a64db-201">Trovare la versione corrente di CLR con Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="a64db-201">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="a64db-202">Usare lo [strumento della versione CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) per determinare le versioni di CLR installate in un computer:</span><span class="sxs-lookup"><span data-stu-id="a64db-202">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="a64db-203">Da un [Prompt dei comandi per gli sviluppatori per Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) immettere `clrver`.</span><span class="sxs-lookup"><span data-stu-id="a64db-203">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="a64db-204">Esempio di output:</span><span class="sxs-lookup"><span data-stu-id="a64db-204">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="a64db-205">Trovare la versione corrente di CLR con la classe Environment</span><span class="sxs-lookup"><span data-stu-id="a64db-205">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a64db-206">Per .NET Framework 4.5 e versioni successive, non usare la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per rilevare la versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="a64db-206">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="a64db-207">Eseguire invece una query nel Registro di sistema come descritto in [Trovare le versioni di .NET Framework 4.5 e successive tramite codice](#net_d).</span><span class="sxs-lookup"><span data-stu-id="a64db-207">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="a64db-208">Eseguire la query per la proprietà <xref:System.Environment.Version?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="a64db-208">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="a64db-209">L'oggetto `System.Version` identifica la versione del runtime che esegue attualmente il codice.</span><span class="sxs-lookup"><span data-stu-id="a64db-209">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="a64db-210">Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere state installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="a64db-210">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="a64db-211">Per le versioni 4, 4.5, 4.5.1 e 4.5.2 di .NET Framework, la rappresentazione stringa dell'oggetto <xref:System.Version> restituito ha il formato 4.0.30319.*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="a64db-211">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="a64db-212">Per .NET Framework 4.6 e versioni successive, ha il formato 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="a64db-212">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="a64db-213">Dopo aver ottenuto l'oggetto `Version`, eseguire una query come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a64db-213">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="a64db-214">Per l'identificatore della versione principale (ad esempio, *4* per la versione 4.0), usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a64db-214">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="a64db-215">Per l'identificatore della versione secondaria (ad esempio, *0* per la versione 4.0), usare la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a64db-215">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="a64db-216">Per l'intera stringa di versione (ad esempio, *4.0.30319.18010*), usare il metodo <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a64db-216">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a64db-217">Questo metodo restituisce un valore singolo che riflette la versione del runtime che esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="a64db-217">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="a64db-218">Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="a64db-218">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>



<span data-ttu-id="a64db-219">L'esempio seguente usa la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare le informazioni sulla versione di CLR:</span><span class="sxs-lookup"><span data-stu-id="a64db-219">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="a64db-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a64db-220">See also</span></span>

- [<span data-ttu-id="a64db-221">Procedura: Determinare gli aggiornamenti di .NET Framework installati</span><span class="sxs-lookup"><span data-stu-id="a64db-221">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="a64db-222">Installare .NET Framework per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="a64db-222">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="a64db-223">Versioni e dipendenze di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64db-223">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
