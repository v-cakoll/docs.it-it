---
title: Host in Internet Information Services
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 588e069280afc369256fdbee0132f732348ffc37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494114"
---
# <a name="hosting-in-internet-information-services"></a>Host in Internet Information Services
Un'opzione di hosting dei servizi Windows Communication Foundation (WCF) è all'interno di un'applicazione Internet Information Services (IIS). Questo modello host è simile al modello usato da [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e dai servizi Web ASMX.  
  
## <a name="versions-of-iis"></a>Versioni di IIS  
 WCF può essere ospitato nelle versioni seguenti di IIS sui sistemi operativi seguenti:  
  
-   IIS 5.1 su [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Questo ambiente è utile per la progettazione e lo sviluppo di applicazioni ospitate da IIS, successivamente distribuite in un sistema operativo server quale [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] su [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] prevede un modello di processo avanzato che offre un migliore livello di scalabilità, affidabilità e isolamento dell'applicazione. Questo ambiente è adatto per la distribuzione di produzione dei servizi WCF che usano esclusivamente la comunicazione HTTP.  
  
-   IIS 7.0 su [!INCLUDE[wv](../../../../includes/wv-md.md)] e [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7.0 offre lo stesso modello di processo avanzato di [!INCLUDE[iis601](../../../../includes/iis601-md.md)], ma usa il servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) per consentire l'attivazione e la comunicazione di rete su protocolli diversi da HTTP. Questo ambiente è adatto per lo sviluppo di servizi WCF che comunicano su qualsiasi protocollo di rete supportato da WCF (inclusi HTTP, NET. TCP, NET. pipe e NET. MSMQ). Per ulteriori informazioni su WAS, vedere [Hosting nel servizio Attivazione processo Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) funziona con [!INCLUDE[iisver](../../../../includes/iisver-md.md)] e processo di attivazione Windows (WAS) per fornire un ambiente per i servizi NET4 WCF e WF di hosting. Tali vantaggi includono la gestione del ciclo di vita del processo, il riciclo del processo, l'hosting condiviso, una rapida protezione dall'errore, la gestione dell'opzione orfano processo, l'attivazione su richiesta e il monitoraggio dello stato. Per informazioni dettagliate, vedere [funzionalità di Hosting di AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494) e [concetti di Hosting di AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vantaggi dell'hosting in IIS  
 Hosting dei servizi WCF in IIS presenta diversi vantaggi:  
  
-   Servizi WCF ospitati in IIS vengono distribuiti e gestiti come qualsiasi altro tipo di applicazione IIS, tra cui [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applicazioni e ASMX.  
  
-   IIS assicura l'attivazione dei processi, la gestione dello stato e il riciclo delle funzionalità, per aumentare l'affidabilità delle applicazioni ospitate.  
  
-   Ad esempio [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], i servizi WCF ospitati in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] possono sfruttare il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] modello host condiviso in cui più applicazioni risiedono in un processo di lavoro comune per migliorare densità e server scalabilità.  
  
-   Servizi WCF ospitati in IIS utilizzano lo stesso modello di compilazione dinamica come [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], che semplifica lo sviluppo e distribuzione di servizi ospitati.  
  
 Quando si decide di ospitare servizi WCF in IIS, è importante ricordare che IIS 5.1 e [!INCLUDE[iis601](../../../../includes/iis601-md.md)] si limitano alla sola comunicazione HTTP. Per ulteriori informazioni sulla scelta di un ambiente di hosting, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Distribuzione di un servizio WCF ospitato in IIS  
 Lo sviluppo e distribuzione di un servizio WCF ospitato in IIS implicano le attività seguenti:  
  
-   Verificare che IIS, ASP.NET, WCF e il componente di attivazione HTTP WCF siano installati e registrati correttamente.  
  
-   Creare una nuova applicazione IIS o riusare un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] esistente.  
  
-   Creare un file con estensione svc per il servizio WCF.  
  
-   Distribuire l'implementazione del servizio nell'applicazione IIS.  
  
-   Configurare il servizio WCF.  
  
 Per una discussione su ognuna di queste attività, vedere [distribuzione di un servizio WCF ospitato](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Servizi WCF e ASP.NET  
 Servizi WCF possono essere ospitati entrambi side-by-side con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] modalità di compatibilità in cui i servizi possono sfruttare appieno le funzionalità fornite dal [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] piattaforma dell'applicazione Web. Per una discussione su queste funzionalità, vedere [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Estensione dell'hosting tramite ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [Servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Configurazione di Internet Information Services 7.0 per Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Windows Server AppFabric con funzionalità di Hosting](http://go.microsoft.com/fwlink/?LinkId=201276)
