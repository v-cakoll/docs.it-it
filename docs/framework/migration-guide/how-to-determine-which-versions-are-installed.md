---
title: 'Procedura: Determinare le versioni di .NET Framework installate'
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584174"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="c9a89-102">Procedura: Determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="c9a89-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="c9a89-103">Gli utenti possono installare ed eseguire nel computer più versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9a89-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="c9a89-104">Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c9a89-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="c9a89-105">Si noti che .NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:</span><span class="sxs-lookup"><span data-stu-id="c9a89-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="c9a89-106">Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app.</span><span class="sxs-lookup"><span data-stu-id="c9a89-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="c9a89-107">.NET Framework e gli assembly condividono lo stesso numero di versione.</span><span class="sxs-lookup"><span data-stu-id="c9a89-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="c9a89-108">Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app</span><span class="sxs-lookup"><span data-stu-id="c9a89-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="c9a89-109">e che viene identificato dal relativo numero di versione (vedere [Versioni e dipendenze](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="c9a89-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
<span data-ttu-id="c9a89-110">Per ottenere un elenco accurato delle versioni di .NET Framework installate in un computer, è possibile visualizzare il Registro di sistema o eseguire query sul Registro di sistema nel codice:</span><span class="sxs-lookup"><span data-stu-id="c9a89-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="c9a89-111">Trovare le versioni di .NET Framework 1-4 nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c9a89-111">Find .NET Framework versions 1-4 in the registry</span></span>](#net_a)  
 [<span data-ttu-id="c9a89-112">Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c9a89-112">Find .NET Framework versions 4.5 and later in the registry)</span></span>](#net_b)  
 [<span data-ttu-id="c9a89-113">Uso del codice per eseguire query sul Registro di sistema (versioni 1-4)</span><span class="sxs-lookup"><span data-stu-id="c9a89-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="c9a89-114">Uso del codice per eseguire query sul Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="c9a89-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="c9a89-115">Uso di PowerShell per eseguire query sul Registro di sistema (versione 4.5 e successive)</span><span class="sxs-lookup"><span data-stu-id="c9a89-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  

 <span data-ttu-id="c9a89-116">Per trovare la versione di CLR, è possibile usare uno strumento o il codice:</span><span class="sxs-lookup"><span data-stu-id="c9a89-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="c9a89-117">Uso dello strumento Clrver</span><span class="sxs-lookup"><span data-stu-id="c9a89-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="c9a89-118">Uso del codice per eseguire query sulla classe System.Environment</span><span class="sxs-lookup"><span data-stu-id="c9a89-118">Using code to query the System.Environment class</span></span>](#clr_b)  

> [!NOTE]
> <span data-ttu-id="c9a89-119">Esiste una differenza tra la versione di .NET Framework e la versione di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c9a89-119">There is a difference between the .NET Framework version and the common language runtime (CLR) version.</span></span> <span data-ttu-id="c9a89-120">Le versioni di .NET Framework sono basate sul set di assembly che costituiscono la libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9a89-120">The .NET Framework is versioned based on the set of assemblies that form the .NET Framework Class Library.</span></span> <span data-ttu-id="c9a89-121">Ad esempio, le versioni di .NET Framework includono 4.5, 4.6.1 e 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="c9a89-121">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> <span data-ttu-id="c9a89-122">Le versioni di CLR sono basate sul runtime in cui vengono eseguite le applicazioni di .NET Framework e una singola versione di CLR supporta in genere più versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9a89-122">The CLR is versioned based on the runtime on which .NET Framework applications execute, and a single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="c9a89-123">La versione di CLR 4.30319.*xxxxx* supporta le versioni di .NET Framework da 4 a 4.5.2. La versione di CLR 4.30319.42000 supporta le versioni di .NET Framework a partire da .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="c9a89-123">CLR version 4.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2; CLR version 4.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> <span data-ttu-id="c9a89-124">Per altre informazioni, vedere la proprietà <xref:System.Environment.Version?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c9a89-124">For more information, see the <xref:System.Environment.Version?displayProperty=nameWithType> property.</span></span>

 <span data-ttu-id="c9a89-125">Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: Determinare gli aggiornamenti di .NET Framework installati](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="c9a89-125">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="c9a89-126">Per informazioni sull'installazione di .NET Framework, vedere [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="c9a89-126">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a><span data-ttu-id="c9a89-127">Trovare le versioni di .NET Framework 1-4 nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c9a89-127">Find .NET Framework versions 1-4 in the registry</span></span> 
  
1.  <span data-ttu-id="c9a89-128">Scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="c9a89-128">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="c9a89-129">Nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="c9a89-129">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="c9a89-130">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="c9a89-130">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="c9a89-131">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="c9a89-131">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="c9a89-132">Per le versioni di .NET Framework da 1.1 a 3.5, le versioni installate sono elencate come sottochiavi della sottochiave `NDP`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-132">For .NET Framework versions 1.1 through 3.5, the installed versions are listed as subkeys under the `NDP` subkey.</span></span> <span data-ttu-id="c9a89-133">Il numero di versione è archiviato nella voce **Version** della sottochiave della versione.</span><span class="sxs-lookup"><span data-stu-id="c9a89-133">The version number is stored in the version subkey's **Version** entry.</span></span> 
     
     <span data-ttu-id="c9a89-134">Per .NET Framework 4, la voce **Version** è nella sottochiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client`, nella sottochiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` o in entrambe.</span><span class="sxs-lookup"><span data-stu-id="c9a89-134">For .NET Framework 4, the **Version** entry is under the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` subkey, the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9a89-135">La cartella "NET Framework Setup" nel Registro di sistema non inizia con un punto.</span><span class="sxs-lookup"><span data-stu-id="c9a89-135">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="c9a89-136">La figura seguente mostra la sottochiave per .NET Framework 3.5 con la relativa voce **Version**.</span><span class="sxs-lookup"><span data-stu-id="c9a89-136">The following figure shows that the subkey for the .NET Framework 3.5 along with its **Version** entry.</span></span>

     <span data-ttu-id="c9a89-137">![Voce del Registro di sistema per .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET framework 4 e versioni precedenti")</span><span class="sxs-lookup"><span data-stu-id="c9a89-137">![The registry entry for the .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 and earlier versions")</span></span>

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="c9a89-138">Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c9a89-138">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="c9a89-139">Scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="c9a89-139">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="c9a89-140">Nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="c9a89-140">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="c9a89-141">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="c9a89-141">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="c9a89-142">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="c9a89-142">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="c9a89-143">Si noti che il percorso della sottochiave `Full` include la sottochiave `Net Framework` e non `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-143">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9a89-144">Se la sottochiave `Full` non è presente, .NET Framework 4.5 o versione successiva non è installato.</span><span class="sxs-lookup"><span data-stu-id="c9a89-144">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="c9a89-145">Verificare la presenza di un valore DWORD denominato `Release`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-145">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="c9a89-146">L'esistenza del valore DWORD `Release` indica che nel computer è stato installato .NET Framework 4.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c9a89-146">The existence of the `Release` DWORD indicates that .NET Framework 4.5 or later has been installed on that computer.</span></span> <span data-ttu-id="c9a89-147">Il valore è una chiave di rilascio che corrisponde a una particolare versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9a89-147">Its value is a release key that corresponds to a particular version of .NET Framework.</span></span> <span data-ttu-id="c9a89-148">Nella figura seguente, ad esempio, il valore DWORD `Release` è 378389, ovvero la chiave di rilascio per .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="c9a89-148">In the following figure, for example, the value of the `Release` DWORD is 378389, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="c9a89-149">![Voce del Registro di sistema per .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="c9a89-149">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

<span data-ttu-id="c9a89-150">La tabella seguente elenca il valore minimo DWORD `Release` per ogni versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9a89-150">The following table lists the minimum value of the `Release` DWORD for each .NET Framework version.</span></span> <span data-ttu-id="c9a89-151">È possibile usare questi valori come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c9a89-151">You can use these values as follows:</span></span>

- <span data-ttu-id="c9a89-152">Per determinare se è presente una versione minima di .NET Framework, verificare se il valore DWORD `Release` trovato nel Registro di sistema è *maggiore o uguale* al valore elencato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="c9a89-152">To determine whether a minimum .NET Framework version is present, test whether the `Release` DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="c9a89-153">Ad esempio, se l'applicazione richiede .NET Framework 4.7 o versioni successive, eseguire un test per il valore minimo della chiave di rilascio 460798.</span><span class="sxs-lookup"><span data-stu-id="c9a89-153">For example, if your application requires .NET Framework 4.7 or later, you would test for a minimum release key value of 460798.</span></span>

- <span data-ttu-id="c9a89-154">Per eseguire il test per più versioni, iniziare con la versione più recente di .NET Framework e quindi ripetere il test per ogni versione precedente successiva.</span><span class="sxs-lookup"><span data-stu-id="c9a89-154">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|<span data-ttu-id="c9a89-155">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c9a89-155">.NET Framework Version</span></span>|<span data-ttu-id="c9a89-156">Valore DWORD di Release</span><span class="sxs-lookup"><span data-stu-id="c9a89-156">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="c9a89-157">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c9a89-157">.NET Framework 4.5</span></span>|<span data-ttu-id="c9a89-158">378389</span><span class="sxs-lookup"><span data-stu-id="c9a89-158">378389</span></span>|
|<span data-ttu-id="c9a89-159">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="c9a89-159">.NET Framework 4.5.1</span></span>|<span data-ttu-id="c9a89-160">378675</span><span class="sxs-lookup"><span data-stu-id="c9a89-160">378675</span></span>|
|<span data-ttu-id="c9a89-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="c9a89-161">.NET Framework 4.5.2</span></span>|<span data-ttu-id="c9a89-162">379893</span><span class="sxs-lookup"><span data-stu-id="c9a89-162">379893</span></span>|
|<span data-ttu-id="c9a89-163">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="c9a89-163">.NET Framework 4.6</span></span>|<span data-ttu-id="c9a89-164">393295</span><span class="sxs-lookup"><span data-stu-id="c9a89-164">393295</span></span>|
|<span data-ttu-id="c9a89-165">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="c9a89-165">.NET Framework 4.6.1</span></span>|<span data-ttu-id="c9a89-166">394254</span><span class="sxs-lookup"><span data-stu-id="c9a89-166">394254</span></span>|
|<span data-ttu-id="c9a89-167">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c9a89-167">.NET Framework 4.6.2</span></span>|<span data-ttu-id="c9a89-168">394802</span><span class="sxs-lookup"><span data-stu-id="c9a89-168">394802</span></span>|
|<span data-ttu-id="c9a89-169">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="c9a89-169">.NET Framework 4.7</span></span>|<span data-ttu-id="c9a89-170">460798</span><span class="sxs-lookup"><span data-stu-id="c9a89-170">460798</span></span>|
|<span data-ttu-id="c9a89-171">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="c9a89-171">.NET Framework 4.7.1</span></span>|<span data-ttu-id="c9a89-172">461308</span><span class="sxs-lookup"><span data-stu-id="c9a89-172">461308</span></span>|
|<span data-ttu-id="c9a89-173">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="c9a89-173">.NET Framework 4.7.2</span></span>|<span data-ttu-id="c9a89-174">461808</span><span class="sxs-lookup"><span data-stu-id="c9a89-174">461808</span></span>|

<span data-ttu-id="c9a89-175">Per una tabella completa delle chiavi di rilascio per .NET Framework per versioni specifiche del sistema operativo Windows, vedere [Chiavi di rilascio di .NET Framework e versioni del sistema operativo Windows](release-keys-and-os-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c9a89-175">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a><span data-ttu-id="c9a89-176">Trovare le versioni di .NET Framework 1-4 tramite codice</span><span class="sxs-lookup"><span data-stu-id="c9a89-176">Find .NET Framework versions 1-4 with code</span></span>

- <span data-ttu-id="c9a89-177">Usare la classe <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> per accedere alla sottochiave `Software\Microsoft\NET Framework Setup\NDP\` nel ramo `HKEY_LOCAL_MACHINE` nel Registro di sistema Windows.</span><span class="sxs-lookup"><span data-stu-id="c9a89-177">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the `Software\Microsoft\NET Framework Setup\NDP\` subkey under `HKEY_LOCAL_MACHINE` branch in the Windows registry.</span></span>

     <span data-ttu-id="c9a89-178">Nel codice seguente viene illustrato un esempio di questa query.</span><span class="sxs-lookup"><span data-stu-id="c9a89-178">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9a89-179">Questo codice non mostra come rilevare .NET Framework 4.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c9a89-179">This code does not show how to detect .NET Framework 4.5 or later.</span></span> <span data-ttu-id="c9a89-180">Controllare il valore DWORD `Release` per rilevare tali versioni, come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="c9a89-180">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="c9a89-181">Per il codice che rileva .NET Framework 4.5 o versioni successive, vedere la sezione successiva in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c9a89-181">For code that detects .NET Framework 4.5 or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="c9a89-182">Trovare le versioni di .NET Framework 4.5 e successive tramite codice</span><span class="sxs-lookup"><span data-stu-id="c9a89-182">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="c9a89-183">L'esistenza del valore DWORD `Release` nella chiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` indica che nel computer è stato installato .NET Framework 4.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c9a89-183">The existence of the `Release` DWORD in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key indicates that the .NET Framework 4.5 or later is installed on a computer.</span></span> <span data-ttu-id="c9a89-184">Il valore di questa parola chiave indica la versione installata.</span><span class="sxs-lookup"><span data-stu-id="c9a89-184">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="c9a89-185">Per controllare questa parola chiave, usare i metodi <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> e <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> per accedere alla sottochiave nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="c9a89-185">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the subkey in the Windows registry.</span></span>

2. <span data-ttu-id="c9a89-186">Verificare il valore della parola chiave `Release` per determinare la versione installata.</span><span class="sxs-lookup"><span data-stu-id="c9a89-186">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="c9a89-187">Per essere compatibili con le versioni successive, è possibile cercare un valore maggiore o uguale di quello elencato nella tabella nella sezione [Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema](#net_b) sezione.</span><span class="sxs-lookup"><span data-stu-id="c9a89-187">To be forward-compatible, you can check for a value greater than or equal to the value listed in the table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section.</span></span>

<span data-ttu-id="c9a89-188">Nell'esempio seguente viene controllato il valore `Release` nel Registro di sistema per determinare se è installato .NET Framework 4.5 o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c9a89-188">The following example checks the `Release` value in the registry to determine whether .NET Framework 4.5 or a later version is installed.</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="c9a89-189">Questo esempio segue la procedura consigliata per il controllo della versione:</span><span class="sxs-lookup"><span data-stu-id="c9a89-189">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="c9a89-190">Controlla se il valore della voce `Release` è *maggiore o uguale* al valore delle parole chiave Release note.</span><span class="sxs-lookup"><span data-stu-id="c9a89-190">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="c9a89-191">Controlla in ordine dalla versione più recente a quella meno recente.</span><span class="sxs-lookup"><span data-stu-id="c9a89-191">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="c9a89-192">Controllare la presenza di una versione minima richiesta di .NET Framework (4.5 e versioni successive) con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9a89-192">Check for a minimum required .NET Framework version (4.5 and later) with PowerShell</span></span>

<span data-ttu-id="c9a89-193">Nell'esempio seguente viene controllato il valore della parola chiave `Release` per determinare se è installato .NET Framework 4.6.2 o versione successiva (viene restituito `True` in caso di esito positivo e `False` in caso contrario).</span><span class="sxs-lookup"><span data-stu-id="c9a89-193">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="c9a89-194">Trovare la versione corrente di CLR con Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="c9a89-194">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="c9a89-195">Usare lo strumento CLR Version (Clrver.exe) per determinare le versioni di Common Language Runtime installate in un computer.</span><span class="sxs-lookup"><span data-stu-id="c9a89-195">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

<span data-ttu-id="c9a89-196">Da un prompt dei comandi per gli sviluppatori per Visual Studio, immettere `clrver`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-196">From a Developer Command Prompt for Visual Studio, enter `clrver`.</span></span> <span data-ttu-id="c9a89-197">Questo comando consente di generare un output analogo a quello illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c9a89-197">This command produces output similar to the following:</span></span>

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

<span data-ttu-id="c9a89-198">Per altre informazioni sull'uso di questo strumento, vedere [Clrver.exe (strumento della versione CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="c9a89-198">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="c9a89-199">Trovare la versione corrente di CLR con la classe Environment</span><span class="sxs-lookup"><span data-stu-id="c9a89-199">Find the current CLR version with the Environment class</span></span>

<span data-ttu-id="c9a89-200">È possibile recuperare il valore della proprietà <xref:System.Environment.Version?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version> che identifica la versione del runtime che esegue attualmente il codice.</span><span class="sxs-lookup"><span data-stu-id="c9a89-200">You can retrieve the value of the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="c9a89-201">Questa proprietà restituisce un singolo valore che riflette la versione del runtime che esegue il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere state installate nel computer. È possibile usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType> per ottenere l'identificatore di versione principale (ad esempio, "4" per la versione 4.0), la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType> per ottenere l'identificatore della versione secondaria (ad esempio, "0" per la versione 4.0) oppure il metodo <xref:System.Version.ToString%2A?displayProperty=nameWithType> per ottenere l'intera stringa della versione (ad esempio "4.0.30319.18010", come illustrato nel codice seguente).</span><span class="sxs-lookup"><span data-stu-id="c9a89-201">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> 

<span data-ttu-id="c9a89-202">Per le versioni 4, 4.5, 4.5.1 e 4.5.2 di .NET Framework, la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> restituisce un oggetto <xref:System.Version> la cui rappresentazione di stringa ha il formato `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-202">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="c9a89-203">In .NET Framework 4.6 e versioni successive, ha il formato `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="c9a89-203">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9a89-204">Per .NET Framework 4.5 e versioni successive, non è consigliabile usare la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per rilevare la versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="c9a89-204">For the .NET Framework 4.5 and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="c9a89-205">Si consiglia invece di eseguire una query sul Registro di sistema, come descritto nella sezione [Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 4.5 e versioni successive)](#net_d) riportata in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c9a89-205">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

<span data-ttu-id="c9a89-206">Nell'esempio seguente viene usata la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare le informazioni sulla versione del runtime:</span><span class="sxs-lookup"><span data-stu-id="c9a89-206">The following example used the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve runtime version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="c9a89-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9a89-207">See also</span></span>

- [<span data-ttu-id="c9a89-208">Procedura: Determinare gli aggiornamenti di .NET Framework installati</span><span class="sxs-lookup"><span data-stu-id="c9a89-208">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="c9a89-209">Installare .NET Framework per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="c9a89-209">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="c9a89-210">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="c9a89-210">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)
