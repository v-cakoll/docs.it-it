---
title: Eseguire la migrazione dell'app Web o del servizio .NET nel servizio app di Azure
description: Informazioni sulla migrazione di un'app web .NET o di un servizio da locale al servizio app di Azure.Learn about migrating a .NET web app or service from on-premises to Azure App Service.
ms.topic: conceptual
ms.date: 08/11/2018
ms.openlocfilehash: 57f3b981a1d94c2193160f55f9c8242da694c169
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "82072137"
---
# <a name="migrate-your-net-web-app-or-service-to-azure-app-service"></a>Eseguire la migrazione dell'app Web o del servizio .NET nel servizio app di Azure

[Il servizio app](https://docs.microsoft.com/azure/app-service/overview) è un servizio di piattaforma di elaborazione completamente gestito ottimizzato per l'hosting di siti Web e applicazioni Web scalabili. Questo articolo fornisce informazioni su come passare e spostare un'applicazione esistente nel servizio app di Azure, le modifiche da considerare e le risorse aggiuntive per [lo spostamento nel cloud.](https://azure.microsoft.com/migration/web-applications/) La maggior parte dei siti Web (Web Form, MVC) e dei servizi (Web API, WCF) ASP.NET può passare direttamente al servizio app di Azure senza alcuna modifica. Alcuni possono necessitare di modifiche minori, mentre per altri possono occorrere alcune operazioni di refactoring.

Informazioni introduttive [Pubblicare l'applicazione ASP.NET + SQL nel servizio app di Azure](https://tutorials.visualstudio.com/azure-webapp-migrate/intro).

## <a name="considerations"></a>Considerazioni

### <a name="on-premises-resources-including-sql-server"></a>Risorse locali (incluso SQL Server)

Verificare l'accesso alle risorse locali perché potrebbe essere necessario eseguirne la migrazione o apportarvi modifiche. Di seguito sono riportate le opzioni per mitigare l'accesso alle risorse locali:

* Creare una VPN che connetta il servizio app alle risorse locali usando le [rete virtuali di Azure](https://docs.microsoft.com/azure/app-service/web-sites-integrate-with-vnet).
* Esporre i servizi locali in modo sicuro nel cloud senza modifiche al firewall usando [Inoltro di Azure](https://docs.microsoft.com/azure/service-bus-relay/relay-what-is-it).
* Eseguire la migrazione delle dipendenze in Azure, ad esempio un [database SQL](https://go.microsoft.com/fwlink/?linkid=863217).
* Usare le offerte platform-as-a-service nel cloud per ridurre le dipendenze. Ad esempio, invece di connettersi a un server di posta locale considerare la possibilità di usare [SendGrid](https://docs.microsoft.com/azure/sendgrid-dotnet-how-to-send-email).

### <a name="port-bindings"></a>Binding delle porte

Il servizio app di Azure supporta la porta 80 per il traffico HTTP e la porta 443 per il traffico HTTPS.

Per WCF sono supportati i binding seguenti:

Associazione | Note
--------|--------
BasicHttp |
WSHttp |
WSDualHttpBinding | Il [supporto WebSocket](https://docs.microsoft.com/azure/app-service/web-sites-configure) deve essere abilitato.
NetHttpBinding | Il [supporto WebSocket](https://docs.microsoft.com/azure/app-service/web-sites-configure) deve essere abilitato per i contratti duplex.
NetHttpsBinding | Il [supporto WebSocket](https://docs.microsoft.com/azure/app-service/web-sites-configure) deve essere abilitato per i contratti duplex.
BasicHttpContextBinding |
WebHttpBinding |
WSHttpContextBinding |

### <a name="authentication"></a>Authentication

Il servizio app di Azure supporta l'autenticazione anonima per impostazione predefinita e l'autenticazione dei moduli quando prevista. L'autenticazione di Windows può essere usata eseguendo l'integrazione solo con Azure Active Directory e ADFS. [Altre informazioni su come integrare le directory locali con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="assemblies-in-the-gac-global-assembly-cache"></a>Assembly nella Global Assembly Cache (GAC)

Questa funzionalità non è supportata. Prendi in considerazione la possibilità di copiare gli assembly necessari nella cartella *.bin* dell'app. I file *MSI* personalizzati installati sul server (ad esempio, i generatori PDF) non possono essere utilizzati.

### <a name="iis-settings"></a>Impostazioni di IIS
Tutti gli elementi che normalmente vengono configurati tramite applicationHost.config nell'applicazione ora possono essere configurati tramite il portale di Azure. Questo vale per il numero di bit di AppPool, abilitare/disabilitare WebSockets, la versione della pipeline gestita, la versione di .NET Framework (2.0/4.0) e così via. Per modificare le [impostazioni applicazione](https://docs.microsoft.com/azure/app-service/web-sites-configure), passare al [portale di Azure](https://portal.azure.com), aprire il pannello dell'app Web e quindi selezionare la scheda **Impostazioni applicazione**.

#### <a name="iis5-compatibility-mode"></a>Modo di compatibilità IIS5
La modalità di compatibilità IIS5 non è supportata. Nel servizio app di Azure ogni app Web e tutte le applicazioni in essa contenuti vengono eseguite nello stesso processo di lavoro con un set specifico di pool di [applicazioni.](https://technet.microsoft.com/library/cc735247(v=WS.10).aspx)

#### <a name="iis7-schema-compliance"></a>Conformità dello schema IIS7+  
Alcuni elementi e attributi non sono definiti nello schema IIS del servizio app di Azure. Se si riscontrano problemi, considerare la possibilità di usare [trasformazioni XDT](https://azure.microsoft.com/documentation/articles/web-sites-transform-extend/).

#### <a name="single-application-pool-per-site"></a>Singolo pool di applicazioni per ogni sito  
Nel servizio app di Azure ogni app Web e tutte le applicazioni in essa contenuti vengono eseguite nello stesso pool di applicazioni. Valutare la possibilità di stabilire un singolo pool di applicazioni con impostazioni comuni o creare un'app Web separata per ogni applicazione.

### <a name="com-and-com-components"></a>Componenti COM e COM+  
Il servizio app di Azure non consente la registrazione di componenti COM nella piattaforma. Se l'app usa componenti COM, questi devono essere riscritti nel codice gestito e distribuiti con il sito o l'applicazione.

### <a name="physical-directories"></a>Directory fisiche
Il servizio app di Azure non consente l'accesso a unità fisiche. Potrebbe essere necessario usare File di [Azure](https://docs.microsoft.com/azure/storage/files/storage-files-introduction) per accedere ai file tramite SMB. [Archiviazione BLOB di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) consente di archiviare i file per l'accesso tramite HTTPS.

### <a name="isapi-filters"></a>Filtri ISAPI  
Il servizio app di Azure può supportare l'uso dei filtri ISAPI, tuttavia è necessario distribuire la DLL ISAPI con il sito e registrarla con web.config.

### <a name="https-bindings-and-ssl"></a>Binding HTTPS e SSL
I binding HTTPS non vengono migrati, né i certificati SSL associati ai siti Web. [I certificati SSL possono essere tuttavia caricati manualmente](https://docs.microsoft.com/azure/app-service/app-service-web-tutorial-custom-ssl) al termine della migrazione del sito.

### <a name="sharepoint-and-frontpage"></a>SharePoint e FrontPage
SharePoint e le estensioni del server di FrontPage (FPSE) non sono supportate.

### <a name="web-site-size"></a>Dimensioni del sito Web  
I siti gratuiti hanno dimensioni massime pari a 1 GB di contenuti. Se il sito ha dimensioni maggiori di 1 GB, è necessario eseguire l'aggiornamento a uno SKU a pagamento. Vedere [Prezzi del servizio app](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="database-size"></a>Dimensioni del database  
Per i database SQL Server, verificare i [prezzi correnti del database SQL](https://azure.microsoft.com/pricing/details/sql-database).

### <a name="azure-active-directory-aad-integration"></a>Integrazione di Azure Active Directory (AAD)  
AAD non funziona con le app gratuite. Per usare Azure Active Directory, è necessario aggiornare lo SKU dell'app. Vedere [Prezzi del servizio app](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="monitoring-and-diagnostics"></a>Monitoraggio e diagnostica
È improbabile che le soluzioni locali correnti per il monitoraggio e la diagnostica funzionino nel cloud. Azure fornisce tuttavia strumenti per la registrazione, il monitoraggio e la diagnostica per poter identificare i problemi delle app Web ed eseguirne il debug. È anche possibile abilitare la diagnostica per l'app Web nella configurazione e visualizzare i log registrati in Azure Application Insights. [Altre informazioni sull'abilitazione della registrazione diagnostica per le app Web](https://docs.microsoft.com/azure/app-service/web-sites-enable-diagnostic-log).

### <a name="connection-strings-and-application-settings"></a>Stringhe di connessione e impostazioni applicazione
Considerare la possibilità di usare [Azure KeyVault](https://docs.microsoft.com/azure/key-vault/), un servizio che archivia in modo sicuro le informazioni riservate usate nell'applicazione. In alternativa, è possibile archiviare questi dati come impostazione del servizio app.

### <a name="dns"></a>DNS
Potrebbe essere necessario aggiornare le configurazioni DNS in base ai requisiti dell'applicazione. Queste impostazioni DNS possono essere configurate nelle [impostazioni del dominio personalizzato](https://docs.microsoft.com/azure/app-service/app-service-web-tutorial-custom-domain) del servizio app.

## <a name="azure-app-service-with-windows-containers"></a>Servizio app di Azure i contenitori Windows
Se non è possibile eseguire la migrazione dell'applicazione direttamente nel servizio app, considerare la possibilità di usare i contenitori Windows, che consentono l'uso di GAC, componenti COM, MSI, accesso completo alle API .NET FX, DirectX e altro ancora.

## <a name="see-also"></a>Vedere anche

* [Come determinare se l'app è qualificata per il servizio app](https://appmigration.microsoft.com/)
* [Passaggio del database al cloud](https://go.microsoft.com/fwlink/?linkid=863217)
* [Dettagli e restrizioni della sandbox dell'app Web di AzureAzure web app sandbox details and restrictions](https://github.com/projectkudu/kudu/wiki/Azure-Web-App-sandbox)
