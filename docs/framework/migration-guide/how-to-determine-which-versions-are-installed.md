---
title: 'Procedura: Determinare le versioni di .NET Framework installate'
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
caps.latest.revision: 62
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cddee407d1245568054871d71f2840f463859535
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="1d7ea-102">Procedura: determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="1d7ea-102">How to: Determine Which .NET Framework Versions Are Installed</span></span>
<span data-ttu-id="1d7ea-103">Gli utenti possono installare ed eseguire nel computer più versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="1d7ea-104">Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="1d7ea-105">Si noti che .NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="1d7ea-106">Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="1d7ea-107">.NET Framework e gli assembly condividono lo stesso numero di versione.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="1d7ea-108">Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app</span><span class="sxs-lookup"><span data-stu-id="1d7ea-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="1d7ea-109">e che viene identificato dal relativo numero di versione (vedere [Versioni e dipendenze](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="1d7ea-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="1d7ea-110">Per ottenere un elenco accurato delle versioni di .NET Framework installate in un computer, è possibile visualizzare il Registro di sistema o eseguire query sul Registro di sistema nel codice:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="1d7ea-111">Visualizzazione del Registro di sistema (versioni 1-4)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="1d7ea-112">Visualizzazione del Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="1d7ea-113">Uso del codice per eseguire query sul Registro di sistema (versioni 1-4)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="1d7ea-114">Uso del codice per eseguire query sul Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
  
 <span data-ttu-id="1d7ea-115">Per trovare la versione di CLR, è possibile usare uno strumento o il codice:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-115">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="1d7ea-116">Uso dello strumento Clrver</span><span class="sxs-lookup"><span data-stu-id="1d7ea-116">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="1d7ea-117">Uso del codice per eseguire query sulla classe System.Environment</span><span class="sxs-lookup"><span data-stu-id="1d7ea-117">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="1d7ea-118">Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: determinare gli aggiornamenti di .NET Framework installati](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="1d7ea-118">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="1d7ea-119">Per informazioni sull'installazione di .NET Framework, vedere [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="1d7ea-119">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="1d7ea-120">Per trovare le versioni di .NET Framework visualizzando il Registro di sistema (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-120">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="1d7ea-121">Scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-121">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="1d7ea-122">Nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-122">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="1d7ea-123">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-123">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="1d7ea-124">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-124">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="1d7ea-125">Le versioni installate sono elencate nella sottochiave NDP.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-125">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="1d7ea-126">Il numero di versione è archiviato nella voce **Version**.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-126">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="1d7ea-127">Per [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la voce **Version** è inclusa nella sottochiave Client o Full (in NDP) o in entrambe.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-127">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="1d7ea-128">La cartella "NET Framework Setup" nel Registro di sistema non inizia con un punto.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-128">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="1d7ea-129">Per trovare le versioni di .NET Framework visualizzando il Registro di sistema (.NET Framework 4.5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-129">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="1d7ea-130">Scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-130">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="1d7ea-131">Nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-131">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="1d7ea-132">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-132">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="1d7ea-133">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-133">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="1d7ea-134">Si noti che il percorso della sottochiave `Full` include la sottochiave `Net Framework` e non `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-134">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d7ea-135">Se la sottochiave `Full` non è presente, .NET Framework 4.5 o versione successiva non è installato.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-135">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="1d7ea-136">Verificare la presenza di un valore DWORD denominato `Release`.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-136">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="1d7ea-137">L'esistenza del valore DWORD `Release` indica che nel computer è stato installato [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-137">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="1d7ea-138">![Voce del Registro di sistema per .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="1d7ea-138">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="1d7ea-139">Il valore DWORD `Release` indica quale versione di .NET Framework è installata.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-139">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    |<span data-ttu-id="1d7ea-140">Valore DWORD di Release</span><span class="sxs-lookup"><span data-stu-id="1d7ea-140">Value of the Release DWORD</span></span>|<span data-ttu-id="1d7ea-141">Versione</span><span class="sxs-lookup"><span data-stu-id="1d7ea-141">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="1d7ea-142">378389</span><span class="sxs-lookup"><span data-stu-id="1d7ea-142">378389</span></span>|<span data-ttu-id="1d7ea-143">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1d7ea-143">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="1d7ea-144">378675</span><span class="sxs-lookup"><span data-stu-id="1d7ea-144">378675</span></span>|<span data-ttu-id="1d7ea-145">.NET Framework 4.5.1 installato con Windows 8.1 o Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1d7ea-145">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="1d7ea-146">378758</span><span class="sxs-lookup"><span data-stu-id="1d7ea-146">378758</span></span>|<span data-ttu-id="1d7ea-147">.NET Framework 4.5.1 installato in Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="1d7ea-147">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="1d7ea-148">379893</span><span class="sxs-lookup"><span data-stu-id="1d7ea-148">379893</span></span>|<span data-ttu-id="1d7ea-149">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="1d7ea-149">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="1d7ea-150">Nei sistemi Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="1d7ea-150">On Windows 10 systems: 393295</span></span><br /><br /> <span data-ttu-id="1d7ea-151">In tutte le altre versioni del sistema operativo: 393297</span><span class="sxs-lookup"><span data-stu-id="1d7ea-151">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="1d7ea-152">Nei sistemi Windows 10 con aggiornamento di novembre: 394254</span><span class="sxs-lookup"><span data-stu-id="1d7ea-152">On Windows 10 November Update systems: 394254</span></span><br /><br /> <span data-ttu-id="1d7ea-153">In tutte le altre versioni del sistema operativo: 394271</span><span class="sxs-lookup"><span data-stu-id="1d7ea-153">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="1d7ea-154">Nell'Aggiornamento dell'anniversario di Windows 10: 394802</span><span class="sxs-lookup"><span data-stu-id="1d7ea-154">On Windows 10 Anniversary Update: 394802</span></span><br /><br /> <span data-ttu-id="1d7ea-155">In tutte le altre versioni del sistema operativo: 394806</span><span class="sxs-lookup"><span data-stu-id="1d7ea-155">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="1d7ea-156">In Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="1d7ea-156">On Windows 10 Creators Update: 460798</span></span><br/><br/> <span data-ttu-id="1d7ea-157">In tutte le altre versioni del sistema operativo: 460805</span><span class="sxs-lookup"><span data-stu-id="1d7ea-157">On all other OS versions: 460805</span></span> | <span data-ttu-id="1d7ea-158">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="1d7ea-158">.NET Framework 4.7</span></span> |

<a name="net_c"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="1d7ea-159">Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-159">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="1d7ea-160">Usare la classe <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> per accedere alla sottochiave Software\Microsoft\NET Framework Setup\NDP in HKEY_LOCAL_MACHINE nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-160">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="1d7ea-161">Nel codice seguente viene illustrato un esempio di questa query.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-161">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d7ea-162">Questo codice non mostra come rilevare [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-162">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="1d7ea-163">Controllare il valore DWORD `Release` per rilevare tali versioni, come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-163">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="1d7ea-164">Per il codice che rileva [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versioni successive, vedere la sezione successiva in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-164">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     <span data-ttu-id="1d7ea-165">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1d7ea-165">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]</span></span>

     <span data-ttu-id="1d7ea-166">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-166">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="1d7ea-167">Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 4.5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-167">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="1d7ea-168">L'esistenza del valore DWORD `Release` indica che nel computer è stato installato .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-168">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="1d7ea-169">Il valore di questa parola chiave indica la versione installata.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-169">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="1d7ea-170">Per controllare questa parola chiave, usare i metodi <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> e <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> della classe <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> per accedere alla sottochiave Software\Microsoft\NET Framework Setup\NDP\v4\Full in HKEY_LOCAL_MACHINE nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-170">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="1d7ea-171">Verificare il valore della parola chiave `Release` per determinare la versione installata.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-171">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="1d7ea-172">Affinché sia compatibile con la versione attualmente installata, è possibile cercare un valore maggiore o uguale ai valori elencati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-172">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="1d7ea-173">Ecco le versioni di .NET Framework e le parole chiave `Release` associate.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-173">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    |<span data-ttu-id="1d7ea-174">Versione</span><span class="sxs-lookup"><span data-stu-id="1d7ea-174">Version</span></span>|<span data-ttu-id="1d7ea-175">Valore DWORD di Release</span><span class="sxs-lookup"><span data-stu-id="1d7ea-175">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="1d7ea-176">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1d7ea-176">.NET Framework 4.5</span></span>|<span data-ttu-id="1d7ea-177">378389</span><span class="sxs-lookup"><span data-stu-id="1d7ea-177">378389</span></span>|
    |<span data-ttu-id="1d7ea-178">.NET Framework 4.5.1 installato con Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1d7ea-178">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="1d7ea-179">378675</span><span class="sxs-lookup"><span data-stu-id="1d7ea-179">378675</span></span>|
    |<span data-ttu-id="1d7ea-180">.NET Framework 4.5.1 installato in Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="1d7ea-180">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="1d7ea-181">378758</span><span class="sxs-lookup"><span data-stu-id="1d7ea-181">378758</span></span>|
    |<span data-ttu-id="1d7ea-182">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="1d7ea-182">.NET Framework 4.5.2</span></span>|<span data-ttu-id="1d7ea-183">379893</span><span class="sxs-lookup"><span data-stu-id="1d7ea-183">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<span data-ttu-id="1d7ea-184"> installato con Windows 10</span><span class="sxs-lookup"><span data-stu-id="1d7ea-184"> installed with Windows 10</span></span>|<span data-ttu-id="1d7ea-185">393295</span><span class="sxs-lookup"><span data-stu-id="1d7ea-185">393295</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<span data-ttu-id="1d7ea-186"> installato in tutte le altre versioni del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="1d7ea-186"> installed on all other Windows OS versions</span></span>|<span data-ttu-id="1d7ea-187">393297</span><span class="sxs-lookup"><span data-stu-id="1d7ea-187">393297</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<span data-ttu-id="1d7ea-188"> installato in Windows 10</span><span class="sxs-lookup"><span data-stu-id="1d7ea-188"> installed on Windows 10</span></span>|<span data-ttu-id="1d7ea-189">394254</span><span class="sxs-lookup"><span data-stu-id="1d7ea-189">394254</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<span data-ttu-id="1d7ea-190"> installato in tutte le altre versioni del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="1d7ea-190"> installed on all other Windows OS versions</span></span>|<span data-ttu-id="1d7ea-191">394271</span><span class="sxs-lookup"><span data-stu-id="1d7ea-191">394271</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<span data-ttu-id="1d7ea-192"> installato nell'Aggiornamento dell'anniversario di Windows 10</span><span class="sxs-lookup"><span data-stu-id="1d7ea-192"> installed on Windows 10 Anniversary Update</span></span>|<span data-ttu-id="1d7ea-193">394802</span><span class="sxs-lookup"><span data-stu-id="1d7ea-193">394802</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<span data-ttu-id="1d7ea-194"> installato in tutte le altre versioni del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="1d7ea-194"> installed on all other Windows OS versions</span></span>|<span data-ttu-id="1d7ea-195">394806</span><span class="sxs-lookup"><span data-stu-id="1d7ea-195">394806</span></span>|
    |<span data-ttu-id="1d7ea-196">.NET Framework 4.7 installato in Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="1d7ea-196">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="1d7ea-197">460798</span><span class="sxs-lookup"><span data-stu-id="1d7ea-197">460798</span></span>|
    |<span data-ttu-id="1d7ea-198">.NET Framework 4.7 installato in tutte le altre versioni del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="1d7ea-198">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="1d7ea-199">460805</span><span class="sxs-lookup"><span data-stu-id="1d7ea-199">460805</span></span>|

     <span data-ttu-id="1d7ea-200">Nell'esempio seguente viene controllato il valore `Release` del Registro di sistema per determinare se è installato [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versione successiva di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-200">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     <span data-ttu-id="1d7ea-201">[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]   [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]</span><span class="sxs-lookup"><span data-stu-id="1d7ea-201">[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]   [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]</span></span>

     <span data-ttu-id="1d7ea-202">Questo esempio segue la procedura consigliata per il controllo della versione:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-202">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="1d7ea-203">Controlla se il valore della voce `Release` è *maggiore o uguale* al valore delle parole chiave Release note.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-203">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="1d7ea-204">Controlla in ordine dalla versione più recente a quella meno recente.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-204">It checks in order from most recent version to earliest version.</span></span>

<a name="clr_a"></a> 
#### <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="1d7ea-205">Per trovare la versione corrente del runtime con lo strumento Clrver</span><span class="sxs-lookup"><span data-stu-id="1d7ea-205">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="1d7ea-206">Usare lo strumento CLR Version (Clrver.exe) per determinare le versioni di Common Language Runtime installate in un computer.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-206">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="1d7ea-207">Al prompt dei comandi di Visual Studio immettere `clrver`.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-207">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="1d7ea-208">Questo comando consente di generare un output analogo a quello illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-208">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="1d7ea-209">Per altre informazioni sull'uso di questo strumento, vedere [Clrver.exe (strumento della versione CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="1d7ea-209">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
#### <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="1d7ea-210">Per trovare la versione corrente del runtime eseguendo una query sulla classe Environment nel codice</span><span class="sxs-lookup"><span data-stu-id="1d7ea-210">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="1d7ea-211">Eseguire una query sulla proprietà <xref:System.Environment.Version%2A?displayProperty=fullName> per recuperare un oggetto <xref:System.Version> che identifica la versione del runtime che esegue attualmente il codice.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-211">Query the <xref:System.Environment.Version%2A?displayProperty=fullName> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="1d7ea-212">È possibile usare la proprietà <xref:System.Version.Major%2A?displayProperty=fullName> per ottenere l'identificatore della versione principale (ad esempio "4" per la versione 4.0), la proprietà <xref:System.Version.Minor%2A?displayProperty=fullName> per ottenere l'identificatore della versione secondaria (ad esempio "0" per la versione 4.0) oppure il metodo <xref:System.Object.ToString%2A?displayProperty=fullName> per ottenere l'intera stringa di versione (ad esempio "4.0.30319.18010", come illustrato nel seguente codice).</span><span class="sxs-lookup"><span data-stu-id="1d7ea-212">You can use the <xref:System.Version.Major%2A?displayProperty=fullName> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=fullName> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=fullName> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="1d7ea-213">Questa proprietà restituisce un valore singolo che corrisponde alla versione del runtime che esegue attualmente il codice; non restituisce le versioni di assembly o altre versioni del runtime che possono essere installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-213">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="1d7ea-214">Per le versioni 4, 4.5, 4.5.1 e 4.5.2 di .NET Framework, la proprietà <xref:System.Environment.Version%2A?displayProperty=fullName> restituisce un oggetto <xref:System.Version> la cui rappresentazione di stringa ha il formato `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-214">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=fullName> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="1d7ea-215">In .NET Framework 4.6 e versioni successive, ha il formato `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-215">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1d7ea-216">Per [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e versioni successive, è consigliabile usare la proprietà <xref:System.Environment.Version%2A?displayProperty=fullName> per rilevare la versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-216">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=fullName> property to detect the version of the runtime.</span></span> <span data-ttu-id="1d7ea-217">Si consiglia invece di eseguire una query sul Registro di sistema, come descritto nella sezione [Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 4.5 e versioni successive)](#net_d) riportata in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-217">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="1d7ea-218">Di seguito è illustrato un esempio di esecuzione di query sulla proprietà <xref:System.Environment.Version%2A?displayProperty=fullName> per informazioni sulla versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="1d7ea-218">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=fullName> property for runtime version information:</span></span>

     <span data-ttu-id="1d7ea-219">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1d7ea-219">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]</span></span>

     <span data-ttu-id="1d7ea-220">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1d7ea-220">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="1d7ea-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d7ea-221">See Also</span></span>
 <span data-ttu-id="1d7ea-222">[Procedura: determinare gli aggiornamenti di .NET Framework installati](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="1d7ea-222">[How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md) </span></span>  
 <span data-ttu-id="1d7ea-223">[Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md)  (Installare .NET Framework per sviluppatori)</span><span class="sxs-lookup"><span data-stu-id="1d7ea-223">[Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) </span></span>  
 [<span data-ttu-id="1d7ea-224">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="1d7ea-224">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)

