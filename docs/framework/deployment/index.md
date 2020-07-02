---
title: Distribuzione di .NET Framework e delle applicazioni
description: Introduzione alla distribuzione di .NET con l'applicazione. .NET fornisce applicazioni senza effetti, componenti privati per impostazione predefinita, condivisione del codice controllata e altro ancora.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: cce888c962c9ab83c13cce4040eb9ba50270972d
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803501"
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="1d899-104">Distribuzione di .NET Framework e delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="1d899-104">Deploying the .NET Framework and Applications</span></span>

<span data-ttu-id="1d899-105">Questo articolo consente di iniziare a distribuire .NET Framework con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d899-105">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="1d899-106">La maggior parte delle informazioni, sono destinate agli sviluppatori OEM e agli amministratori aziendali.</span><span class="sxs-lookup"><span data-stu-id="1d899-106">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="1d899-107">È consigliabile che gli utenti che vogliono installare .NET Framework leggano [Installare .NET Framework](../install/index.md).</span><span class="sxs-lookup"><span data-stu-id="1d899-107">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](../install/index.md).</span></span>

## <a name="key-deployment-resources"></a><span data-ttu-id="1d899-108">Risorse principali di distribuzione</span><span class="sxs-lookup"><span data-stu-id="1d899-108">Key Deployment Resources</span></span>

<span data-ttu-id="1d899-109">Usare i seguenti collegamenti ad altri argomenti di MSDN per informazioni specifiche sulla distribuzione e sui servizi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d899-109">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>

<span data-ttu-id="1d899-110">**Installazione e distribuzione**</span><span class="sxs-lookup"><span data-stu-id="1d899-110">**Setup and deployment**</span></span>

