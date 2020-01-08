---
title: URI di tipo pack in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: e20053c451d12c6a8493d5d7fcfc72fe3d3d764e
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636380"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="26326-102">URI di tipo pack in WPF</span><span class="sxs-lookup"><span data-stu-id="26326-102">Pack URIs in WPF</span></span>

<span data-ttu-id="26326-103">In Windows Presentation Foundation (WPF), gli URI (Uniform Resource Identifier) vengono usati per identificare e caricare i file in molti modi, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-103">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="26326-104">Specifica del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] da visualizzare all'avvio di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="26326-105">Caricando immagini.</span><span class="sxs-lookup"><span data-stu-id="26326-105">Loading images.</span></span>

- <span data-ttu-id="26326-106">Spostandosi sulle pagine.</span><span class="sxs-lookup"><span data-stu-id="26326-106">Navigating to pages.</span></span>

- <span data-ttu-id="26326-107">Caricando file di dati non eseguibili.</span><span class="sxs-lookup"><span data-stu-id="26326-107">Loading non-executable data files.</span></span>

<span data-ttu-id="26326-108">Gli URI possono inoltre essere utilizzati per identificare e caricare file da diverse posizioni, incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-108">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="26326-109">L'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="26326-109">The current assembly.</span></span>

- <span data-ttu-id="26326-110">Un assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-110">A referenced assembly.</span></span>

- <span data-ttu-id="26326-111">Un percorso relativo a un assembly.</span><span class="sxs-lookup"><span data-stu-id="26326-111">A location relative to an assembly.</span></span>

- <span data-ttu-id="26326-112">L'applicazione del sito di origine.</span><span class="sxs-lookup"><span data-stu-id="26326-112">The application's site of origin.</span></span>

<span data-ttu-id="26326-113">Per fornire un meccanismo coerente per l'identificazione e il caricamento di questi tipi di file da questi percorsi, WPF sfrutta l'estensibilità dello *schema URI*di tipo pack.</span><span class="sxs-lookup"><span data-stu-id="26326-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, WPF leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="26326-114">In questo argomento viene fornita una panoramica dello schema, viene illustrato come costruire URI di pacchetto per diversi scenari, vengono illustrati gli URI assoluti e relativi e la risoluzione degli URI, prima di illustrare come utilizzare gli URI di Pack da markup e codice.</span><span class="sxs-lookup"><span data-stu-id="26326-114">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="26326-115">Schema URI di tipo pack</span><span class="sxs-lookup"><span data-stu-id="26326-115">The Pack URI Scheme</span></span>

<span data-ttu-id="26326-116">Lo schema URI di tipo pack viene usato dalla specifica [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC), che descrive un modello per organizzare e identificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="26326-116">The pack URI scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="26326-117">Gli elementi chiave di questo modello sono i pacchetti e le parti, dove un *pacchetto* è un contenitore logico per una o più *parti*logiche.</span><span class="sxs-lookup"><span data-stu-id="26326-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="26326-118">La figura seguente illustra questo concetto.</span><span class="sxs-lookup"><span data-stu-id="26326-118">The following figure illustrates this concept.</span></span>

