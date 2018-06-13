---
title: Uso di Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: bcd6543e6cd47dc723b308acebec6f492fa14fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489131"
---
# <a name="adopting-windows-communication-foundation"></a>Uso di Windows Communication Foundation
È possibile scegliere di utilizzare Windows Communication Foundation (WCF) per i nuovi sviluppi, mentre continuando a mantenere le applicazioni esistenti sviluppate tramite ASP.NET. Poiché WCF è destinato a essere la scelta più adatta per agevolare la comunicazione con le applicazioni compilate con .NET Framework in qualsiasi scenario, può fungere da uno strumento standard per la risoluzione di una vasta gamma di problemi di comunicazione software in modo che in ASP.NET non è possibile.  
  
 Le nuove applicazioni WCF possono essere distribuite nelle macchine stesse come servizi Web ASP.NET esistenti. Se i servizi Web ASP.NET esistenti utilizzano una versione di .NET Framework precedenti alla versione 2.0, è possibile utilizzare lo strumento di registrazione ASP.NET IIS per distribuire selettivamente .NET Framework 2.0 alle applicazioni di IIS in cui devono essere ospitate le nuove applicazioni WCF. Questo strumento è documentato al [strumento di registrazione ASP.NET IIS (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), ed è un'interfaccia utente incorporata la console di gestione IIS 6.0.  
  
 WCF può essere utilizzato per aggiungere nuove funzionalità ai servizi Web ASP.NET esistenti tramite l'aggiunta di servizi WCF configurati per l'esecuzione in modalità compatibile ASP.NET ad applicazioni di servizio Web ASP.NET esistenti in IIS. A causa delle modalità di compatibilità ASP.NET, il codice per i servizi WCF nuovi può accedere e aggiornare le informazioni sullo stato dell'applicazione stesso come il codice ASP.NET preesistente, utilizzando il <xref:System.Web.HttpContext> classe. Le applicazioni possono inoltre condividere le stesse librerie di classi.  
  
 I client WCF possono usare i servizi Web ASP.NET. Servizi WCF che sono configurati con il <xref:System.ServiceModel.BasicHttpBinding> può essere utilizzato dal client di servizi Web ASP.NET. Servizi Web ASP.NET possono coesistere con le applicazioni WCF e WCF può anche essere utilizzato per aggiungere funzionalità a servizi Web ASP.NET esistenti. Data tutte queste modalità in cui i servizi WCF e ASP.NET Web possono essere usati insieme, si può decidere di eseguire la migrazione di servizi Web ASP.NET a WCF solo se sono richieste funzionalità fornite dai servizi WCF e non Web ASP.NET.  
  
 Anche nei rari casi in cui si renda necessaria, valutare attentamente la migrazione di codice da una tecnologia a un'altra poiché questo approccio raramente si rivela corretto. L'utilizzo della nuova tecnologia è volto a soddisfare requisiti nuovi che non possono essere soddisfatti dalla precedente tecnologia e in tal caso la cosa corretta da fare è progettare una nuova soluzione in grado di soddisfare il nuovo set espanso di requisiti. La nuova progettazione si avvale dell'esperienza maturata con il sistema esistente e delle conoscenze acquisite nel frattempo. La nuova progettazione può inoltre utilizzare le funzionalità complete delle nuove tecnologie anziché riprodurre nella nuova piattaforma la progettazione precedente. Dopo aver creato gli elementi principali della nuova progettazione, diviene più semplice riutilizzare all'interno del nuovo sistema un codice proveniente dal sistema esistente.  
  
 Per solo nei rari casi in cui porting da servizi Web ASP.NET a WCF è la soluzione corretta, nella sezione seguente vengono fornite alcune indicazioni su come procedere. Vengono forniti suggerimenti per l'esecuzione della migrazione di servizi e di client.  
  
 Per un'analisi completa su come eseguire la migrazione di servizi Web ASP.NET esistenti a WCF, vedere [servizi Web ASP.NET e Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761). In questa sezione viene descritto come implementare un servizio conforme a WCF dai metadati per servizi Web ASP.NET e come eseguire la migrazione di codice di servizio e client Web ASP.NET a WCF.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Recuperare metadati e implementare un servizio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [Procedura: Eseguire la migrazione del codice dei servizi Web ASP.NET in Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [Procedura: Eseguire la migrazione del codice client dei servizi Web ASP.NET in Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
