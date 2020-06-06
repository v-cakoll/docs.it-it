---
title: Schema dei file di configurazione per .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: 35ed53fc480e218df595794f80af2458f3ecec38
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73039151"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="812ff-102">Schema dei file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="812ff-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="812ff-103">I file di configurazione sono file XML standard che è possibile usare per modificare le impostazioni e impostare criteri per le app.</span><span class="sxs-lookup"><span data-stu-id="812ff-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="812ff-104">Lo schema di configurazione di .NET Framework è costituito da elementi che è possibile usare nei file di configurazione per controllare il comportamento delle app.</span><span class="sxs-lookup"><span data-stu-id="812ff-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="812ff-105">Il sommario di questa sezione rispecchia la gerarchia dello schema per l'avvio, il runtime, la rete e altri tipi di impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="812ff-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="812ff-106">Per informazioni sui tipi, il formato e la posizione dei file di configurazione, vedere [configurare le app](../index.md).</span><span class="sxs-lookup"><span data-stu-id="812ff-106">For information about the types, format, and location of configuration files, see [Configure apps](../index.md).</span></span> <span data-ttu-id="812ff-107">Per modificare direttamente i file di configurazione, acquisire familiarità con XML.</span><span class="sxs-lookup"><span data-stu-id="812ff-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="812ff-108">Gli attributi e i tag XML nei file di configurazione fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="812ff-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="812ff-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="812ff-109">In this section</span></span>

