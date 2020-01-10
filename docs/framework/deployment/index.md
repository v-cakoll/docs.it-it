---
title: Distribuzione di .NET Framework e delle applicazioni
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: b1ba9810b4b0d5a1688318db1093a9ce9bdf8fda
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716469"
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="c34cc-102">Distribuzione di .NET Framework e delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="c34cc-102">Deploying the .NET Framework and Applications</span></span>

<span data-ttu-id="c34cc-103">Questo articolo consente di iniziare a distribuire .NET Framework con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-103">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="c34cc-104">La maggior parte delle informazioni, sono destinate agli sviluppatori OEM e agli amministratori aziendali.</span><span class="sxs-lookup"><span data-stu-id="c34cc-104">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="c34cc-105">È consigliabile che gli utenti che vogliono installare .NET Framework leggano [Installare .NET Framework](../install/index.md).</span><span class="sxs-lookup"><span data-stu-id="c34cc-105">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](../install/index.md).</span></span>

## <a name="key-deployment-resources"></a><span data-ttu-id="c34cc-106">Risorse principali di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c34cc-106">Key Deployment Resources</span></span>

<span data-ttu-id="c34cc-107">Usare i seguenti collegamenti ad altri argomenti di MSDN per informazioni specifiche sulla distribuzione e sui servizi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c34cc-107">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>

<span data-ttu-id="c34cc-108">**Installazione e distribuzione**</span><span class="sxs-lookup"><span data-stu-id="c34cc-108">**Setup and deployment**</span></span>

