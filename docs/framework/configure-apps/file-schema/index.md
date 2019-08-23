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
ms.openlocfilehash: c3b5518b4b86c2e6f47825d552f49579c5ac0a6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921036"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="936a0-102">Schema dei file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="936a0-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="936a0-103">I file di configurazione sono file XML standard che è possibile usare per modificare le impostazioni e impostare criteri per le app.</span><span class="sxs-lookup"><span data-stu-id="936a0-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="936a0-104">Lo schema di configurazione di .NET Framework è costituito da elementi che è possibile usare nei file di configurazione per controllare il comportamento delle app.</span><span class="sxs-lookup"><span data-stu-id="936a0-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="936a0-105">Il sommario di questa sezione rispecchia la gerarchia dello schema per l'avvio, il runtime, la rete e altri tipi di impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="936a0-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="936a0-106">Per informazioni sui tipi, il formato e il percorso dei file di configurazione, vedere l'articolo [Configurazione di app](../index.md).</span><span class="sxs-lookup"><span data-stu-id="936a0-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](../index.md).</span></span> <span data-ttu-id="936a0-107">Per modificare direttamente i file di configurazione, acquisire familiarità con XML.</span><span class="sxs-lookup"><span data-stu-id="936a0-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="936a0-108">Gli attributi e i tag XML nei file di configurazione fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="936a0-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="936a0-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="936a0-109">In this section</span></span>

<span data-ttu-id="936a0-110">[**Elemento \<configuration>** ](configuration-element.md) Viene descritto l'elemento `<configuration>`, ossia l'elemento di primo livello di tutti i file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="936a0-110">[**\<configuration>** Element](configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="936a0-111">[**Elemento \<assemblyBinding>** ](assemblybinding-element-for-configuration.md) Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="936a0-111">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="936a0-112">[**Elemento \<linkedConfiguration>** ](linkedconfiguration-element.md) Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="936a0-112">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="936a0-113">[Schema delle impostazioni di avvio](./startup/index.md) Vengono descritti gli elementi che specificano la versione di Common Language Runtime da usare.</span><span class="sxs-lookup"><span data-stu-id="936a0-113">[Startup Settings Schema](./startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="936a0-114">[Schema delle impostazioni di runtime](./runtime/index.md) Vengono descritti gli elementi che configurano l'associazione degli assembly e il comportamento dell'ambiente di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="936a0-114">[Runtime Settings Schema](./runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="936a0-115">[Schema delle impostazioni di rete](./network/index.md) Vengono descritti gli elementi che specificano la modalità di connessione di .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="936a0-115">[Network Settings Schema](./network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="936a0-116">[Schema delle impostazioni di crittografia](./cryptography/index.md) Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="936a0-116">[Cryptography Settings Schema](./cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="936a0-117">[Schema delle sezioni di configurazione](configuration-sections-schema.md) Vengono descritti gli elementi che consentono di creare e usare le sezioni di configurazione per le impostazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="936a0-117">[Configuration Sections Schema](configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="936a0-118">[Schema delle impostazioni di traccia e debug](./trace-debug/index.md) Vengono descritti gli elementi che specificano i listener e le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="936a0-118">[Trace and Debug Settings Schema](./trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="936a0-119">[Schema di impostazioni del compilatore e del provider di linguaggi](./compiler/index.md) Vengono descritti gli elementi che specificano la configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="936a0-119">[Compiler and Language Provider Settings Schema](./compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="936a0-120">[Schema Application Settings](application-settings-schema.md) Vengono descritti gli elementi che consentono a un'applicazione Windows Form o ASP.NET di archiviare e recuperare le impostazioni con ambito applicazione o utente.</span><span class="sxs-lookup"><span data-stu-id="936a0-120">[Application Settings Schema](application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="936a0-121">[Schema impostazioni applicazione](./appsettings/index.md) Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="936a0-121">[App Settings Schema](./appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="936a0-122">[Schema delle impostazioni Web](./web/index.md) Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS.</span><span class="sxs-lookup"><span data-stu-id="936a0-122">[Web Settings Schema](./web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="936a0-123">Usato nei file *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="936a0-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="936a0-124">[Schema di configurazione di Windows Form](winforms/index.md) Tutti gli elementi nella sezione di configurazione dell'applicazione Windows Form, che include le personalizzazioni, ad esempio il supporto di valori DPI alti e di più monitor.</span><span class="sxs-lookup"><span data-stu-id="936a0-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="936a0-125">[Schema di configurazione di WCF](./wcf/index.md) Tutti gli elementi che consentono di configurare il servizio e le applicazioni client WCF.</span><span class="sxs-lookup"><span data-stu-id="936a0-125">[WCF Configuration Schema](./wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="936a0-126">[Sintassi delle direttive WCF](./wcf-directive/index.md) Viene descritta la direttiva `@ServiceHost` che definisce gli attributi specifici della pagina usati dal compilatore con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="936a0-126">[WCF Directive Syntax](./wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="936a0-127">[Schema di configurazione di WIF](windows-identity-foundation/index.md) Tutti gli elementi dello schema di configurazione WIF (Windows Identity Foundation).</span><span class="sxs-lookup"><span data-stu-id="936a0-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="936a0-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="936a0-128">Related sections</span></span>

<span data-ttu-id="936a0-129">[Schema delle impostazioni remote](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) Vengono descritti gli elementi che configurano le applicazioni client e server che implementano i servizi remoti.</span><span class="sxs-lookup"><span data-stu-id="936a0-129">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="936a0-130">[Schema delle impostazioni ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) Vengono descritti gli elementi che controllano il comportamento delle applicazioni Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="936a0-130">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="936a0-131">[Schema delle impostazioni dei servizi Web ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) Vengono descritti gli elementi che controllano il comportamento dei servizi Web ASP.NET e dei relativi client.</span><span class="sxs-lookup"><span data-stu-id="936a0-131">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="936a0-132">[Configurazione di app .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) Viene descritto come configurare la sicurezza, l'associazione degli assembly e i servizi remoti in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="936a0-132">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
