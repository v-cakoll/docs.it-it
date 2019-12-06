---
title: Host in Internet Information Services
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 8ea7602e82d13425bb678555dde1f44ccbbf5a0f
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837467"
---
# <a name="hosting-in-internet-information-services"></a>Host in Internet Information Services
Un'opzione per l'hosting di servizi di Windows Communication Foundation (WCF) si trova all'interno di un'applicazione Internet Information Services (IIS). Questo modello di hosting è simile al modello usato dai servizi Web ASP.NET e ASP.NET Web Services (ASMX).  
  
## <a name="versions-of-iis"></a>Versioni di IIS  
 WCF può essere ospitato nelle versioni seguenti di IIS nei sistemi operativi seguenti:  
  
- IIS 5.1 su [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Questo ambiente è utile per la progettazione e lo sviluppo di applicazioni ospitate da IIS, successivamente distribuite in un sistema operativo server quale [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
- IIS 6,0 in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. IIS 6,0 fornisce un modello di processo avanzato che offre maggiore scalabilità, affidabilità e isolamento delle applicazioni. Questo ambiente è adatto per la distribuzione di produzione di servizi WCF che utilizzano esclusivamente la comunicazione HTTP.  
  
- IIS 7,0 in Windows Vista e [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7,0 fornisce lo stesso modello di processo avanzato di IIS 6,0, ma utilizza il servizio di attivazione dei processi di Windows per consentire l'attivazione e la comunicazione di rete su protocolli diversi da HTTP. Questo ambiente è adatto per lo sviluppo di servizi WCF che comunicano su qualsiasi protocollo di rete supportato da WCF (compresi HTTP, NET. TCP, NET. pipe e NET. MSMQ). Per ulteriori informazioni su WAS, vedere [hosting nel servizio di attivazione dei processi di Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
- [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) funziona con IIS 7,0 e il servizio Attivazione processo Windows (was) per fornire un ambiente di hosting di applicazioni completo per i servizi WCF e WF NET4. Tali vantaggi includono la gestione del ciclo di vita del processo, il riciclo del processo, l'hosting condiviso, una rapida protezione dall'errore, la gestione dell'opzione orfano processo, l'attivazione su richiesta e il monitoraggio dello stato. Per informazioni dettagliate, vedere [funzionalità di hosting di AppFabric](https://go.microsoft.com/fwlink/?LinkId=196494) e [concetti di hosting di AppFabric](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vantaggi dell'hosting in IIS  
 L'hosting di servizi WCF in IIS presenta diversi vantaggi:  
  
- I servizi WCF ospitati in IIS vengono distribuiti e gestiti in modo analogo a qualsiasi altro tipo di applicazione IIS, incluse le applicazioni ASP.NET e ASMX.  
  
- IIS assicura l'attivazione dei processi, la gestione dello stato e il riciclo delle funzionalità, per aumentare l'affidabilità delle applicazioni ospitate.  
  
- Analogamente a ASP.NET, i servizi WCF ospitati in ASP.NET possono sfruttare il modello di hosting condiviso ASP.NET in cui più applicazioni si trovano in un processo di lavoro comune per migliorare la densità e la scalabilità del server.  
  
- I servizi WCF ospitati in IIS utilizzano lo stesso modello di compilazione dinamica di ASP.NET 2,0, che semplifica lo sviluppo e la distribuzione di servizi ospitati.  
  
 Quando si decide di ospitare i servizi WCF in IIS, è importante ricordare che IIS 5,1 e IIS 6,0 sono limitati solo alla comunicazione HTTP. Per ulteriori informazioni sulla scelta di un ambiente host, vedere [servizi di hosting](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Distribuzione di un servizio WCF ospitato in IIS  
 Lo sviluppo e la distribuzione di un servizio WCF ospitato da IIS è costituito dalle attività seguenti:  
  
- Verificare che IIS, ASP.NET, WCF e il componente di attivazione HTTP WCF siano installati e registrati correttamente.  
  
- Creare una nuova applicazione IIS o riutilizzare un'applicazione ASP.NET esistente.  
  
- Creare un file con estensione svc per il servizio WCF.  
  
- Distribuire l'implementazione del servizio nell'applicazione IIS.  
  
- Configurare il servizio WCF.  
  
 Per una descrizione di ciascuna di queste attività, vedere [distribuzione di un servizio WCF ospitato in Internet Information Services](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Servizi WCF e ASP.NET  
 I servizi WCF possono essere ospitati side-by-side con ASP.NET o in modalità di compatibilità ASP.NET in cui i servizi possono sfruttare appieno le funzionalità offerte dalla piattaforma di applicazioni Web ASP.NET. Per una descrizione di queste funzionalità, vedere [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estensione dell'hosting tramite ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [Servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [Configurazione di Internet Information Services 7.0 per Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
