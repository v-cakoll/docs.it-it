---
title: Uso di Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: 58a51f7ea0db2297c7151a752de3f54307e0c5fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643351"
---
# <a name="adopting-windows-communication-foundation"></a>Uso di Windows Communication Foundation

È possibile scegliere di utilizzare Windows Communication Foundation (WCF) per i nuovi sviluppi, mentre continuando a mantenere le applicazioni esistenti sviluppate tramite ASP.NET. Poiché WCF è destinato a essere la scelta più adatta per agevolare la comunicazione con applicazioni create con .NET Framework in qualsiasi scenario, che possa servire come uno strumento standard per la risoluzione di un'ampia gamma di problemi di comunicazione software in modo che in ASP.NET non è possibile.

Le nuove applicazioni WCF possono essere distribuite nelle macchine stesse come servizi Web ASP.NET esistenti. Se i servizi Web ASP.NET esistenti utilizzano una versione di .NET Framework precedenti alla versione 2.0, è possibile utilizzare lo strumento di registrazione ASP.NET IIS per distribuire selettivamente .NET Framework 2.0 alle applicazioni di IIS in cui devono essere ospitate le nuove applicazioni WCF. Tale strumento è documentato al [strumento di registrazione ASP.NET IIS (Aspnet_regiis.exe)](https://go.microsoft.com/fwlink/?LinkId=94687), e ha un'interfaccia utente incorporata nella console di gestione IIS 6.0.

WCF può essere utilizzato per aggiungere nuove funzionalità per servizi Web ASP.NET esistenti mediante l'aggiunta di servizi WCF configurati per l'esecuzione in modalità di compatibilità ASP.NET per applicazioni di servizio Web ASP.NET esistenti in IIS. A causa delle modalità di compatibilità ASP.NET, il codice per i nuovi servizi WCF può accedere e aggiornare le informazioni sullo stato dell'applicazione stesso come il codice ASP.NET preesistente, utilizzando il <xref:System.Web.HttpContext> classe. Le applicazioni possono inoltre condividere le stesse librerie di classi.

I client WCF possono utilizzare servizi Web ASP.NET. I servizi WCF che sono configurati con la <xref:System.ServiceModel.BasicHttpBinding> può essere utilizzato dai client del servizio Web ASP.NET. Servizi Web ASP.NET possono coesistere con le applicazioni WCF e WCF può anche essere utilizzato per aggiungere funzionalità a servizi Web ASP.NET esistenti. Tutte le modalità in cui i servizi Web ASP.NET e WCF possono essere usati insieme, è possibile eseguire la migrazione di servizi Web ASP.NET a WCF solo se sono necessarie funzionalità fornite da servizi non Web ASP.NET e WCF.

Anche in alcuni casi in cui è necessario, la migrazione di codice da una tecnologia a un altro raramente è l'approccio corretto. L'utilizzo della nuova tecnologia è volto a soddisfare requisiti nuovi che non possono essere soddisfatti dalla precedente tecnologia e in tal caso la cosa corretta da fare è progettare una nuova soluzione in grado di soddisfare il nuovo set espanso di requisiti. La nuova progettazione si avvale dell'esperienza maturata con il sistema esistente e delle conoscenze acquisite nel frattempo. La nuova progettazione può inoltre utilizzare le funzionalità complete delle nuove tecnologie anziché riprodurre nella nuova piattaforma la progettazione precedente. Dopo aver creato gli elementi principali della nuova progettazione, diviene più semplice riutilizzare all'interno del nuovo sistema un codice proveniente dal sistema esistente.

## <a name="see-also"></a>Vedere anche

- [Procedura: Recuperare i metadati e implementare un servizio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