<span data-ttu-id="812ff-110">[**\<configuration>** Elemento](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-110">[**\<configuration>** Element](configuration-element.md)</span></span>\
<span data-ttu-id="812ff-111">Elemento di primo livello per tutti i file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="812ff-111">The top-level element for all configuration files.</span></span>

<span data-ttu-id="812ff-112">[**\<assemblyBinding>** Elemento](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="812ff-113">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="812ff-113">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="812ff-114">[**\<linkedConfiguration>** Elemento](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span></span>\
<span data-ttu-id="812ff-115">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="812ff-115">Specifies a configuration file to include.</span></span>

<span data-ttu-id="812ff-116">[Schema delle impostazioni di avvio](./startup/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-116">[Startup Settings Schema](./startup/index.md)</span></span>\
<span data-ttu-id="812ff-117">Elementi che specificano la versione del Common Language Runtime da usare.</span><span class="sxs-lookup"><span data-stu-id="812ff-117">Elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="812ff-118">[Schema delle impostazioni di runtime](./runtime/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-118">[Runtime Settings Schema](./runtime/index.md)</span></span>\
<span data-ttu-id="812ff-119">Elementi che configurano il comportamento del runtime e dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="812ff-119">Elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="812ff-120">[Schema delle impostazioni di rete](./network/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-120">[Network Settings Schema](./network/index.md)</span></span>\
<span data-ttu-id="812ff-121">Elementi che specificano il modo in cui il .NET Framework si connette a Internet.</span><span class="sxs-lookup"><span data-stu-id="812ff-121">Elements that specify how the .NET Framework connects to the internet.</span></span>

<span data-ttu-id="812ff-122">[Schema delle impostazioni di crittografia](./cryptography/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-122">[Cryptography Settings Schema](./cryptography/index.md)</span></span>\
<span data-ttu-id="812ff-123">Elementi che consentono di eseguire il mapping di nomi di algoritmi descrittivi a classi che implementano algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="812ff-123">Elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="812ff-124">[Schema delle sezioni di configurazione](configuration-sections-schema.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-124">[Configuration Sections Schema](configuration-sections-schema.md)</span></span>\
<span data-ttu-id="812ff-125">Elementi usati per creare e usare le sezioni di configurazione per le impostazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="812ff-125">Elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="812ff-126">[Schema delle impostazioni di traccia e debug](./trace-debug/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-126">[Trace and Debug Settings Schema](./trace-debug/index.md)</span></span>\
<span data-ttu-id="812ff-127">Elementi che specificano i listener e le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="812ff-127">Elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="812ff-128">[Schema delle impostazioni del compilatore e del provider del linguaggio](./compiler/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-128">[Compiler and Language Provider Settings Schema](./compiler/index.md)</span></span>\
<span data-ttu-id="812ff-129">Elementi che specificano la configurazione del compilatore per i provider di lingue disponibili.</span><span class="sxs-lookup"><span data-stu-id="812ff-129">Elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="812ff-130">[Schema delle impostazioni dell'applicazione](application-settings-schema.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-130">[Application Settings Schema](application-settings-schema.md)</span></span>\
<span data-ttu-id="812ff-131">Elementi che consentono a un'applicazione Windows Forms o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente.</span><span class="sxs-lookup"><span data-stu-id="812ff-131">Elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="812ff-132">[Schema delle impostazioni dell'app](./appsettings/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-132">[App Settings Schema](./appsettings/index.md)</span></span>\
<span data-ttu-id="812ff-133">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="812ff-133">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="812ff-134">[Schema delle impostazioni Web](./web/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-134">[Web Settings Schema](./web/index.md)</span></span>\
<span data-ttu-id="812ff-135">Elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host come IIS.</span><span class="sxs-lookup"><span data-stu-id="812ff-135">Elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="812ff-136">Usato nei file *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="812ff-136">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="812ff-137">[Schema di configurazione Windows Forms](winforms/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-137">[Windows Forms Configuration Schema](winforms/index.md)</span></span>\
<span data-ttu-id="812ff-138">Tutti gli elementi nella sezione di configurazione Windows Forms Application, che include personalizzazioni quali il supporto di più monitor e DPI.</span><span class="sxs-lookup"><span data-stu-id="812ff-138">All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high-DPI support.</span></span>

<span data-ttu-id="812ff-139">[Schema di configurazione di WCF](./wcf/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-139">[WCF Configuration Schema](./wcf/index.md)</span></span>\
<span data-ttu-id="812ff-140">Tutti gli elementi che consentono di configurare il servizio WCF e le applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="812ff-140">All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="812ff-141">[Sintassi delle direttive WCF](./wcf-directive/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-141">[WCF Directive Syntax](./wcf-directive/index.md)</span></span>\
<span data-ttu-id="812ff-142">Viene descritta la `@ServiceHost` direttiva, che definisce gli attributi specifici della pagina utilizzati dal compilatore svc.</span><span class="sxs-lookup"><span data-stu-id="812ff-142">Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="812ff-143">[Schema di configurazione di WIF](windows-identity-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="812ff-143">[WIF Configuration Schema](windows-identity-foundation/index.md)</span></span>\
<span data-ttu-id="812ff-144">Tutti gli elementi dello schema di configurazione di Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="812ff-144">All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="812ff-145">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="812ff-145">Related sections</span></span>

<span data-ttu-id="812ff-146">[Schema delle impostazioni remote](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="812ff-146">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span>\
<span data-ttu-id="812ff-147">Vengono descritti gli elementi che configurano le applicazioni client e server che implementano i servizi remoti.</span><span class="sxs-lookup"><span data-stu-id="812ff-147">Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="812ff-148">[Schema delle impostazioni ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="812ff-148">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span>\
<span data-ttu-id="812ff-149">Vengono descritti gli elementi che controllano il comportamento delle applicazioni Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="812ff-149">Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="812ff-150">[Schema delle impostazioni dei servizi Web](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="812ff-150">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span>\
<span data-ttu-id="812ff-151">Vengono descritti gli elementi che controllano il comportamento dei servizi Web ASP.NET e dei relativi client.</span><span class="sxs-lookup"><span data-stu-id="812ff-151">Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="812ff-152">[Configurazione di app .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="812ff-152">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span></span>\
<span data-ttu-id="812ff-153">Viene descritto come configurare la sicurezza, l'associazione degli assembly e i servizi remoti in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="812ff-153">Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
