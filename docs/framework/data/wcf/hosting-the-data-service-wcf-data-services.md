---
title: Hosting del servizio dati (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 15122984dbaf3245436ff21836065c05131f71d1
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894323"
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Hosting del servizio dati (WCF Data Services)
Utilizzando WCF Data Services, è possibile creare un servizio che espone i dati come [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed. Questo servizio dati è definito come una classe che eredita da <xref:System.Data.Services.DataService%601>. Questa classe fornisce la funzionalità necessaria per elaborare i messaggi di richiesta, eseguire aggiornamenti sull'origine dati e generare messaggi di risposta, come richiesto da OData. Un servizio dati, tuttavia, non può eseguire l'associazione e l'ascolto su un socket di rete per le richieste HTTP in ingresso. Per questa funzionalità obbligatoria, il servizio dati si basa su un componente di hosting.

 L'host del servizio dati esegue le attività seguenti per conto del servizio dati:

- È in attesa delle richieste e le indirizza al servizio dati.

- Crea un'istanza del servizio dati per ogni richiesta.

- Richiede che il servizio dati elabori la richiesta in ingresso.

- Invia la risposta per conto del servizio dati.

 Per semplificare l'hosting di un servizio dati, WCF Data Services è progettato per l'integrazione con Windows Communication Foundation (WCF). Il servizio dati fornisce un'implementazione WCF predefinita che funge da host del servizio dati in un'applicazione ASP.NET. È pertanto possibile ospitare un servizio dati in uno dei modi seguenti:

- In un'applicazione ASP.NET.

- In un'applicazione gestita che supporta servizi WCF indipendenti.

- In un altro host del servizio dati personalizzato.

## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Hosting di un servizio dati in un'applicazione ASP.NET

Quando si usa la finestra di dialogo **Aggiungi nuovo elemento** in Visual Studio 2015 per definire un servizio dati in un'applicazione ASP.NET, lo strumento genera due nuovi file nel progetto. Il primo file presenta un'estensione `.svc` e indica al runtime WCF come creare un'istanza del servizio dati. Di seguito è riportato un esempio di questo file per il servizio dati di esempio Northwind creato al completamento della [Guida introduttiva](quickstart-wcf-data-services.md):

```aspx-csharp
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 Questa direttiva richiede all'applicazione la creazione dell'host del servizio per la classe di servizi dati denominata tramite la classe <xref:System.Data.Services.DataServiceHostFactory>.

 La pagina code-behind per il file `.svc` contiene la classe che corrisponde all'implementazione del servizio dati stesso, definita come segue per il servizio dati di esempio di Northwind:

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 Poiché un servizio dati si comporta come un servizio WCF, il servizio dati si integra con ASP.NET e segue il modello di programmazione Web WCF. Per ulteriori informazioni, vedere la pagina relativa ai [servizi WCF e](../../wcf/feature-details/wcf-services-and-aspnet.md) al [modello di programmazione HTTP Web](../../wcf/feature-details/wcf-web-http-programming-model.md)ASP.NET e WCF.

## <a name="self-hosted-wcf-services"></a>Servizi WCF indipendenti
 Poiché incorpora un'implementazione WCF, WCF Data Services supportano il self-hosting di un servizio dati come servizio WCF. Un servizio può essere indipendente in qualsiasi applicazione .NET Framework, ad esempio un'applicazione console. La classe <xref:System.Data.Services.DataServiceHost>, che eredita da <xref:System.ServiceModel.Web.WebServiceHost>, viene usata per creare un'istanza del servizio dati in un indirizzo specifico.

 Il self-hosting può essere usato per lo sviluppo e il test in quanto semplifica la distribuzione del servizio e la risoluzione dei relativi problemi. Questo tipo di hosting non fornisce tuttavia le funzionalità avanzate di gestione e hosting fornite da ASP.NET o da Internet Information Services (IIS). Per altre informazioni, vedere [hosting in un'applicazione gestita](../../wcf/feature-details/hosting-in-a-managed-application.md).

## <a name="defining-a-custom-data-service-host"></a>Definizione di un host del servizio dati personalizzato
 Per i casi in cui l'implementazione dell'host WCF è troppo restrittiva, è anche possibile definire un host personalizzato per un servizio dati. Qualsiasi classe che implementi l'interfaccia <xref:System.Data.Services.IDataServiceHost> può essere usata come host di rete per un servizio dati. Un host personalizzato deve implementare l'interfaccia <xref:System.Data.Services.IDataServiceHost> e deve essere in grado di gestire le responsabilità di base seguenti dell'host del servizio dati:

- Fornire al servizio dati il percorso radice del servizio.

- Elaborare le informazioni delle intestazioni di richieste e risposte per l'implementazione del membro <xref:System.Data.Services.IDataServiceHost> appropriato.

- Gestire le eccezioni generate dal servizio dati.

- Convalidare i parametri contenuti nella stringa di query.

## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Esposizione dei dati come un servizio](exposing-your-data-as-a-service-wcf-data-services.md)
- [Configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md)
