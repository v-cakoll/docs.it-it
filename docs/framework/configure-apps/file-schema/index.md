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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4543802c3918a4761daa5a4fbbab366695823f73
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839041"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>Schema dei file di configurazione per .NET Framework

I file di configurazione sono file XML standard che è possibile usare per modificare le impostazioni e impostare criteri per le app. Lo schema di configurazione di .NET Framework è costituito da elementi che è possibile usare nei file di configurazione per controllare il comportamento delle app. Il sommario di questa sezione rispecchia la gerarchia dello schema per l'avvio, il runtime, la rete e altri tipi di impostazioni di configurazione.

Per informazioni sui tipi, il formato e il percorso dei file di configurazione, vedere l'articolo [Configurazione di app](~/docs/framework/configure-apps/index.md). Per modificare direttamente i file di configurazione, acquisire familiarità con XML.

> [!IMPORTANT]
> Gli attributi e i tag XML nei file di configurazione fanno distinzione tra maiuscole e minuscole.

## <a name="in-this-section"></a>Contenuto della sezione

[**Elemento \<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) Viene descritto l'elemento `<configuration>`, ossia l'elemento di primo livello di tutti i file di configurazione.

[**Elemento \<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) Specifica i criteri di associazione degli assembly al livello di configurazione.

[**Elemento \<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Specifica un file di configurazione da includere.

[Schema delle impostazioni di avvio](~/docs/framework/configure-apps/file-schema/startup/index.md) Vengono descritti gli elementi che specificano la versione di Common Language Runtime da usare.

[Schema delle impostazioni di runtime](~/docs/framework/configure-apps/file-schema/runtime/index.md) Vengono descritti gli elementi che configurano l'associazione degli assembly e il comportamento dell'ambiente di esecuzione.

[Schema delle impostazioni di rete](~/docs/framework/configure-apps/file-schema/network/index.md) Vengono descritti gli elementi che specificano la modalità di connessione di .NET Framework a Internet.

[Schema delle impostazioni di crittografia](~/docs/framework/configure-apps/file-schema/cryptography/index.md) Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.

[Schema delle sezioni di configurazione](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) Vengono descritti gli elementi che consentono di creare e usare le sezioni di configurazione per le impostazioni personalizzate.

[Schema delle impostazioni di traccia e debug](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) Vengono descritti gli elementi che specificano i listener e le opzioni di traccia.

[Schema di impostazioni del compilatore e del provider di linguaggi](~/docs/framework/configure-apps/file-schema/compiler/index.md) Vengono descritti gli elementi che specificano la configurazione del compilatore per i provider di linguaggi disponibili.

[Schema Application Settings](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) Vengono descritti gli elementi che consentono a un'applicazione Windows Form o ASP.NET di archiviare e recuperare le impostazioni con ambito applicazione o utente.

[Schema impostazioni applicazione](~/docs/framework/configure-apps/file-schema/appsettings/index.md) Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.

[Schema delle impostazioni Web](~/docs/framework/configure-apps/file-schema/web/index.md) Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS. Usato nei file *Aspnet.config*.

[Schema di configurazione di Windows Form](winforms/index.md) Tutti gli elementi nella sezione di configurazione dell'applicazione Windows Form, che include le personalizzazioni, ad esempio il supporto di valori DPI alti e di più monitor.

[Schema di configurazione di WCF](~/docs/framework/configure-apps/file-schema/wcf/index.md) Tutti gli elementi che consentono di configurare il servizio e le applicazioni client WCF.

[Sintassi delle direttive WCF](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) Viene descritta la direttiva `@ServiceHost` che definisce gli attributi specifici della pagina usati dal compilatore con estensione svc.

[Schema di configurazione di WIF](windows-identity-foundation/index.md) Tutti gli elementi dello schema di configurazione WIF (Windows Identity Foundation).

## <a name="related-sections"></a>Sezioni correlate

[Schema delle impostazioni remote](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) Vengono descritti gli elementi che configurano le applicazioni client e server che implementano i servizi remoti.

[Schema delle impostazioni ASP.NET](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) Vengono descritti gli elementi che controllano il comportamento delle applicazioni Web ASP.NET.

[Schema delle impostazioni dei servizi Web ](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e) Vengono descritti gli elementi che controllano il comportamento dei servizi Web ASP.NET e dei relativi client.

[Configurazione di app .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) Viene descritto come configurare la sicurezza, l'associazione degli assembly e i servizi remoti in .NET Framework.