![Diagramma di package e parti](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="26326-120">Per identificare le parti, la specifica OPC sfrutta l'estendibilità di RFC 2396 (Uniform Resource Identifier (URI): sintassi generica) per definire lo schema URI di Pack.</span><span class="sxs-lookup"><span data-stu-id="26326-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="26326-121">Lo schema specificato da un URI viene definito dal relativo prefisso. http, FTP e file sono esempi noti.</span><span class="sxs-lookup"><span data-stu-id="26326-121">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="26326-122">Lo schema URI di Pack utilizza "Pack" come schema e contiene due componenti: Authority e Path.</span><span class="sxs-lookup"><span data-stu-id="26326-122">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="26326-123">Di seguito è riportato il formato per un URI di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="26326-123">The following is the format for a pack URI.</span></span>

<span data-ttu-id="26326-124">*percorso*/dell'*autorità* Pack://</span><span class="sxs-lookup"><span data-stu-id="26326-124">pack://*authority*/*path*</span></span>

<span data-ttu-id="26326-125">L' *autorità* specifica il tipo di pacchetto in cui è contenuta una parte, mentre il *percorso* specifica la posizione di una parte all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="26326-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="26326-126">Questo concetto è illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="26326-126">This concept is illustrated by the following figure:</span></span>

![Relazione tra package, autorità e percorso](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="26326-128">Pacchetti e parti sono analoghi ad applicazioni e file, dove un'applicazione (pacchetto) può includere uno o più file (parti), tra cui:</span><span class="sxs-lookup"><span data-stu-id="26326-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="26326-129">File di risorse compilati nell'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-129">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="26326-130">File di risorse compilati in un assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-130">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="26326-131">File di risorse compilati in un assembly contenente un riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-131">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="26326-132">File di contenuto.</span><span class="sxs-lookup"><span data-stu-id="26326-132">Content files.</span></span>

- <span data-ttu-id="26326-133">File del sito di origine.</span><span class="sxs-lookup"><span data-stu-id="26326-133">Site of origin files.</span></span>

<span data-ttu-id="26326-134">Per accedere a questi tipi di file, WPF supporta due autorità: application:///e siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="26326-134">To access these types of files, WPF supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="26326-135">L'autorità application:/// identifica i file di dati dell'applicazione noti al momento della compilazione, inclusi file di risorse e di contenuto.</span><span class="sxs-lookup"><span data-stu-id="26326-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="26326-136">L'autorità siteoforigin:/// identifica i file del sito di origine.</span><span class="sxs-lookup"><span data-stu-id="26326-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="26326-137">La figura seguente illustra l'ambito di ciascuna autorità.</span><span class="sxs-lookup"><span data-stu-id="26326-137">The scope of each authority is shown in the following figure.</span></span>

![Diagramma dell'URI di tipo pack](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="26326-139">Il componente Authority di un URI di pacchetto è un URI incorporato che punta a un pacchetto e deve essere conforme allo standard RFC 2396.</span><span class="sxs-lookup"><span data-stu-id="26326-139">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="26326-140">Inoltre, il carattere "/" deve essere sostituito con il carattere "," e i caratteri riservati quali "%" e "?" devono essere preceduti da un carattere di escape.</span><span class="sxs-lookup"><span data-stu-id="26326-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="26326-141">Per informazioni dettagliate, vedere la specifica OPC.</span><span class="sxs-lookup"><span data-stu-id="26326-141">See the OPC for details.</span></span>

<span data-ttu-id="26326-142">Le sezioni seguenti illustrano come costruire gli URI di pacchetto usando queste due autorità insieme ai percorsi appropriati per l'identificazione dei file di risorse, di contenuto e del sito di origine.</span><span class="sxs-lookup"><span data-stu-id="26326-142">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="26326-143">URI di tipo pack di file di risorse</span><span class="sxs-lookup"><span data-stu-id="26326-143">Resource File Pack URIs</span></span>

<span data-ttu-id="26326-144">I file di risorse sono configurati come MSBuild `Resource` gli elementi e vengono compilati in assembly.</span><span class="sxs-lookup"><span data-stu-id="26326-144">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="26326-145">WPF supporta la costruzione di URI di tipo pack che possono essere utilizzati per identificare i file di risorse compilati nell'assembly locale o compilati in un assembly a cui viene fatto riferimento dall'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-145">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="26326-146">File di risorse dell'assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-146">Local Assembly Resource File</span></span>

<span data-ttu-id="26326-147">L'URI di Pack per un file di risorse compilato nell'assembly locale usa l'autorità e il percorso seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-147">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="26326-148">**Autorità**: application:///.</span><span class="sxs-lookup"><span data-stu-id="26326-148">**Authority**: application:///.</span></span>

- <span data-ttu-id="26326-149">**Percorso**: nome del file di risorse che include il percorso relativo alla radice della cartella del progetto dell'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="26326-150">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova nella radice della cartella del progetto dell'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-150">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="26326-151">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova in una sottocartella della cartella del progetto dell'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="26326-152">File di risorse dell'assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-152">Referenced Assembly Resource File</span></span>

<span data-ttu-id="26326-153">L'URI di Pack per un file di risorse compilato in un assembly a cui si fa riferimento usa l'autorità e il percorso seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-153">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="26326-154">**Autorità**: application:///.</span><span class="sxs-lookup"><span data-stu-id="26326-154">**Authority**: application:///.</span></span>

- <span data-ttu-id="26326-155">**Percorso**: nome di un file di risorse compilato in un assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="26326-156">Il percorso deve essere conforme al formato seguente:</span><span class="sxs-lookup"><span data-stu-id="26326-156">The path must conform to the following format:</span></span>

  <span data-ttu-id="26326-157">*NomeBreveAssembly*{ *; Versione*] { *; PublicKey*]; componente/*percorso*</span><span class="sxs-lookup"><span data-stu-id="26326-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="26326-158">**NomeBreveAssembly**: nome breve dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="26326-159">**;Versione** [facoltativo]: versione dell'assembly a cui si fa riferimento che contiene il file di risorse.</span><span class="sxs-lookup"><span data-stu-id="26326-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="26326-160">Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.</span><span class="sxs-lookup"><span data-stu-id="26326-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="26326-161">**;ChiavePubblica** [facoltativo]: chiave pubblica usata per firmare l'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="26326-162">Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.</span><span class="sxs-lookup"><span data-stu-id="26326-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="26326-163">**;component**: specifica che il riferimento all'assembly avviene dall'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="26326-164">**/Percorso**: nome del file di risorse, contenente il percorso relativo alla radice della cartella del progetto dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="26326-165">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova nella radice della cartella del progetto dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-165">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="26326-166">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova in una sottocartella della cartella del progetto dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="26326-167">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova nella cartella radice di una cartella di progetto di un assembly specifico della versione a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="26326-168">Si noti che la sintassi dell'URI di Pack per i file di risorse dell'assembly a cui si fa riferimento può essere usata solo con l'autorità application:///.</span><span class="sxs-lookup"><span data-stu-id="26326-168">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="26326-169">Il codice seguente, ad esempio, non è supportato in WPF.</span><span class="sxs-lookup"><span data-stu-id="26326-169">For example, the following is not supported in WPF.</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="26326-170">URI di tipo pack di file di contenuto</span><span class="sxs-lookup"><span data-stu-id="26326-170">Content File Pack URIs</span></span>

<span data-ttu-id="26326-171">L'URI di Pack per un file di contenuto usa l'autorità e il percorso seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-171">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="26326-172">**Autorità**: application:///.</span><span class="sxs-lookup"><span data-stu-id="26326-172">**Authority**: application:///.</span></span>

- <span data-ttu-id="26326-173">**Percorso**: nome del file di contenuto contenente il percorso relativo alla posizione del file system del principale assembly eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="26326-174">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], che si trova nella stessa cartella dell'assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="26326-174">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="26326-175">Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], che si trova in una sottocartella relativa all'assembly eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="26326-176">Non è possibile passare a file di contenuto HTML.</span><span class="sxs-lookup"><span data-stu-id="26326-176">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="26326-177">Lo schema URI supporta solo la navigazione a file HTML che si trovano nel sito di origine.</span><span class="sxs-lookup"><span data-stu-id="26326-177">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="26326-178">URI di tipo pack del sito di origine</span><span class="sxs-lookup"><span data-stu-id="26326-178">Site of Origin Pack URIs</span></span>

<span data-ttu-id="26326-179">L'URI di Pack per un file del sito di origine usa l'autorità e il percorso seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-179">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="26326-180">**Autorità**: siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="26326-180">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="26326-181">**Percorso**: nome del file del sito di origine contenente il percorso relativo alla posizione da cui è stato avviato l'assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="26326-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="26326-182">Nell'esempio seguente viene illustrato l'URI di pacchetto per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file del sito di origine, archiviato nel percorso da cui viene avviato l'assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="26326-182">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="26326-183">Nell'esempio seguente viene illustrato l'URI di pacchetto per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file del sito di origine, archiviato nella sottocartella relativa al percorso da cui viene avviato l'assembly eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="26326-184">File di paging</span><span class="sxs-lookup"><span data-stu-id="26326-184">Page Files</span></span>

<span data-ttu-id="26326-185">I file XAML configurati come MSBuild `Page` gli elementi vengono compilati in assembly nello stesso modo dei file di risorse.</span><span class="sxs-lookup"><span data-stu-id="26326-185">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="26326-186">Di conseguenza, è possibile identificare gli elementi di MSBuild `Page` usando gli URI di pacchetto per i file di risorse.</span><span class="sxs-lookup"><span data-stu-id="26326-186">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="26326-187">I tipi di file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] comunemente configurati come MSBuild`Page` elementi hanno uno dei seguenti elementi come elemento radice:</span><span class="sxs-lookup"><span data-stu-id="26326-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="26326-188">URI di pacchetto assoluto rispetto a</span><span class="sxs-lookup"><span data-stu-id="26326-188">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="26326-189">Un URI di pacchetto completo include lo schema, l'autorità e il percorso ed è considerato un URI di pacchetto assoluto.</span><span class="sxs-lookup"><span data-stu-id="26326-189">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="26326-190">Per semplificare gli sviluppatori, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi consentono in genere di impostare attributi appropriati con un URI di pacchetto relativo, che include solo il percorso.</span><span class="sxs-lookup"><span data-stu-id="26326-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="26326-191">Si consideri, ad esempio, l'URI di pacchetto assoluto seguente per un file di risorse nell'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-191">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="26326-192">L'URI di pacchetto relativo che fa riferimento a questo file di risorse è il seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-192">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="26326-193">Poiché i file del sito di origine non sono associati ad assembly, è possibile farvi riferimento solo con URI di pacchetto assoluti.</span><span class="sxs-lookup"><span data-stu-id="26326-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="26326-194">Per impostazione predefinita, un URI di pacchetto relativo viene considerato relativo alla posizione del markup o del codice che contiene il riferimento.</span><span class="sxs-lookup"><span data-stu-id="26326-194">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="26326-195">Se viene utilizzata una barra rovesciata principale, tuttavia, il riferimento all'URI di pacchetto relativo viene quindi considerato relativo alla radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-195">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="26326-196">Si consideri ad esempio la struttura di progetto seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-196">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="26326-197">Se Pagina1. XAML contiene un URI che fa riferimento alla *radice*\SubFolder\Page2.XAML, il riferimento può usare l'URI di pacchetto relativo seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-197">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="26326-198">Se Pagina1. XAML contiene un URI che fa riferimento alla *radice*\Page2.XAML, il riferimento può usare l'URI di pacchetto relativo seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-198">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="26326-199">Risoluzione degli URI di tipo pack</span><span class="sxs-lookup"><span data-stu-id="26326-199">Pack URI Resolution</span></span>

<span data-ttu-id="26326-200">Il formato degli URI di tipo pack rende possibile l'aspetto degli URI di tipo pack per diversi tipi di file.</span><span class="sxs-lookup"><span data-stu-id="26326-200">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="26326-201">Si consideri, ad esempio, l'URI di pacchetto assoluto seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-201">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="26326-202">Questo URI di tipo pack assoluto può fare riferimento a un file di risorse nell'assembly locale o in un file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="26326-202">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="26326-203">Lo stesso vale per l'URI relativo seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-203">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="26326-204">Per determinare il tipo di file a cui fa riferimento un URI di tipo pack, WPF risolve gli URI per i file di risorse in assembly locali e file di contenuto usando l'euristica seguente:</span><span class="sxs-lookup"><span data-stu-id="26326-204">In order to determine the type of file that a pack URI refers to, WPF resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="26326-205">Esegue il probe dei metadati dell'assembly per un attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> corrispondente all'URI del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="26326-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="26326-206">Se viene trovato l'attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, il percorso dell'URI del pacchetto fa riferimento a un file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="26326-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="26326-207">Se l'attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> non viene trovato, verificare i file di risorse impostati compilati nell'assembly locale.</span><span class="sxs-lookup"><span data-stu-id="26326-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="26326-208">Se viene trovato un file di risorse che corrisponde al percorso dell'URI del pacchetto, il percorso dell'URI del pacchetto fa riferimento a un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="26326-208">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="26326-209">Se la risorsa non viene trovata, il <xref:System.Uri> creato internamente non è valido.</span><span class="sxs-lookup"><span data-stu-id="26326-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="26326-210">La risoluzione dell'URI non è valida per gli URI che fanno riferimento agli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="26326-210">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="26326-211">File di contenuto in assembly a cui si fa riferimento: questi tipi di file non sono supportati da WPF.</span><span class="sxs-lookup"><span data-stu-id="26326-211">Content files in referenced assemblies: these file types are not supported by WPF.</span></span>

- <span data-ttu-id="26326-212">File incorporati negli assembly a cui si fa riferimento: gli URI che li identificano sono univoci in quanto includono sia il nome dell'assembly a cui si fa riferimento sia il suffisso `;component`.</span><span class="sxs-lookup"><span data-stu-id="26326-212">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="26326-213">File del sito di origine: gli URI che li identificano sono univoci perché sono gli unici file che possono essere identificati da URI di pacchetto che contengono l'autorità siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="26326-213">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="26326-214">Una semplificazione che la risoluzione URI di Pack consente è che il codice sia indipendente dalle posizioni dei file di risorse e di contenuto.</span><span class="sxs-lookup"><span data-stu-id="26326-214">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="26326-215">Se, ad esempio, si dispone di un file di risorse nell'assembly locale riconfigurato come file di contenuto, l'URI di pacchetto per la risorsa rimane invariato, così come il codice che usa l'URI di Pack.</span><span class="sxs-lookup"><span data-stu-id="26326-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="26326-216">Programmazione con URI di tipo pack</span><span class="sxs-lookup"><span data-stu-id="26326-216">Programming with Pack URIs</span></span>

<span data-ttu-id="26326-217">Molte classi WPF implementano proprietà che possono essere impostate con URI di pacchetto, tra cui:</span><span class="sxs-lookup"><span data-stu-id="26326-217">Many WPF classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="26326-218">Queste proprietà possono essere impostate da markup e codice.</span><span class="sxs-lookup"><span data-stu-id="26326-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="26326-219">Questa sezione illustra le costruzioni di base per entrambi e quindi riporta esempi di scenari comuni.</span><span class="sxs-lookup"><span data-stu-id="26326-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="26326-220">Uso di URI di tipo pack nel markup</span><span class="sxs-lookup"><span data-stu-id="26326-220">Using Pack URIs in Markup</span></span>

<span data-ttu-id="26326-221">Un URI di pacchetto viene specificato nel markup impostando l'elemento di un attributo con l'URI del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="26326-221">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="26326-222">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="26326-222">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="26326-223">Nella tabella 1 sono illustrati i vari URI di pacchetto assoluti che è possibile specificare nel markup.</span><span class="sxs-lookup"><span data-stu-id="26326-223">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="26326-224">Tabella 1: URI di tipo pack assoluti nel markup</span><span class="sxs-lookup"><span data-stu-id="26326-224">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="26326-225">File</span><span class="sxs-lookup"><span data-stu-id="26326-225">File</span></span>|<span data-ttu-id="26326-226">URI pack assoluto</span><span class="sxs-lookup"><span data-stu-id="26326-226">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="26326-227">File di risorse - assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="26326-228">File di risorse in una sottocartella - assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="26326-229">File di risorse - assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="26326-230">File di risorse in una sottocartella dell'assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="26326-231">File di risorse in un assembly a cui si fa riferimento con versione</span><span class="sxs-lookup"><span data-stu-id="26326-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="26326-232">File di contenuto</span><span class="sxs-lookup"><span data-stu-id="26326-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="26326-233">File di contenuto in una sottocartella</span><span class="sxs-lookup"><span data-stu-id="26326-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="26326-234">File del sito di origine</span><span class="sxs-lookup"><span data-stu-id="26326-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="26326-235">File del sito di origine in una sottocartella</span><span class="sxs-lookup"><span data-stu-id="26326-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="26326-236">Nella tabella 2 sono illustrati i vari URI di pacchetto relativi che è possibile specificare nel markup.</span><span class="sxs-lookup"><span data-stu-id="26326-236">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="26326-237">Tabella 2: URI di tipo pack relativi nel markup</span><span class="sxs-lookup"><span data-stu-id="26326-237">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="26326-238">File</span><span class="sxs-lookup"><span data-stu-id="26326-238">File</span></span>|<span data-ttu-id="26326-239">URI di pacchetto relativo</span><span class="sxs-lookup"><span data-stu-id="26326-239">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="26326-240">File di risorse nell'assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="26326-241">File di risorse in una sottocartella dell'assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="26326-242">File di risorse nell'assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="26326-243">File di risorse in una sottocartella dell'assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="26326-244">File di contenuto</span><span class="sxs-lookup"><span data-stu-id="26326-244">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="26326-245">File di contenuto in una sottocartella</span><span class="sxs-lookup"><span data-stu-id="26326-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="26326-246">Uso di URI di tipo pack nel codice</span><span class="sxs-lookup"><span data-stu-id="26326-246">Using Pack URIs in Code</span></span>

<span data-ttu-id="26326-247">È possibile specificare un URI di pacchetto nel codice creando un'istanza della classe <xref:System.Uri> e passando l'URI del pacchetto come parametro al costruttore.</span><span class="sxs-lookup"><span data-stu-id="26326-247">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="26326-248">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-248">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="26326-249">Per impostazione predefinita, la classe <xref:System.Uri> considera gli URI di pacchetto come assoluti.</span><span class="sxs-lookup"><span data-stu-id="26326-249">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="26326-250">Di conseguenza, viene generata un'eccezione quando un'istanza della classe <xref:System.Uri> viene creata con un URI di pacchetto relativo.</span><span class="sxs-lookup"><span data-stu-id="26326-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="26326-251">Fortunatamente, l'overload <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> del costruttore della classe <xref:System.Uri> accetta un parametro di tipo <xref:System.UriKind> per consentire di specificare se un URI di tipo pack è assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="26326-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="26326-252">È necessario specificare solo <xref:System.UriKind.Absolute> o <xref:System.UriKind.Relative> quando si è certi che l'URI di pacchetto fornito sia uno o l'altro.</span><span class="sxs-lookup"><span data-stu-id="26326-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="26326-253">Se non si conosce il tipo di URI di tipo pack usato, ad esempio quando un utente immette un URI di tipo pack in fase di esecuzione, usare invece <xref:System.UriKind.RelativeOrAbsolute>.</span><span class="sxs-lookup"><span data-stu-id="26326-253">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="26326-254">Nella tabella 3 vengono illustrati i vari URI di pacchetto relativi che è possibile specificare nel codice utilizzando <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="26326-254">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="26326-255">Tabella 3: URI di tipo pack assoluti nel codice</span><span class="sxs-lookup"><span data-stu-id="26326-255">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="26326-256">File</span><span class="sxs-lookup"><span data-stu-id="26326-256">File</span></span>|<span data-ttu-id="26326-257">URI pack assoluto</span><span class="sxs-lookup"><span data-stu-id="26326-257">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="26326-258">File di risorse - assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-259">File di risorse in una sottocartella - assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-260">File di risorse - assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-261">File di risorse in una sottocartella dell'assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-262">File di risorse in un assembly a cui si fa riferimento con versione</span><span class="sxs-lookup"><span data-stu-id="26326-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-263">File di contenuto</span><span class="sxs-lookup"><span data-stu-id="26326-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-264">File di contenuto in una sottocartella</span><span class="sxs-lookup"><span data-stu-id="26326-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-265">File del sito di origine</span><span class="sxs-lookup"><span data-stu-id="26326-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="26326-266">File del sito di origine in una sottocartella</span><span class="sxs-lookup"><span data-stu-id="26326-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="26326-267">Nella tabella 4 sono illustrati i vari URI di pacchetto relativi che è possibile specificare nel codice utilizzando <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="26326-267">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="26326-268">Tabella 4: URI di tipo pack relativi nel codice</span><span class="sxs-lookup"><span data-stu-id="26326-268">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="26326-269">File</span><span class="sxs-lookup"><span data-stu-id="26326-269">File</span></span>|<span data-ttu-id="26326-270">URI di pacchetto relativo</span><span class="sxs-lookup"><span data-stu-id="26326-270">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="26326-271">File di risorse - assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="26326-272">File di risorse in una sottocartella - assembly locale</span><span class="sxs-lookup"><span data-stu-id="26326-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="26326-273">File di risorse - assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="26326-274">File di risorse in una sottocartella - assembly a cui si fa riferimento</span><span class="sxs-lookup"><span data-stu-id="26326-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="26326-275">File di contenuto</span><span class="sxs-lookup"><span data-stu-id="26326-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="26326-276">File di contenuto in una sottocartella</span><span class="sxs-lookup"><span data-stu-id="26326-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="26326-277">Scenari comuni di URI Pack</span><span class="sxs-lookup"><span data-stu-id="26326-277">Common Pack URI Scenarios</span></span>

<span data-ttu-id="26326-278">Nelle sezioni precedenti è stato illustrato come costruire URI di pacchetto per identificare i file di risorse, di contenuto e del sito di origine.</span><span class="sxs-lookup"><span data-stu-id="26326-278">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="26326-279">In WPF queste costruzioni vengono usate in diversi modi e nelle sezioni seguenti vengono illustrati alcuni utilizzi comuni.</span><span class="sxs-lookup"><span data-stu-id="26326-279">In WPF, these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="26326-280">Specifica dell'interfaccia utente da visualizzare all'avvio di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="26326-280">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="26326-281"><xref:System.Windows.Application.StartupUri%2A> specifica il primo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da visualizzare quando viene avviata un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="26326-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a WPF application is launched.</span></span> <span data-ttu-id="26326-282">Per le applicazioni autonome, il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] può essere una finestra, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="26326-283">Le applicazioni autonome e le applicazioni browser XAML (XBAPs) possono inoltre specificare una pagina come interfaccia utente iniziale, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-283">Standalone applications and XAML browser applications (XBAPs) can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="26326-284">Se l'applicazione è un'applicazione autonoma e viene specificata una pagina con <xref:System.Windows.Application.StartupUri%2A>, WPF apre un <xref:System.Windows.Navigation.NavigationWindow> per ospitare la pagina.</span><span class="sxs-lookup"><span data-stu-id="26326-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, WPF opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="26326-285">Per le applicazioni XBAPs, la pagina viene visualizzata nel browser host.</span><span class="sxs-lookup"><span data-stu-id="26326-285">For XBAPs, the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="26326-286">Spostamento su una pagina</span><span class="sxs-lookup"><span data-stu-id="26326-286">Navigating to a Page</span></span>

<span data-ttu-id="26326-287">L'esempio seguente illustra come spostarsi su una pagina.</span><span class="sxs-lookup"><span data-stu-id="26326-287">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="26326-288">Per ulteriori informazioni sui vari modi per spostarsi in WPF, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="26326-288">For more information on the various ways to navigate in WPF, see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="26326-289">Specifica dell'icona di una finestra</span><span class="sxs-lookup"><span data-stu-id="26326-289">Specifying a Window Icon</span></span>

<span data-ttu-id="26326-290">L'esempio seguente illustra come usare un URI per specificare l'icona di una finestra.</span><span class="sxs-lookup"><span data-stu-id="26326-290">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="26326-291">Per ulteriori informazioni, vedere <xref:System.Windows.Window.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="26326-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="26326-292">Caricamento di file di immagine, audio e video</span><span class="sxs-lookup"><span data-stu-id="26326-292">Loading Image, Audio, and Video Files</span></span>

<span data-ttu-id="26326-293">WPF consente alle applicazioni di usare un'ampia gamma di tipi di supporti, che possono essere identificati e caricati con URI di tipo pack, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="26326-293">WPF allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="26326-294">Per ulteriori informazioni sull'utilizzo del contenuto multimediale, vedere [grafica e multimedia](../graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="26326-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="26326-295">Caricamento di un dizionario risorse dal sito di origine</span><span class="sxs-lookup"><span data-stu-id="26326-295">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="26326-296">È possibile usare i dizionari risorse (<xref:System.Windows.ResourceDictionary>) per supportare i temi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="26326-297">Un modo per creare e gestire i temi consiste nel creare più temi come dizionari risorse che si trovano nel sito di origine di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="26326-298">In questo modo è possibile aggiungere e aggiornare i temi senza ricompilare e ridistribuire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26326-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="26326-299">Questi dizionari risorse possono essere identificati e caricati usando gli URI di pacchetto, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26326-299">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="26326-300">Per una panoramica dei temi in WPF, vedere applicazione di [stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="26326-300">For an overview of themes in WPF, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26326-301">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26326-301">See also</span></span>

- [<span data-ttu-id="26326-302">File di dati e di risorse dell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="26326-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
