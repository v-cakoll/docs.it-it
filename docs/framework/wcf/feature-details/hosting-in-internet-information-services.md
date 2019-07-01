---
title: Host in Internet Information Services
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 3940d8436ba5441d4e884879213a7a782214cb05
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486756"
---
# <a name="hosting-in-internet-information-services"></a>Host in Internet Information Services
Una delle opzioni per l'hosting di servizi Windows Communication Foundation (WCF) è all'interno di un'applicazione Internet Information Services (IIS). Questo modello di hosting è simile al modello usato da ASP.NET e servizi Web (ASMX) i servizi Web ASP.NET.  
  
## <a name="versions-of-iis"></a>Versioni di IIS  
 WCF possono essere ospitati nelle versioni seguenti di IIS nei sistemi operativi seguenti:  
  
- IIS 5.1 su [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Questo ambiente è utile per la progettazione e lo sviluppo di applicazioni ospitate da IIS, successivamente distribuite in un sistema operativo server quale [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
- IIS 6.0 in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. IIS 6.0 fornisce un modello di processo avanzato che offre una migliore scalabilità, affidabilità e isolamento dell'applicazione. Questo ambiente è adatto per la distribuzione di produzione di servizi WCF che usano esclusivamente la comunicazione HTTP.  
  
- IIS 7.0 su [!INCLUDE[wv](../../../../includes/wv-md.md)] e [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7.0 offre lo stesso modello di processo avanzato di IIS 6.0, ma usa il servizio di attivazione processo Windows (WAS) per consentire l'attivazione e la comunicazione di rete su protocolli diversi da HTTP. Questo ambiente è adatto per lo sviluppo di servizi WCF che comunicano su qualsiasi protocollo di rete supportato da WCF (inclusi HTTP, NET. TCP, NET. pipe e NET. MSMQ). Per altre informazioni su WAS, vedere [Hosting nel servizio Attivazione processo Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
- [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) funziona con IIS 7.0 e Windows Process Activation Service (WAS) per fornire un ambiente per i servizi NET4 WCF e WF di hosting. Tali vantaggi includono la gestione del ciclo di vita del processo, il riciclo del processo, l'hosting condiviso, una rapida protezione dall'errore, la gestione dell'opzione orfano processo, l'attivazione su richiesta e il monitoraggio dello stato. Per informazioni dettagliate, vedere [funzionalità di Hosting di AppFabric](https://go.microsoft.com/fwlink/?LinkId=196494) e [concetti di Hosting](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vantaggi dell'hosting in IIS  
 Hosting di servizi WCF in IIS presenta diversi vantaggi:  
  
- Servizi WCF ospitati in IIS vengono distribuiti e gestiti come qualsiasi altro tipo di applicazione di IIS, incluse le applicazioni ASP.NET e ASMX.  
  
- IIS assicura l'attivazione dei processi, la gestione dello stato e il riciclo delle funzionalità, per aumentare l'affidabilità delle applicazioni ospitate.  
  
- Come ASP.NET, servizi WCF ospitati in ASP.NET possono sfruttare il modello di hosting condiviso di ASP.NET in cui più applicazioni risiedono in un processo di lavoro comuni per server maggiore densità e scalabilità.  
  
- Servizi WCF ospitati in IIS utilizzano lo stesso modello di compilazione dinamica come ASP.NET 2.0, che semplifica lo sviluppo e la distribuzione di servizi ospitati.  
  
 Quando si decide di ospitare servizi WCF in IIS, è importante ricordare che IIS 5.1 e 6.0 di IIS sono limitati alla sola comunicazione HTTP. Per altre informazioni sulla scelta di un ambiente di hosting, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Distribuzione di un servizio WCF ospitato in IIS  
 Lo sviluppo e distribuzione di un servizio WCF ospitato da IIS include le attività seguenti:  
  
- Verificare che IIS, ASP.NET, WCF e il componente di attivazione HTTP WCF siano installati e registrati correttamente.  
  
- Creare una nuova applicazione IIS o riusare un'applicazione ASP.NET esistente.  
  
- Creare un file con estensione svc del servizio WCF.  
  
- Distribuire l'implementazione del servizio nell'applicazione IIS.  
  
- Configurare il servizio WCF.  
  
 Per una descrizione di ognuna di queste attività, vedere [distribuzione di un servizio WCF ospitato](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Servizi WCF e ASP.NET  
 I servizi WCF possono essere ospitati entrambi side-by-side con ASP.NET o in modalità di compatibilità ASP.NET in cui i servizi possono usufruire delle funzionalità fornite dalla piattaforma dell'applicazione Web ASP.NET. Per una descrizione di queste funzionalità, vedere [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estensione dell'hosting tramite ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [Servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [Configurazione di Internet Information Services 7.0 per Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
