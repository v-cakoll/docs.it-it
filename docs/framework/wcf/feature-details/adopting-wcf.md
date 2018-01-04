---
title: Uso di Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 522d4d39df6df62a6bed2fdc9f6d72df1193faca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="adopting-windows-communication-foundation"></a>Uso di Windows Communication Foundation
È possibile scegliere di utilizzare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per lo sviluppo di nuove applicazioni, continuando a mantenere le applicazioni esistenti sviluppate tramite ASP.NET. Poiché [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene proposto come la scelta più adatta per agevolare la comunicazione con applicazioni generate con .NET Framework in qualsiasi scenario, a differenza di ASP.NET, può essere utilizzato come strumento standard per la risoluzione di un'ampia gamma di problemi di comunicazione software.  
  
 Le nuove applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono essere distribuite negli stessi computer in cui si trovano i servizi Web ASP.NET esistenti. Se i servizi Web ASP.NET esistenti utilizzano una versione di .NET Framework precedente alla versione 2.0, è possibile utilizzare lo strumento di registrazione ASP.NET IIS per distribuire selettivamente .NET Framework 2.0 alle applicazioni IIS in cui devono essere ospitate le nuove applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Questo strumento è documentato al [strumento di registrazione ASP.NET IIS (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), ed è un'interfaccia utente incorporata la console di gestione IIS 6.0.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può essere utilizzato per aggiungere nuove funzionalità ai servizi Web ASP.NET esistenti. A tale scopo aggiungere servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurati per l'esecuzione in modalità compatibile ASP.NET ad applicazioni di servizi Web ASP.NET esistenti in IIS. Data la modalità di compatibilità ASP.NET, il codice per i nuovi servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può accedere e aggiornare le stesse informazioni sullo stato dell'applicazione del codice ASP.NET preesistente, utilizzando la classe <xref:System.Web.HttpContext>. Le applicazioni possono inoltre condividere le stesse librerie di classi.  
  
 I client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono utilizzare i servizi Web ASP.NET. I servizi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurati con <xref:System.ServiceModel.BasicHttpBinding> possono essere utilizzati dai client di servizi Web ASP.NET. I servizi Web ASP.NET possono coesistere con le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può anche essere utilizzato per aggiungere funzionalità ai servizi Web ASP.NET esistenti. Date le numerose possibilità di utilizzo congiunto di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e dei servizi Web ASP.NET, è consigliabile eseguire la migrazione di servizi Web ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] solo se sono richieste funzionalità fornite da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e non da servizi Web ASP.NET.  
  
 Anche nei rari casi in cui si renda necessaria, valutare attentamente la migrazione di codice da una tecnologia a un'altra poiché questo approccio raramente si rivela corretto. L'utilizzo della nuova tecnologia è volto a soddisfare requisiti nuovi che non possono essere soddisfatti dalla precedente tecnologia e in tal caso la cosa corretta da fare è progettare una nuova soluzione in grado di soddisfare il nuovo set espanso di requisiti. La nuova progettazione si avvale dell'esperienza maturata con il sistema esistente e delle conoscenze acquisite nel frattempo. La nuova progettazione può inoltre utilizzare le funzionalità complete delle nuove tecnologie anziché riprodurre nella nuova piattaforma la progettazione precedente. Dopo aver creato gli elementi principali della nuova progettazione, diviene più semplice riutilizzare all'interno del nuovo sistema un codice proveniente dal sistema esistente.  
  
 Nella sezione seguente vengono forniti consigli sul trasferimento dai servizi Web ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], da utilizzare solo nei rari casi in cui tale trasferimento si riveli la soluzione corretta. Vengono forniti suggerimenti per l'esecuzione della migrazione di servizi e di client.  
  
 Per un'analisi completa su come eseguire la migrazione di servizi Web ASP.NET esistenti a WCF, vedere [servizi Web ASP.NET e Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761). Contenuto della sezione viene descritto come implementare un servizio conforme a WCF dai metadati per servizi Web ASP.NET e come eseguire la migrazione di servizi Web e del codice client ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Recuperare metadati e implementare un servizio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [Procedura: Eseguire la migrazione del codice dei servizi Web ASP.NET in Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [Procedura: Eseguire la migrazione del codice client dei servizi Web ASP.NET in Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