- <span data-ttu-id="1d899-111">Installazione generica ed informazioni di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="1d899-111">General installer and deployment information:</span></span>

  - <span data-ttu-id="1d899-112">Opzioni del programma di installazione:</span><span class="sxs-lookup"><span data-stu-id="1d899-112">Installer options:</span></span>

    - [<span data-ttu-id="1d899-113">programma di installazione Web</span><span class="sxs-lookup"><span data-stu-id="1d899-113">Web installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [<span data-ttu-id="1d899-114">Programma di installazione offline</span><span class="sxs-lookup"><span data-stu-id="1d899-114">Offline installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - <span data-ttu-id="1d899-115">Modalità di installazione:</span><span class="sxs-lookup"><span data-stu-id="1d899-115">Installation modes:</span></span>

    - [<span data-ttu-id="1d899-116">Installazione invisibile all'utente</span><span class="sxs-lookup"><span data-stu-id="1d899-116">Silent installation</span></span>](deployment-guide-for-developers.md#chaining_custom)

    - [<span data-ttu-id="1d899-117">Visualizzazione di un'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1d899-117">Displaying a UI</span></span>](deployment-guide-for-developers.md#chaining_default)

  - [<span data-ttu-id="1d899-118">Riduzione del riavvii del sistema durante le installazioni di .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="1d899-118">Reducing system restarts during .NET Framework 4.5 installations</span></span>](reducing-system-restarts.md)

  - [<span data-ttu-id="1d899-119">Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1d899-119">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- <span data-ttu-id="1d899-120">Distribuzione di .NET Framework in un'applicazione client (per gli sviluppatori): </span><span class="sxs-lookup"><span data-stu-id="1d899-120">Deploying the .NET Framework with a client application (for developers):</span></span>

  - <span data-ttu-id="1d899-121">[Uso di InstallShield](deployment-guide-for-developers.md#installshield-deployment) in un progetto di installazione e distribuzione</span><span class="sxs-lookup"><span data-stu-id="1d899-121">[Using InstallShield](deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>

  - [<span data-ttu-id="1d899-122">Uso di un'applicazione ClickOnce di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1d899-122">Using a Visual Studio ClickOnce application</span></span>](deployment-guide-for-developers.md#clickonce-deployment)

  - [<span data-ttu-id="1d899-123">Creazione di un pacchetto di installazione WiX</span><span class="sxs-lookup"><span data-stu-id="1d899-123">Creating a WiX installation package</span></span>](deployment-guide-for-developers.md#wix)

  - [<span data-ttu-id="1d899-124">Uso di un programma di installazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="1d899-124">Using a custom installer</span></span>](deployment-guide-for-developers.md#chaining)

  - <span data-ttu-id="1d899-125">[Altre informazioni](deployment-guide-for-developers.md) per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="1d899-125">[Additional information](deployment-guide-for-developers.md) for developers</span></span>

- <span data-ttu-id="1d899-126">Distribuzione di .NET Framework (per gli OEM e gli amministratori):</span><span class="sxs-lookup"><span data-stu-id="1d899-126">Deploying the .NET Framework (for OEMs and administrators):</span></span>

  - [<span data-ttu-id="1d899-127">Windows Assessment and Deployment Kit (ADK)</span><span class="sxs-lookup"><span data-stu-id="1d899-127">Windows Assessment and Deployment Kit (ADK)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [<span data-ttu-id="1d899-128">Guida dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="1d899-128">Administrator's guide</span></span>](guide-for-administrators.md)

<span data-ttu-id="1d899-129">**Manutenzione**</span><span class="sxs-lookup"><span data-stu-id="1d899-129">**Servicing**</span></span>

- <span data-ttu-id="1d899-130">Per informazioni generali, vedere il [blog .NET Framework](https://devblogs.microsoft.com/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="1d899-130">For general information, see the [.NET Framework blog](https://devblogs.microsoft.com/dotnet/).</span></span>

- [<span data-ttu-id="1d899-131">Determinazione delle versioni</span><span class="sxs-lookup"><span data-stu-id="1d899-131">Detecting versions</span></span>](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [<span data-ttu-id="1d899-132">Determinazione di service pack e aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="1d899-132">Detecting service packs and updates</span></span>](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a><span data-ttu-id="1d899-133">Funzionalità che semplificano la distribuzione</span><span class="sxs-lookup"><span data-stu-id="1d899-133">Features That Simplify Deployment</span></span>

<span data-ttu-id="1d899-134">In .NET Framework sono disponibili diverse funzionalità di base che semplificano la distribuzione delle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="1d899-134">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>

- <span data-ttu-id="1d899-135">Indipendenza delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1d899-135">No-impact applications.</span></span>

     <span data-ttu-id="1d899-136">Questa funzionalità fornisce l'isolamento delle applicazioni ed elimina i conflitti di DLL.</span><span class="sxs-lookup"><span data-stu-id="1d899-136">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="1d899-137">Per impostazione predefinita i componenti di un'applicazione non influenzano il funzionamento di altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1d899-137">By default, components do not affect other applications.</span></span>

- <span data-ttu-id="1d899-138">Componenti privati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1d899-138">Private components by default.</span></span>

     <span data-ttu-id="1d899-139">Per impostazione predefinita, i componenti vengono distribuiti nella directory dell'applicazione e sono visibili solo a tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d899-139">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>

- <span data-ttu-id="1d899-140">Condivisione controllata del codice.</span><span class="sxs-lookup"><span data-stu-id="1d899-140">Controlled code sharing.</span></span>

     <span data-ttu-id="1d899-141">La condivisione del codice richiede che il codice venga reso disponibile per la condivisione in modo esplicito, in quanto non è condiviso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1d899-141">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>

- <span data-ttu-id="1d899-142">Controllo delle versioni side-by-side.</span><span class="sxs-lookup"><span data-stu-id="1d899-142">Side-by-side versioning.</span></span>

     <span data-ttu-id="1d899-143">È possibile creare più versioni di un componente o di un'applicazione e specificare la versione da usare. I criteri di gestione delle versioni sono attivati da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1d899-143">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>

- <span data-ttu-id="1d899-144">Distribuzione e replica XCOPY.</span><span class="sxs-lookup"><span data-stu-id="1d899-144">XCOPY deployment and replication.</span></span>

     <span data-ttu-id="1d899-145">È possibile distribuire applicazioni e componenti autodescrittivi e indipendenti senza voci del Registro di sistema o dipendenze.</span><span class="sxs-lookup"><span data-stu-id="1d899-145">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>

- <span data-ttu-id="1d899-146">Aggiornamenti al volo.</span><span class="sxs-lookup"><span data-stu-id="1d899-146">On-the-fly updates.</span></span>

     <span data-ttu-id="1d899-147">Gli amministratori possono aggiornare le DLL dei programmi usando host, ad esempio ASP.NET, anche su computer remoti.</span><span class="sxs-lookup"><span data-stu-id="1d899-147">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>

- <span data-ttu-id="1d899-148">Integrazione con Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="1d899-148">Integration with the Windows Installer.</span></span>

     <span data-ttu-id="1d899-149">Durante la distribuzione di un'applicazione sono disponibili le funzioni di annuncio, pubblicazione, ripristino e installazione su richiesta.</span><span class="sxs-lookup"><span data-stu-id="1d899-149">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>

- <span data-ttu-id="1d899-150">Distribuzione aziendale.</span><span class="sxs-lookup"><span data-stu-id="1d899-150">Enterprise deployment.</span></span>

     <span data-ttu-id="1d899-151">Questa funzionalità semplifica la distribuzione di software, anche mediante Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d899-151">This feature provides easy software distribution, including using Active Directory.</span></span>

- <span data-ttu-id="1d899-152">Download e memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="1d899-152">Downloading and caching.</span></span>

     <span data-ttu-id="1d899-153">I download incrementali consentono di limitare le dimensioni degli oggetti scaricati e i componenti possono essere isolati per consentirne l'uso solo da parte dell'applicazione, in modo da ridurre al minimo l'impatto della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1d899-153">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>

- <span data-ttu-id="1d899-154">Codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="1d899-154">Partially trusted code.</span></span>

     <span data-ttu-id="1d899-155">L'identità è basata sul codice anziché sull'utente e non viene visualizzata alcuna finestra di dialogo relativa ai certificati.</span><span class="sxs-lookup"><span data-stu-id="1d899-155">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>

## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="1d899-156">Creazione di pacchetti e distribuzione di applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1d899-156">Packaging and Distributing .NET Framework Applications</span></span>

<span data-ttu-id="1d899-157">Alcuni concetti relativi alla creazione di pacchetti e alla distribuzione in .NET Framework vengono illustrati in altre sezioni della documentazione.</span><span class="sxs-lookup"><span data-stu-id="1d899-157">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="1d899-158">Queste sezioni includono informazioni sulle unità autodescrittive denominate [assembly](../../standard/assembly/index.md), che non richiedono voci nel Registro di sistema, sugli [assembly con nome sicuro](../../standard/assembly/strong-named.md), che assicurano l'univocità dei nomi e prevengono lo spoofing dei nomi e sul [controllo delle versioni degli assembly](../../standard/assembly/versioning.md), che consente di risolvere molti dei problemi associati ai conflitti di DLL.</span><span class="sxs-lookup"><span data-stu-id="1d899-158">Those sections provide information about the self-describing units called [assemblies](../../standard/assembly/index.md), which require no registry entries, [strong-named assemblies](../../standard/assembly/strong-named.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../standard/assembly/versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="1d899-159">Le sezioni seguenti forniscono informazioni sulla creazione di pacchetti e sulla distribuzione di applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d899-159">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>

### <a name="packaging"></a><span data-ttu-id="1d899-160">Packaging</span><span class="sxs-lookup"><span data-stu-id="1d899-160">Packaging</span></span>

<span data-ttu-id="1d899-161">.NET Framework consente di creare i pacchetti delle applicazioni nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="1d899-161">The .NET Framework provides the following options for packaging applications:</span></span>

- <span data-ttu-id="1d899-162">Come singolo assembly o come una raccolta di assembly.</span><span class="sxs-lookup"><span data-stu-id="1d899-162">As a single assembly or as a collection of assemblies.</span></span>

     <span data-ttu-id="1d899-163">Con questa opzione è sufficiente usare i file DLL o EXE così come sono stati compilati.</span><span class="sxs-lookup"><span data-stu-id="1d899-163">With this option, you simply use the .dll or .exe files as they were built.</span></span>

- <span data-ttu-id="1d899-164">Come file cabinet (CAB).</span><span class="sxs-lookup"><span data-stu-id="1d899-164">As cabinet (CAB) files.</span></span>

     <span data-ttu-id="1d899-165">Con questa opzione i file vengono compressi in file CAB per ridurre il tempo necessario per la distribuzione o il download.</span><span class="sxs-lookup"><span data-stu-id="1d899-165">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>

- <span data-ttu-id="1d899-166">Come pacchetto di Windows Installer o programmi di installazione in altri formati.</span><span class="sxs-lookup"><span data-stu-id="1d899-166">As a Windows Installer package or in other installer formats.</span></span>

     <span data-ttu-id="1d899-167">Con questa opzione vengono creati file MSI che possono essere usati con Windows Installer oppure viene creato un pacchetto dell'applicazione per l'uso con altri programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="1d899-167">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>

### <a name="distribution"></a><span data-ttu-id="1d899-168">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="1d899-168">Distribution</span></span>

<span data-ttu-id="1d899-169">.NET Framework consente di distribuire le applicazioni nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="1d899-169">The .NET Framework provides the following options for distributing applications:</span></span>

- <span data-ttu-id="1d899-170">Mediante XCOPY o FTP.</span><span class="sxs-lookup"><span data-stu-id="1d899-170">Use XCOPY or FTP.</span></span>

     <span data-ttu-id="1d899-171">Poiché le applicazioni Common Language Runtime sono autodescrittive e non richiedono alcuna voce nel Registro di sistema, è possibile usare XCOPY o FTP per copiare semplicemente l'applicazione in una directory appropriata.</span><span class="sxs-lookup"><span data-stu-id="1d899-171">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="1d899-172">L'applicazione potrà quindi essere eseguita da tale directory.</span><span class="sxs-lookup"><span data-stu-id="1d899-172">The application can then be run from that directory.</span></span>

- <span data-ttu-id="1d899-173">Mediante download del codice.</span><span class="sxs-lookup"><span data-stu-id="1d899-173">Use code download.</span></span>

     <span data-ttu-id="1d899-174">Se l'applicazione viene distribuita su Internet o su una rete Intranet aziendale, è possibile effettuare il download del codice su un computer ed eseguire l'applicazione su tale computer.</span><span class="sxs-lookup"><span data-stu-id="1d899-174">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>

- <span data-ttu-id="1d899-175">Mediante un programma di installazione come Windows Installer 2.0.</span><span class="sxs-lookup"><span data-stu-id="1d899-175">Use an installer program such as Windows Installer 2.0.</span></span>

     <span data-ttu-id="1d899-176">Windows Installer 2.0 consente di installare, ripristinare o rimuovere assembly .NET Framework nella Global Assembly Cache e in directory private.</span><span class="sxs-lookup"><span data-stu-id="1d899-176">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>

### <a name="installation-location"></a><span data-ttu-id="1d899-177">Percorso di installazione</span><span class="sxs-lookup"><span data-stu-id="1d899-177">Installation Location</span></span>

<span data-ttu-id="1d899-178">Per determinare dove distribuire gli assembly dell'applicazione per consentirne l'individuazione da parte del runtime, vedere [Come il runtime individua gli assembly](how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="1d899-178">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](how-the-runtime-locates-assemblies.md).</span></span>

<span data-ttu-id="1d899-179">La modalità di distribuzione delle applicazioni dipende anche da alcune considerazioni sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1d899-179">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="1d899-180">Le autorizzazioni di sicurezza vengono concesse al codice gestito in base alla posizione del codice.</span><span class="sxs-lookup"><span data-stu-id="1d899-180">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="1d899-181">La distribuzione di un'applicazione o di un componente in una posizione con un livello di attendibilità basso, ad esempio Internet, comporta la limitazione delle operazioni che possono essere eseguite dall'applicazione o dal componente.</span><span class="sxs-lookup"><span data-stu-id="1d899-181">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="1d899-182">Per altre informazioni sulla distribuzione e considerazioni relative alla sicurezza, vedere [Nozioni fondamentali sulla sicurezza per l'accesso al codice](../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="1d899-182">For more information about deployment and security considerations, see [Code Access Security Basics](../misc/code-access-security-basics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d899-183">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1d899-183">Related Topics</span></span>

|<span data-ttu-id="1d899-184">Titolo</span><span class="sxs-lookup"><span data-stu-id="1d899-184">Title</span></span>|<span data-ttu-id="1d899-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d899-185">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="1d899-186">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="1d899-186">How the Runtime Locates Assemblies</span></span>](how-the-runtime-locates-assemblies.md)|<span data-ttu-id="1d899-187">Descrive come Common Language Runtime determina l'assembly da usare per eseguire una richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="1d899-187">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|
|[<span data-ttu-id="1d899-188">Procedure consigliate per il caricamento di assembly</span><span class="sxs-lookup"><span data-stu-id="1d899-188">Best Practices for Assembly Loading</span></span>](best-practices-for-assembly-loading.md)|<span data-ttu-id="1d899-189">Illustra come evitare problemi di identità del tipo che possono causare la generazione di eccezioni <xref:System.InvalidCastException>, <xref:System.MissingMethodException> e altri errori.</span><span class="sxs-lookup"><span data-stu-id="1d899-189">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|
|[<span data-ttu-id="1d899-190">Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1d899-190">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)|<span data-ttu-id="1d899-191">Descrive il gestore di riavvio, che impedisce automaticamente il riavvio quando possibile, e viene illustrato come le applicazioni che installano .NET Framework possano usufruirne.</span><span class="sxs-lookup"><span data-stu-id="1d899-191">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|
|[<span data-ttu-id="1d899-192">Guida alla distribuzione per amministratori</span><span class="sxs-lookup"><span data-stu-id="1d899-192">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)|<span data-ttu-id="1d899-193">Viene illustrato come un amministratore di sistema può distribuire il .NET Framework e le relative dipendenze di sistema attraverso una rete usando Microsoft endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1d899-193">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>|
|[<span data-ttu-id="1d899-194">Guida alla distribuzione per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="1d899-194">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)|<span data-ttu-id="1d899-195">Illustra come gli sviluppatori possono installare .NET Framework nei computer dei rispettivi utenti con le rispettive applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1d899-195">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|
|[<span data-ttu-id="1d899-196">Distribuzione di applicazioni, servizi e componenti</span><span class="sxs-lookup"><span data-stu-id="1d899-196">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="1d899-197">Illustra le opzioni di distribuzione di Visual Studio, incluse le istruzioni per la pubblicazione di un'applicazione usando le tecnologie ClickOnce e Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="1d899-197">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>|
|[<span data-ttu-id="1d899-198">Pubblicazione di applicazioni ClickOnce</span><span class="sxs-lookup"><span data-stu-id="1d899-198">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="1d899-199">Descrive come creare il pacchetto di un'applicazione Windows Forms e distribuirla con ClickOnce nei computer client di una rete.</span><span class="sxs-lookup"><span data-stu-id="1d899-199">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|
|[<span data-ttu-id="1d899-200">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="1d899-200">Packaging and Deploying Resources</span></span>](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="1d899-201">Descrive il modello hub e spoke usato da .NET Framework per creare pacchetti e distribuire le risorse. Vengono illustrate le convenzioni di denominazione, i processi di fallback e le possibilità alternative di creazione di pacchetti delle risorse.</span><span class="sxs-lookup"><span data-stu-id="1d899-201">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|
|[<span data-ttu-id="1d899-202">Distribuzione di una applicazione di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="1d899-202">Deploying an Interop Application</span></span>](../interop/deploying-an-interop-application.md)|<span data-ttu-id="1d899-203">Illustra come fornire e installare applicazioni di interoperabilità, che in genere includono un assembly client .NET Framework, uno o più assembly di interoperabilità che rappresentano librerie dei tipi COM distinte e uno o più componenti COM registrati.</span><span class="sxs-lookup"><span data-stu-id="1d899-203">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|
|[<span data-ttu-id="1d899-204">Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1d899-204">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="1d899-205">Descrive come avviare e rilevare automaticamente il processo di installazione di .NET Framework pur mostrando la propria visualizzazione dello stato di avanzamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="1d899-205">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1d899-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d899-206">See also</span></span>

- [<span data-ttu-id="1d899-207">Guida allo sviluppo</span><span class="sxs-lookup"><span data-stu-id="1d899-207">Development Guide</span></span>](../development-guide.md)
