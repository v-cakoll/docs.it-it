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
# <a name="configuration-file-schema-for-the-net-framework"></a>Schema dei file di configurazione per .NET Framework

I file di configurazione sono file XML standard che è possibile usare per modificare le impostazioni e impostare criteri per le app. Lo schema di configurazione di .NET Framework è costituito da elementi che è possibile usare nei file di configurazione per controllare il comportamento delle app. Il sommario di questa sezione rispecchia la gerarchia dello schema per l'avvio, il runtime, la rete e altri tipi di impostazioni di configurazione.

Per informazioni sui tipi, il formato e la posizione dei file di configurazione, vedere [configurare le app](../index.md). Per modificare direttamente i file di configurazione, acquisire familiarità con XML.

> [!IMPORTANT]
> Gli attributi e i tag XML nei file di configurazione fanno distinzione tra maiuscole e minuscole.

## <a name="in-this-section"></a>Contenuto della sezione

[**\<configuration>** Elemento](configuration-element.md)\
Elemento di primo livello per tutti i file di configurazione.

[**\<assemblyBinding>** Elemento](assemblybinding-element-for-configuration.md)\
Specifica i criteri di associazione degli assembly al livello di configurazione.

[**\<linkedConfiguration>** Elemento](linkedconfiguration-element.md)\
Specifica un file di configurazione da includere.

[Schema delle impostazioni di avvio](./startup/index.md)\
Elementi che specificano la versione del Common Language Runtime da usare.

[Schema delle impostazioni di runtime](./runtime/index.md)\
Elementi che configurano il comportamento del runtime e dell'associazione di assembly.

[Schema delle impostazioni di rete](./network/index.md)\
Elementi che specificano il modo in cui il .NET Framework si connette a Internet.

[Schema delle impostazioni di crittografia](./cryptography/index.md)\
Elementi che consentono di eseguire il mapping di nomi di algoritmi descrittivi a classi che implementano algoritmi di crittografia.

[Schema delle sezioni di configurazione](configuration-sections-schema.md)\
Elementi usati per creare e usare le sezioni di configurazione per le impostazioni personalizzate.

[Schema delle impostazioni di traccia e debug](./trace-debug/index.md)\
Elementi che specificano i listener e le opzioni di traccia.

[Schema delle impostazioni del compilatore e del provider del linguaggio](./compiler/index.md)\
Elementi che specificano la configurazione del compilatore per i provider di lingue disponibili.

[Schema delle impostazioni dell'applicazione](application-settings-schema.md)\
Elementi che consentono a un'applicazione Windows Forms o ASP.NET di archiviare e recuperare le impostazioni con ambito di applicazione e con ambito di utente.

[Schema delle impostazioni dell'app](./appsettings/index.md)\
Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.

[Schema delle impostazioni Web](./web/index.md)\
Elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host come IIS. Usato nei file *Aspnet.config*.

[Schema di configurazione Windows Forms](winforms/index.md)\
Tutti gli elementi nella sezione di configurazione Windows Forms Application, che include personalizzazioni quali il supporto di più monitor e DPI.

[Schema di configurazione di WCF](./wcf/index.md)\
Tutti gli elementi che consentono di configurare il servizio WCF e le applicazioni client.

[Sintassi delle direttive WCF](./wcf-directive/index.md)\
Viene descritta la `@ServiceHost` direttiva, che definisce gli attributi specifici della pagina utilizzati dal compilatore svc.

[Schema di configurazione di WIF](windows-identity-foundation/index.md)\
Tutti gli elementi dello schema di configurazione di Windows Identity Foundation (WIF).

## <a name="related-sections"></a>Sezioni correlate

[Schema delle impostazioni remote](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))\
Vengono descritti gli elementi che configurano le applicazioni client e server che implementano i servizi remoti.

[Schema delle impostazioni ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))\
Vengono descritti gli elementi che controllano il comportamento delle applicazioni Web ASP.NET.

[Schema delle impostazioni dei servizi Web](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))\
Vengono descritti gli elementi che controllano il comportamento dei servizi Web ASP.NET e dei relativi client.

[Configurazione di app .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))\
Viene descritto come configurare la sicurezza, l'associazione degli assembly e i servizi remoti in .NET Framework.