- <span data-ttu-id="c34cc-109">Installazione generica ed informazioni di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="c34cc-109">General installer and deployment information:</span></span>

  - <span data-ttu-id="c34cc-110">Opzioni del programma di installazione:</span><span class="sxs-lookup"><span data-stu-id="c34cc-110">Installer options:</span></span>

    - [<span data-ttu-id="c34cc-111">Web installer</span><span class="sxs-lookup"><span data-stu-id="c34cc-111">Web installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [<span data-ttu-id="c34cc-112">Offline installer</span><span class="sxs-lookup"><span data-stu-id="c34cc-112">Offline installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - <span data-ttu-id="c34cc-113">Modalità di installazione:</span><span class="sxs-lookup"><span data-stu-id="c34cc-113">Installation modes:</span></span>

    - [<span data-ttu-id="c34cc-114">Installazione invisibile all'utente</span><span class="sxs-lookup"><span data-stu-id="c34cc-114">Silent installation</span></span>](deployment-guide-for-developers.md#chaining_custom)

    - [<span data-ttu-id="c34cc-115">Visualizzazione di un'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c34cc-115">Displaying a UI</span></span>](deployment-guide-for-developers.md#chaining_default)

  - [<span data-ttu-id="c34cc-116">Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c34cc-116">Reducing system restarts during .NET Framework 4.5 installations</span></span>](reducing-system-restarts.md)

  - [<span data-ttu-id="c34cc-117">Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c34cc-117">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- <span data-ttu-id="c34cc-118">Distribuzione di .NET Framework in un'applicazione client (per gli sviluppatori):</span><span class="sxs-lookup"><span data-stu-id="c34cc-118">Deploying the .NET Framework with a client application (for developers):</span></span>

  - <span data-ttu-id="c34cc-119">[Uso di InstallShield](deployment-guide-for-developers.md#installshield-deployment) in un progetto di installazione e distribuzione</span><span class="sxs-lookup"><span data-stu-id="c34cc-119">[Using InstallShield](deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>

  - [<span data-ttu-id="c34cc-120">Uso di un'applicazione ClickOnce di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c34cc-120">Using a Visual Studio ClickOnce application</span></span>](deployment-guide-for-developers.md#clickonce-deployment)

  - [<span data-ttu-id="c34cc-121">Creazione di un pacchetto di installazione WiX</span><span class="sxs-lookup"><span data-stu-id="c34cc-121">Creating a WiX installation package</span></span>](deployment-guide-for-developers.md#wix)

  - [<span data-ttu-id="c34cc-122">Uso di un programma di installazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="c34cc-122">Using a custom installer</span></span>](deployment-guide-for-developers.md#chaining)

  - <span data-ttu-id="c34cc-123">[Altre informazioni](deployment-guide-for-developers.md) per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="c34cc-123">[Additional information](deployment-guide-for-developers.md) for developers</span></span>

- <span data-ttu-id="c34cc-124">Distribuzione di .NET Framework (per gli OEM e gli amministratori):</span><span class="sxs-lookup"><span data-stu-id="c34cc-124">Deploying the .NET Framework (for OEMs and administrators):</span></span>

  - [<span data-ttu-id="c34cc-125">Windows Assessment and Deployment Kit (ADK)</span><span class="sxs-lookup"><span data-stu-id="c34cc-125">Windows Assessment and Deployment Kit (ADK)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [<span data-ttu-id="c34cc-126">Guida dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="c34cc-126">Administrator's guide</span></span>](guide-for-administrators.md)

<span data-ttu-id="c34cc-127">**Manutenzione**</span><span class="sxs-lookup"><span data-stu-id="c34cc-127">**Servicing**</span></span>

- <span data-ttu-id="c34cc-128">Per informazioni generali, vedere il [blog .NET Framework](https://devblogs.microsoft.com/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="c34cc-128">For general information, see the [.NET Framework blog](https://devblogs.microsoft.com/dotnet/).</span></span>

- [<span data-ttu-id="c34cc-129">Determinazione delle versioni</span><span class="sxs-lookup"><span data-stu-id="c34cc-129">Detecting versions</span></span>](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [<span data-ttu-id="c34cc-130">Determinazione di service pack e aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="c34cc-130">Detecting service packs and updates</span></span>](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a><span data-ttu-id="c34cc-131">Funzionalità che semplificano la distribuzione</span><span class="sxs-lookup"><span data-stu-id="c34cc-131">Features That Simplify Deployment</span></span>

<span data-ttu-id="c34cc-132">In .NET Framework sono disponibili diverse funzionalità di base che semplificano la distribuzione delle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="c34cc-132">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>

- <span data-ttu-id="c34cc-133">Indipendenza delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c34cc-133">No-impact applications.</span></span>

     <span data-ttu-id="c34cc-134">Questa funzionalità fornisce l'isolamento delle applicazioni ed elimina i conflitti di DLL.</span><span class="sxs-lookup"><span data-stu-id="c34cc-134">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="c34cc-135">Per impostazione predefinita i componenti di un'applicazione non influenzano il funzionamento di altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c34cc-135">By default, components do not affect other applications.</span></span>

- <span data-ttu-id="c34cc-136">Componenti privati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c34cc-136">Private components by default.</span></span>

     <span data-ttu-id="c34cc-137">Per impostazione predefinita, i componenti vengono distribuiti nella directory dell'applicazione e sono visibili solo a tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-137">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>

- <span data-ttu-id="c34cc-138">Condivisione controllata del codice.</span><span class="sxs-lookup"><span data-stu-id="c34cc-138">Controlled code sharing.</span></span>

     <span data-ttu-id="c34cc-139">La condivisione del codice richiede che il codice venga reso disponibile per la condivisione in modo esplicito, in quanto non è condiviso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c34cc-139">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>

- <span data-ttu-id="c34cc-140">Controllo delle versioni side-by-side.</span><span class="sxs-lookup"><span data-stu-id="c34cc-140">Side-by-side versioning.</span></span>

     <span data-ttu-id="c34cc-141">È possibile creare più versioni di un componente o di un'applicazione e specificare la versione da usare. I criteri di gestione delle versioni sono attivati da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c34cc-141">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>

- <span data-ttu-id="c34cc-142">Distribuzione e replica XCOPY.</span><span class="sxs-lookup"><span data-stu-id="c34cc-142">XCOPY deployment and replication.</span></span>

     <span data-ttu-id="c34cc-143">È possibile distribuire applicazioni e componenti autodescrittivi e indipendenti senza voci del Registro di sistema o dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c34cc-143">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>

- <span data-ttu-id="c34cc-144">Aggiornamenti al volo.</span><span class="sxs-lookup"><span data-stu-id="c34cc-144">On-the-fly updates.</span></span>

     <span data-ttu-id="c34cc-145">Gli amministratori possono aggiornare le DLL dei programmi usando host, ad esempio ASP.NET, anche su computer remoti.</span><span class="sxs-lookup"><span data-stu-id="c34cc-145">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>

- <span data-ttu-id="c34cc-146">Integrazione con Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="c34cc-146">Integration with the Windows Installer.</span></span>

     <span data-ttu-id="c34cc-147">Durante la distribuzione di un'applicazione sono disponibili le funzioni di annuncio, pubblicazione, ripristino e installazione su richiesta.</span><span class="sxs-lookup"><span data-stu-id="c34cc-147">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>

- <span data-ttu-id="c34cc-148">Distribuzione aziendale.</span><span class="sxs-lookup"><span data-stu-id="c34cc-148">Enterprise deployment.</span></span>

     <span data-ttu-id="c34cc-149">Questa funzionalità semplifica la distribuzione di software, anche mediante Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c34cc-149">This feature provides easy software distribution, including using Active Directory.</span></span>

- <span data-ttu-id="c34cc-150">Download e memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="c34cc-150">Downloading and caching.</span></span>

     <span data-ttu-id="c34cc-151">I download incrementali consentono di limitare le dimensioni degli oggetti scaricati e i componenti possono essere isolati per consentirne l'uso solo da parte dell'applicazione, in modo da ridurre al minimo l'impatto della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-151">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>

- <span data-ttu-id="c34cc-152">Codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="c34cc-152">Partially trusted code.</span></span>

     <span data-ttu-id="c34cc-153">L'identità è basata sul codice anziché sull'utente e non viene visualizzata alcuna finestra di dialogo relativa ai certificati.</span><span class="sxs-lookup"><span data-stu-id="c34cc-153">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>

## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="c34cc-154">Creazione di pacchetti e distribuzione di applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c34cc-154">Packaging and Distributing .NET Framework Applications</span></span>

<span data-ttu-id="c34cc-155">Alcuni concetti relativi alla creazione di pacchetti e alla distribuzione in .NET Framework vengono illustrati in altre sezioni della documentazione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-155">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="c34cc-156">Queste sezioni includono informazioni sulle unità autodescrittive denominate [assembly](../../standard/assembly/index.md), che non richiedono voci nel Registro di sistema, sugli [assembly con nome sicuro](../../standard/assembly/strong-named.md), che assicurano l'univocità dei nomi e prevengono lo spoofing dei nomi e sul [controllo delle versioni degli assembly](../../standard/assembly/versioning.md), che consente di risolvere molti dei problemi associati ai conflitti di DLL.</span><span class="sxs-lookup"><span data-stu-id="c34cc-156">Those sections provide information about the self-describing units called [assemblies](../../standard/assembly/index.md), which require no registry entries, [strong-named assemblies](../../standard/assembly/strong-named.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../standard/assembly/versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="c34cc-157">Le sezioni seguenti forniscono informazioni sulla creazione di pacchetti e sulla distribuzione di applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c34cc-157">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>

### <a name="packaging"></a><span data-ttu-id="c34cc-158">Creazione del package</span><span class="sxs-lookup"><span data-stu-id="c34cc-158">Packaging</span></span>

<span data-ttu-id="c34cc-159">.NET Framework consente di creare i pacchetti delle applicazioni nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="c34cc-159">The .NET Framework provides the following options for packaging applications:</span></span>

- <span data-ttu-id="c34cc-160">Come singolo assembly o come una raccolta di assembly.</span><span class="sxs-lookup"><span data-stu-id="c34cc-160">As a single assembly or as a collection of assemblies.</span></span>

     <span data-ttu-id="c34cc-161">Con questa opzione è sufficiente usare i file DLL o EXE così come sono stati compilati.</span><span class="sxs-lookup"><span data-stu-id="c34cc-161">With this option, you simply use the .dll or .exe files as they were built.</span></span>

- <span data-ttu-id="c34cc-162">Come file cabinet (CAB).</span><span class="sxs-lookup"><span data-stu-id="c34cc-162">As cabinet (CAB) files.</span></span>

     <span data-ttu-id="c34cc-163">Con questa opzione i file vengono compressi in file CAB per ridurre il tempo necessario per la distribuzione o il download.</span><span class="sxs-lookup"><span data-stu-id="c34cc-163">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>

- <span data-ttu-id="c34cc-164">Come pacchetto di Windows Installer o programmi di installazione in altri formati.</span><span class="sxs-lookup"><span data-stu-id="c34cc-164">As a Windows Installer package or in other installer formats.</span></span>

     <span data-ttu-id="c34cc-165">Con questa opzione vengono creati file MSI che possono essere usati con Windows Installer oppure viene creato un pacchetto dell'applicazione per l'uso con altri programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-165">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>

### <a name="distribution"></a><span data-ttu-id="c34cc-166">Punto di</span><span class="sxs-lookup"><span data-stu-id="c34cc-166">Distribution</span></span>

<span data-ttu-id="c34cc-167">.NET Framework consente di distribuire le applicazioni nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="c34cc-167">The .NET Framework provides the following options for distributing applications:</span></span>

- <span data-ttu-id="c34cc-168">Mediante XCOPY o FTP.</span><span class="sxs-lookup"><span data-stu-id="c34cc-168">Use XCOPY or FTP.</span></span>

     <span data-ttu-id="c34cc-169">Poiché le applicazioni Common Language Runtime sono autodescrittive e non richiedono alcuna voce nel Registro di sistema, è possibile usare XCOPY o FTP per copiare semplicemente l'applicazione in una directory appropriata.</span><span class="sxs-lookup"><span data-stu-id="c34cc-169">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="c34cc-170">L'applicazione potrà quindi essere eseguita da tale directory.</span><span class="sxs-lookup"><span data-stu-id="c34cc-170">The application can then be run from that directory.</span></span>

- <span data-ttu-id="c34cc-171">Mediante download del codice.</span><span class="sxs-lookup"><span data-stu-id="c34cc-171">Use code download.</span></span>

     <span data-ttu-id="c34cc-172">Se l'applicazione viene distribuita su Internet o su una rete Intranet aziendale, è possibile effettuare il download del codice su un computer ed eseguire l'applicazione su tale computer.</span><span class="sxs-lookup"><span data-stu-id="c34cc-172">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>

- <span data-ttu-id="c34cc-173">Mediante un programma di installazione come Windows Installer 2.0.</span><span class="sxs-lookup"><span data-stu-id="c34cc-173">Use an installer program such as Windows Installer 2.0.</span></span>

     <span data-ttu-id="c34cc-174">Windows Installer 2.0 consente di installare, ripristinare o rimuovere assembly .NET Framework nella Global Assembly Cache e in directory private.</span><span class="sxs-lookup"><span data-stu-id="c34cc-174">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>

### <a name="installation-location"></a><span data-ttu-id="c34cc-175">Percorso di installazione</span><span class="sxs-lookup"><span data-stu-id="c34cc-175">Installation Location</span></span>

<span data-ttu-id="c34cc-176">Per determinare dove distribuire gli assembly dell'applicazione per consentirne l'individuazione da parte del runtime, vedere [Come il runtime individua gli assembly](how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c34cc-176">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](how-the-runtime-locates-assemblies.md).</span></span>

<span data-ttu-id="c34cc-177">La modalità di distribuzione delle applicazioni dipende anche da alcune considerazioni sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c34cc-177">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="c34cc-178">Le autorizzazioni di sicurezza vengono concesse al codice gestito in base alla posizione del codice.</span><span class="sxs-lookup"><span data-stu-id="c34cc-178">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="c34cc-179">La distribuzione di un'applicazione o di un componente in una posizione con un livello di attendibilità basso, ad esempio Internet, comporta la limitazione delle operazioni che possono essere eseguite dall'applicazione o dal componente.</span><span class="sxs-lookup"><span data-stu-id="c34cc-179">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="c34cc-180">Per altre informazioni sulla distribuzione e considerazioni relative alla sicurezza, vedere [Nozioni fondamentali sulla sicurezza per l'accesso al codice](../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="c34cc-180">For more information about deployment and security considerations, see [Code Access Security Basics](../misc/code-access-security-basics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c34cc-181">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c34cc-181">Related Topics</span></span>

|<span data-ttu-id="c34cc-182">Titolo</span><span class="sxs-lookup"><span data-stu-id="c34cc-182">Title</span></span>|<span data-ttu-id="c34cc-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c34cc-183">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="c34cc-184">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="c34cc-184">How the Runtime Locates Assemblies</span></span>](how-the-runtime-locates-assemblies.md)|<span data-ttu-id="c34cc-185">Descrive come Common Language Runtime determina l'assembly da usare per eseguire una richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-185">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|
|[<span data-ttu-id="c34cc-186">Procedure consigliate per il caricamento di assembly</span><span class="sxs-lookup"><span data-stu-id="c34cc-186">Best Practices for Assembly Loading</span></span>](best-practices-for-assembly-loading.md)|<span data-ttu-id="c34cc-187">Illustra come evitare problemi di identità del tipo che possono causare la generazione di eccezioni <xref:System.InvalidCastException>, <xref:System.MissingMethodException> e altri errori.</span><span class="sxs-lookup"><span data-stu-id="c34cc-187">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|
|[<span data-ttu-id="c34cc-188">Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c34cc-188">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)|<span data-ttu-id="c34cc-189">Descrive il gestore di riavvio, che impedisce automaticamente il riavvio quando possibile, e viene illustrato come le applicazioni che installano .NET Framework possano usufruirne.</span><span class="sxs-lookup"><span data-stu-id="c34cc-189">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|
|[<span data-ttu-id="c34cc-190">Guida alla distribuzione per amministratori</span><span class="sxs-lookup"><span data-stu-id="c34cc-190">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)|<span data-ttu-id="c34cc-191">Viene illustrato come un amministratore di sistema può distribuire il .NET Framework e le relative dipendenze di sistema attraverso una rete usando Microsoft endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c34cc-191">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>|
|[<span data-ttu-id="c34cc-192">Guida alla distribuzione per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="c34cc-192">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)|<span data-ttu-id="c34cc-193">Illustra come gli sviluppatori possono installare .NET Framework nei computer dei rispettivi utenti con le rispettive applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c34cc-193">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|
|[<span data-ttu-id="c34cc-194">Distribuzione di applicazioni, servizi e componenti</span><span class="sxs-lookup"><span data-stu-id="c34cc-194">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="c34cc-195">Illustra le opzioni di distribuzione di Visual Studio, incluse le istruzioni per la pubblicazione di un'applicazione usando le tecnologie ClickOnce e Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="c34cc-195">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>|
|[<span data-ttu-id="c34cc-196">Pubblicazione di applicazioni ClickOnce</span><span class="sxs-lookup"><span data-stu-id="c34cc-196">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="c34cc-197">Descrive come creare il pacchetto di un'applicazione Windows Forms e distribuirla con ClickOnce nei computer client di una rete.</span><span class="sxs-lookup"><span data-stu-id="c34cc-197">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|
|[<span data-ttu-id="c34cc-198">Creazione del pacchetto e distribuzione delle risorse</span><span class="sxs-lookup"><span data-stu-id="c34cc-198">Packaging and Deploying Resources</span></span>](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="c34cc-199">Descrive il modello hub e spoke usato da .NET Framework per creare pacchetti e distribuire le risorse. Vengono illustrate le convenzioni di denominazione, i processi di fallback e le possibilità alternative di creazione di pacchetti delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c34cc-199">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|
|[<span data-ttu-id="c34cc-200">Distribuzione di una applicazione di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="c34cc-200">Deploying an Interop Application</span></span>](../interop/deploying-an-interop-application.md)|<span data-ttu-id="c34cc-201">Illustra come fornire e installare applicazioni di interoperabilità, che in genere includono un assembly client .NET Framework, uno o più assembly di interoperabilità che rappresentano librerie dei tipi COM distinte e uno o più componenti COM registrati.</span><span class="sxs-lookup"><span data-stu-id="c34cc-201">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|
|[<span data-ttu-id="c34cc-202">Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c34cc-202">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="c34cc-203">Descrive come avviare e rilevare automaticamente il processo di installazione di .NET Framework pur mostrando la propria visualizzazione dello stato di avanzamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="c34cc-203">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c34cc-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c34cc-204">See also</span></span>

- [<span data-ttu-id="c34cc-205">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="c34cc-205">Development Guide</span></span>](../development-guide.md)
