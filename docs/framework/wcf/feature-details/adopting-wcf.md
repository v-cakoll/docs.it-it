---
title: Uso di Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: e4955d3a1d1c3a7c2afae5b0e1573d383e03bb33
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116657"
---
# <a name="adopt-windows-communication-foundation"></a>Adottare Windows Communication Foundation

È possibile scegliere di usare Windows Communication Foundation (WCF) per il nuovo sviluppo continuando a mantenere le applicazioni esistenti sviluppate con ASP.NET. Poiché WCF è la scelta più adatta per facilitare la comunicazione con le applicazioni compilate con il .NET Framework in qualsiasi scenario, può fungere da strumento standard per la risoluzione di un'ampia gamma di problemi di comunicazione software in modo da ASP.NET non.

Le nuove applicazioni WCF possono essere distribuite nelle stesse macchine dei servizi Web ASP.NET esistenti. Se i servizi Web ASP.NET esistenti utilizzano una versione del .NET Framework precedente alla versione 2,0, è possibile utilizzare lo strumento di registrazione IIS ASP.NET per distribuire in modo selettivo le .NET Framework 2,0 alle applicazioni IIS in cui sono ospitate le nuove applicazioni WCF. Tale strumento è documentato in [ASP.NET IIS Registration Tool (Aspnet_regiis. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))e dispone di un'interfaccia utente incorporata nella console di gestione IIS 6,0.

È possibile utilizzare WCF per aggiungere nuove funzionalità ai servizi Web ASP.NET esistenti mediante l'aggiunta di servizi WCF configurati per l'esecuzione in modalità di compatibilità ASP.NET a applicazioni del servizio Web ASP.NET esistenti in IIS. A causa della modalità di compatibilità ASP.NET, il codice per i nuovi servizi WCF può accedere e aggiornare le stesse informazioni sullo stato dell'applicazione del codice ASP.NET preesistente usando la classe <xref:System.Web.HttpContext>. Le applicazioni possono inoltre condividere le stesse librerie di classi.

I client WCF possono usare i servizi Web ASP.NET. I servizi WCF configurati con il <xref:System.ServiceModel.BasicHttpBinding> possono essere utilizzati dai client del servizio Web ASP.NET. I servizi Web ASP.NET possono coesistere con le applicazioni WCF e WCF può anche essere usato per aggiungere funzionalità ai servizi Web ASP.NET esistenti. Considerati tutti i modi in cui è possibile utilizzare insieme i servizi Web WCF e ASP.NET, è possibile eseguire la migrazione di servizi Web ASP.NET a WCF solo se sono necessarie funzionalità fornite da WCF e non da servizi Web ASP.NET.

Anche nei pochi casi in cui è necessario, la migrazione del codice da una tecnologia all'altra è raramente l'approccio corretto. Il motivo per cui si adotta la nuova tecnologia è soddisfare i nuovi requisiti che non possono essere soddisfatti con la tecnologia precedente e, in tal caso, la cosa corretta da fare è progettare una nuova soluzione per soddisfare il set di requisiti appena espanso. La nuova progettazione si avvale dell'esperienza maturata con il sistema esistente e delle conoscenze acquisite nel frattempo. La nuova progettazione può inoltre utilizzare le funzionalità complete delle nuove tecnologie anziché riprodurre nella nuova piattaforma la progettazione precedente. Dopo la creazione di prototipi degli elementi chiave della nuova progettazione, diventa più facile riutilizzare il codice del sistema esistente all'interno di quello nuovo.

## <a name="see-also"></a>Vedere anche

- [Procedura: Recuperare metadati e implementare un servizio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
