---
title: 'Procedura: Determinare le versioni di .NET Framework installate'
ms.date: 01/24/2018
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: edf1e5a53f6f578f943cf8775a798b5681d2d9dd
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="a3eee-102">Procedura: Determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="a3eee-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="a3eee-103">Gli utenti possono installare ed eseguire nel computer più versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3eee-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="a3eee-104">Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a3eee-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="a3eee-105">Si noti che .NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:</span><span class="sxs-lookup"><span data-stu-id="a3eee-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="a3eee-106">Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app.</span><span class="sxs-lookup"><span data-stu-id="a3eee-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="a3eee-107">.NET Framework e gli assembly condividono lo stesso numero di versione.</span><span class="sxs-lookup"><span data-stu-id="a3eee-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="a3eee-108">Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app</span><span class="sxs-lookup"><span data-stu-id="a3eee-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="a3eee-109">e che viene identificato dal relativo numero di versione (vedere [Versioni e dipendenze](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="a3eee-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="a3eee-110">Per ottenere un elenco accurato delle versioni di .NET Framework installate in un computer, è possibile visualizzare il Registro di sistema o eseguire query sul Registro di sistema nel codice:</span><span class="sxs-lookup"><span data-stu-id="a3eee-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="a3eee-111">Visualizzazione del Registro di sistema (versioni 1-4)</span><span class="sxs-lookup"><span data-stu-id="a3eee-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="a3eee-112">Visualizzazione del Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="a3eee-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="a3eee-113">Uso del codice per eseguire query sul Registro di sistema (versioni 1-4)</span><span class="sxs-lookup"><span data-stu-id="a3eee-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="a3eee-114">Uso del codice per eseguire query sul Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="a3eee-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="a3eee-115">Uso di PowerShell per eseguire query sul Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="a3eee-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  
  
 <span data-ttu-id="a3eee-116">Per trovare la versione di CLR, è possibile usare uno strumento o il codice:</span><span class="sxs-lookup"><span data-stu-id="a3eee-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="a3eee-117">Uso dello strumento Clrver</span><span class="sxs-lookup"><span data-stu-id="a3eee-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="a3eee-118">Uso del codice per eseguire query sulla classe System.Environment</span><span class="sxs-lookup"><span data-stu-id="a3eee-118">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="a3eee-119">Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: determinare gli aggiornamenti di .NET Framework installati](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="a3eee-119">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="a3eee-120">Per informazioni sull'installazione di .NET Framework, vedere [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="a3eee-120">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="a3eee-121">Per trovare le versioni di .NET Framework visualizzando il Registro di sistema (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="a3eee-121">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="a3eee-122">Scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="a3eee-122">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="a3eee-123">Nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="a3eee-123">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="a3eee-124">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="a3eee-124">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="a3eee-125">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="a3eee-125">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="a3eee-126">Le versioni installate sono elencate nella sottochiave NDP.</span><span class="sxs-lookup"><span data-stu-id="a3eee-126">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="a3eee-127">Il numero di versione è archiviato nella voce **Version**.</span><span class="sxs-lookup"><span data-stu-id="a3eee-127">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="a3eee-128">Per [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la voce **Version** è inclusa nella sottochiave Client o Full (in NDP) o in entrambe.</span><span class="sxs-lookup"><span data-stu-id="a3eee-128">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="a3eee-129">La cartella "NET Framework Setup" nel Registro di sistema non inizia con un punto.</span><span class="sxs-lookup"><span data-stu-id="a3eee-129">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="a3eee-130">Per trovare le versioni di .NET Framework visualizzando il Registro di sistema (.NET Framework 4.5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a3eee-130">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="a3eee-131">Scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="a3eee-131">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="a3eee-132">Nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="a3eee-132">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="a3eee-133">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="a3eee-133">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="a3eee-134">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="a3eee-134">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="a3eee-135">Si noti che il percorso della sottochiave `Full` include la sottochiave `Net Framework` e non `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="a3eee-135">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3eee-136">Se la sottochiave `Full` non è presente, .NET Framework 4.5 o versione successiva non è installato.</span><span class="sxs-lookup"><span data-stu-id="a3eee-136">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="a3eee-137">Verificare la presenza di un valore DWORD denominato `Release`.</span><span class="sxs-lookup"><span data-stu-id="a3eee-137">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="a3eee-138">L'esistenza del valore DWORD `Release` indica che nel computer è stato installato [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a3eee-138">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="a3eee-139">![Voce del Registro di sistema per .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="a3eee-139">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="a3eee-140">Il valore DWORD `Release` indica quale versione di .NET Framework è installata.</span><span class="sxs-lookup"><span data-stu-id="a3eee-140">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="a3eee-141">Valore DWORD di Release</span><span class="sxs-lookup"><span data-stu-id="a3eee-141">Value of the Release DWORD</span></span>|<span data-ttu-id="a3eee-142">Versione</span><span class="sxs-lookup"><span data-stu-id="a3eee-142">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="a3eee-143">378389</span><span class="sxs-lookup"><span data-stu-id="a3eee-143">378389</span></span>|<span data-ttu-id="a3eee-144">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a3eee-144">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="a3eee-145">378675</span><span class="sxs-lookup"><span data-stu-id="a3eee-145">378675</span></span>|<span data-ttu-id="a3eee-146">.NET Framework 4.5.1 installato con Windows 8.1 o Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a3eee-146">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="a3eee-147">378758</span><span class="sxs-lookup"><span data-stu-id="a3eee-147">378758</span></span>|<span data-ttu-id="a3eee-148">.NET Framework 4.5.1 installato in Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="a3eee-148">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="a3eee-149">379893</span><span class="sxs-lookup"><span data-stu-id="a3eee-149">379893</span></span>|<span data-ttu-id="a3eee-150">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a3eee-150">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="a3eee-151">Nei sistemi Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="a3eee-151">On Windows 10 systems: 393295</span></span><br /><br /> <span data-ttu-id="a3eee-152">In tutte le altre versioni del sistema operativo: 393297</span><span class="sxs-lookup"><span data-stu-id="a3eee-152">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="a3eee-153">Nei sistemi Windows 10 con aggiornamento di novembre: 394254</span><span class="sxs-lookup"><span data-stu-id="a3eee-153">On Windows 10 November Update systems: 394254</span></span><br /><br /> <span data-ttu-id="a3eee-154">In tutte le altre versioni del sistema operativo: 394271</span><span class="sxs-lookup"><span data-stu-id="a3eee-154">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="a3eee-155">Nell'Aggiornamento dell'anniversario di Windows 10: 394802</span><span class="sxs-lookup"><span data-stu-id="a3eee-155">On Windows 10 Anniversary Update: 394802</span></span><br /><br /> <span data-ttu-id="a3eee-156">In tutte le altre versioni del sistema operativo: 394806</span><span class="sxs-lookup"><span data-stu-id="a3eee-156">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="a3eee-157">In Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="a3eee-157">On Windows 10 Creators Update: 460798</span></span><br/><br/> <span data-ttu-id="a3eee-158">In tutte le altre versioni del sistema operativo: 460805</span><span class="sxs-lookup"><span data-stu-id="a3eee-158">On all other OS versions: 460805</span></span> | <span data-ttu-id="a3eee-159">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="a3eee-159">.NET Framework 4.7</span></span> |
    |<span data-ttu-id="a3eee-160">In Windows 10 Fall Creators Update: 461308</span><span class="sxs-lookup"><span data-stu-id="a3eee-160">On Windows 10 Fall Creators Update: 461308</span></span><br/><br/> <span data-ttu-id="a3eee-161">In tutte le altre versioni del sistema operativo: 461310</span><span class="sxs-lookup"><span data-stu-id="a3eee-161">On all other OS versions: 461310</span></span> | <span data-ttu-id="a3eee-162">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a3eee-162">.NET Framework 4.7.1</span></span> |
    
<a name="net_c"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="a3eee-163">Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="a3eee-163">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="a3eee-164">Usare la classe <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> per accedere alla sottochiave Software\Microsoft\NET Framework Setup\NDP in HKEY_LOCAL_MACHINE nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="a3eee-164">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="a3eee-165">Nel codice seguente viene illustrato un esempio di questa query.</span><span class="sxs-lookup"><span data-stu-id="a3eee-165">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3eee-166">Questo codice non mostra come rilevare [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a3eee-166">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="a3eee-167">Controllare il valore DWORD `Release` per rilevare tali versioni, come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="a3eee-167">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="a3eee-168">Per il codice che rileva [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versioni successive, vedere la sezione successiva in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a3eee-168">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     <span data-ttu-id="a3eee-169">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3eee-169">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="a3eee-170">Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 4.5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a3eee-170">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="a3eee-171">L'esistenza del valore DWORD `Release` indica che nel computer è stato installato .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a3eee-171">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="a3eee-172">Il valore di questa parola chiave indica la versione installata.</span><span class="sxs-lookup"><span data-stu-id="a3eee-172">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="a3eee-173">Per controllare questa parola chiave, usare i metodi <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> e <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> della classe <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> per accedere alla sottochiave Software\Microsoft\NET Framework Setup\NDP\v4\Full in HKEY_LOCAL_MACHINE nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="a3eee-173">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="a3eee-174">Verificare il valore della parola chiave `Release` per determinare la versione installata.</span><span class="sxs-lookup"><span data-stu-id="a3eee-174">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="a3eee-175">Affinché sia compatibile con la versione attualmente installata, è possibile cercare un valore maggiore o uguale ai valori elencati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a3eee-175">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="a3eee-176">Ecco le versioni di .NET Framework e le parole chiave `Release` associate.</span><span class="sxs-lookup"><span data-stu-id="a3eee-176">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="a3eee-177">Versione</span><span class="sxs-lookup"><span data-stu-id="a3eee-177">Version</span></span>|<span data-ttu-id="a3eee-178">Valore DWORD di Release</span><span class="sxs-lookup"><span data-stu-id="a3eee-178">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="a3eee-179">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a3eee-179">.NET Framework 4.5</span></span>|<span data-ttu-id="a3eee-180">378389</span><span class="sxs-lookup"><span data-stu-id="a3eee-180">378389</span></span>|
    |<span data-ttu-id="a3eee-181">.NET Framework 4.5.1 installato con Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a3eee-181">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="a3eee-182">378675</span><span class="sxs-lookup"><span data-stu-id="a3eee-182">378675</span></span>|
    |<span data-ttu-id="a3eee-183">.NET Framework 4.5.1 installato in Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="a3eee-183">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="a3eee-184">378758</span><span class="sxs-lookup"><span data-stu-id="a3eee-184">378758</span></span>|
    |<span data-ttu-id="a3eee-185">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a3eee-185">.NET Framework 4.5.2</span></span>|<span data-ttu-id="a3eee-186">379893</span><span class="sxs-lookup"><span data-stu-id="a3eee-186">379893</span></span>|
    |<span data-ttu-id="a3eee-187">.NET Framework 4.6 installato con Windows 10</span><span class="sxs-lookup"><span data-stu-id="a3eee-187">.NET Framework 4.6 installed with Windows 10</span></span>|<span data-ttu-id="a3eee-188">393295</span><span class="sxs-lookup"><span data-stu-id="a3eee-188">393295</span></span>|
    |<span data-ttu-id="a3eee-189">.NET Framework 4.6 installato in tutte le altre versioni del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="a3eee-189">.NET Framework 4.6 installed on all other Windows OS versions</span></span>|<span data-ttu-id="a3eee-190">393297</span><span class="sxs-lookup"><span data-stu-id="a3eee-190">393297</span></span>|
    |<span data-ttu-id="a3eee-191">.NET Framework 4.6.1 installato in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a3eee-191">.NET Framework 4.6.1 installed on Windows 10</span></span>|<span data-ttu-id="a3eee-192">394254</span><span class="sxs-lookup"><span data-stu-id="a3eee-192">394254</span></span>|
    |<span data-ttu-id="a3eee-193">.NET Framework 4.6.1 installato in tutte le altre versioni del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="a3eee-193">.NET Framework 4.6.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="a3eee-194">394271</span><span class="sxs-lookup"><span data-stu-id="a3eee-194">394271</span></span>|
    |<span data-ttu-id="a3eee-195">.NET Framework 4.6.2 installato nell'Aggiornamento dell'anniversario di Windows 10</span><span class="sxs-lookup"><span data-stu-id="a3eee-195">.NET Framework 4.6.2 installed on Windows 10 Anniversary Update</span></span>|<span data-ttu-id="a3eee-196">394802</span><span class="sxs-lookup"><span data-stu-id="a3eee-196">394802</span></span>|
    |<span data-ttu-id="a3eee-197">.NET Framework 4.6.2 installato in tutte le altre versioni del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="a3eee-197">.NET Framework 4.6.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="a3eee-198">394806</span><span class="sxs-lookup"><span data-stu-id="a3eee-198">394806</span></span>|
    |<span data-ttu-id="a3eee-199">.NET Framework 4.7 installato in Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="a3eee-199">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="a3eee-200">460798</span><span class="sxs-lookup"><span data-stu-id="a3eee-200">460798</span></span>|
    |<span data-ttu-id="a3eee-201">.NET Framework 4.7 installato in tutte le altre versioni del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a3eee-201">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="a3eee-202">460805</span><span class="sxs-lookup"><span data-stu-id="a3eee-202">460805</span></span>|
    |<span data-ttu-id="a3eee-203">.NET Framework 4.7.1 installato in Windows 10 Fall Creators Update</span><span class="sxs-lookup"><span data-stu-id="a3eee-203">.NET Framework 4.7.1 installed on Windows 10 Fall Creators Update</span></span>|<span data-ttu-id="a3eee-204">461308</span><span class="sxs-lookup"><span data-stu-id="a3eee-204">461308</span></span>|
    |<span data-ttu-id="a3eee-205">.NET Framework 4.7.1 installato in tutte le altre versioni del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="a3eee-205">.NET Framework 4.7.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="a3eee-206">461310</span><span class="sxs-lookup"><span data-stu-id="a3eee-206">461310</span></span>|

     <span data-ttu-id="a3eee-207">Nell'esempio seguente viene controllato il valore `Release` del Registro di sistema per determinare se è installato [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versione successiva di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3eee-207">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     <span data-ttu-id="a3eee-208">Questo esempio segue la procedura consigliata per il controllo della versione:</span><span class="sxs-lookup"><span data-stu-id="a3eee-208">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="a3eee-209">Controlla se il valore della voce `Release` è *maggiore o uguale* al valore delle parole chiave Release note.</span><span class="sxs-lookup"><span data-stu-id="a3eee-209">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="a3eee-210">Controlla in ordine dalla versione più recente a quella meno recente.</span><span class="sxs-lookup"><span data-stu-id="a3eee-210">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a><span data-ttu-id="a3eee-211">Per controllare la versione minima di .NET Framework necessaria eseguendo query sul Registro di sistema in PowerShell (.NET Framework 4.5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a3eee-211">To check for a minimum-required .NET Framework version by querying the registry in PowerShell (.NET Framework 4.5 and later)</span></span>

- <span data-ttu-id="a3eee-212">Nell'esempio seguente viene controllato il valore della parola chiave `Release` per determinare se è installato .NET Framework 4.6.2 o versione successiva, indipendentemente dalla versione del sistema operativo Windows; viene restituito `True` in caso di esito positivo e `False` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="a3eee-212">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed, regardless of Windows OS version (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    Get-ChildItem "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | ForEach-Object { $_ -ge 394802 } 
    ```

    <span data-ttu-id="a3eee-213">È possibile sostituire il valore `394802` nell'esempio precedente con un altro valore indicato nella tabella seguente per controllare la presenza di una versione minima necessaria diversa di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3eee-213">You can replace `394802` in the previous example with another value from the following table to check for a different minimum-required .NET Framework version.</span></span>
  
    |<span data-ttu-id="a3eee-214">Versione</span><span class="sxs-lookup"><span data-stu-id="a3eee-214">Version</span></span>|<span data-ttu-id="a3eee-215">Valore minimo del valore DWORD Release</span><span class="sxs-lookup"><span data-stu-id="a3eee-215">Minimum value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="a3eee-216">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a3eee-216">.NET Framework 4.5</span></span>|<span data-ttu-id="a3eee-217">378389</span><span class="sxs-lookup"><span data-stu-id="a3eee-217">378389</span></span>|
    |<span data-ttu-id="a3eee-218">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="a3eee-218">.NET Framework 4.5.1</span></span>|<span data-ttu-id="a3eee-219">378675</span><span class="sxs-lookup"><span data-stu-id="a3eee-219">378675</span></span>|
    |<span data-ttu-id="a3eee-220">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a3eee-220">.NET Framework 4.5.2</span></span>|<span data-ttu-id="a3eee-221">379893</span><span class="sxs-lookup"><span data-stu-id="a3eee-221">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|<span data-ttu-id="a3eee-222">393295</span><span class="sxs-lookup"><span data-stu-id="a3eee-222">393295</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|<span data-ttu-id="a3eee-223">394254</span><span class="sxs-lookup"><span data-stu-id="a3eee-223">394254</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|<span data-ttu-id="a3eee-224">394802</span><span class="sxs-lookup"><span data-stu-id="a3eee-224">394802</span></span>|
    |<span data-ttu-id="a3eee-225">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="a3eee-225">.NET Framework 4.7</span></span>|<span data-ttu-id="a3eee-226">460798</span><span class="sxs-lookup"><span data-stu-id="a3eee-226">460798</span></span>|
    |<span data-ttu-id="a3eee-227">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a3eee-227">.NET Framework 4.7.1</span></span>|<span data-ttu-id="a3eee-228">461308</span><span class="sxs-lookup"><span data-stu-id="a3eee-228">461308</span></span>|
    
<a name="clr_a"></a> 
## <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="a3eee-229">Per trovare la versione corrente del runtime con lo strumento Clrver</span><span class="sxs-lookup"><span data-stu-id="a3eee-229">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="a3eee-230">Usare lo strumento CLR Version (Clrver.exe) per determinare le versioni di Common Language Runtime installate in un computer.</span><span class="sxs-lookup"><span data-stu-id="a3eee-230">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="a3eee-231">Al prompt dei comandi di Visual Studio immettere `clrver`.</span><span class="sxs-lookup"><span data-stu-id="a3eee-231">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="a3eee-232">Questo comando consente di generare un output analogo a quello illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a3eee-232">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="a3eee-233">Per altre informazioni sull'uso di questo strumento, vedere [Clrver.exe (strumento della versione CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a3eee-233">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="a3eee-234">Per trovare la versione corrente del runtime eseguendo una query sulla classe Environment nel codice</span><span class="sxs-lookup"><span data-stu-id="a3eee-234">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="a3eee-235">Eseguire una query sulla proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version> che identifica la versione del runtime che esegue attualmente il codice.</span><span class="sxs-lookup"><span data-stu-id="a3eee-235">Query the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="a3eee-236">È possibile usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType> per ottenere l'identificatore della versione principale (ad esempio "4" per la versione 4.0), la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType> per ottenere l'identificatore della versione secondaria (ad esempio "0" per la versione 4.0) oppure il metodo <xref:System.Object.ToString%2A?displayProperty=nameWithType> per ottenere l'intera stringa di versione (ad esempio "4.0.30319.18010", come illustrato nel seguente codice).</span><span class="sxs-lookup"><span data-stu-id="a3eee-236">You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="a3eee-237">Questa proprietà restituisce un valore singolo che corrisponde alla versione del runtime che esegue attualmente il codice; non restituisce le versioni di assembly o altre versioni del runtime che possono essere installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="a3eee-237">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="a3eee-238">Per le versioni 4, 4.5, 4.5.1 e 4.5.2 di .NET Framework, la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> restituisce un oggetto <xref:System.Version> la cui rappresentazione di stringa ha il formato `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="a3eee-238">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="a3eee-239">In .NET Framework 4.6 e versioni successive, ha il formato `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="a3eee-239">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a3eee-240">Per [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e versioni successive, è consigliabile usare la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per rilevare la versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="a3eee-240">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="a3eee-241">Si consiglia invece di eseguire una query sul Registro di sistema, come descritto nella sezione [Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 4.5 e versioni successive)](#net_d) riportata in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a3eee-241">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="a3eee-242">Di seguito è illustrato un esempio di esecuzione di query sulla proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per informazioni sulla versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="a3eee-242">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property for runtime version information:</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     <span data-ttu-id="a3eee-243">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3eee-243">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="a3eee-244">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3eee-244">See also</span></span>

[<span data-ttu-id="a3eee-245">Procedura: Determinare gli aggiornamenti di .NET Framework installati</span><span class="sxs-lookup"><span data-stu-id="a3eee-245">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
[<span data-ttu-id="a3eee-246">Installare .NET Framework per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="a3eee-246">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="a3eee-247">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="a3eee-247">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)  
