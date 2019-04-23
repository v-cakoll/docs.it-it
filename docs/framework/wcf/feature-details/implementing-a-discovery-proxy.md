---
title: Implementazione di un proxy di individuazione
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 5d9296d8ba70d4c9e8d8339fa3a032d9c4c62826
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141002"
---
# <a name="implementing-a-discovery-proxy"></a>Implementazione di un proxy di individuazione
Contenuto della sezione vengono descritti i passaggi necessari per implementare un proxy di individuazione. Un proxy di individuazione è un servizio autonomo che contiene un repository di servizi. I client possono eseguire una query su un proxy di individuazione per cercare servizi individuabili noti al proxy. La modalità di popolamento di un proxy con i servizi dipende dall'implementatore. Un proxy di individuazione può ad esempio connettersi a un repository del servizio esistente e può rendere individuabili tali informazioni, un amministratore può usare un'interfaccia API di gestione per aggiungere servizi individuabili a un proxy o un proxy di individuazione può usare la funzionalità degli annunci per aggiornare la cache interna.  
  
 L'implementazione WCF fornisce classi di base che consentono di compilare con facilità un proxy. È possibile usare queste API per compilare un proxy di individuazione sul repository esistente.  
  
 Il proxy di individuazione implementato è simile a qualsiasi altro servizio WCF. È infatti possibile renderlo individuabile e fare in modo che i client ne individuino gli endpoint.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Implementare un Proxy di individuazione](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 Descrive come implementare un proxy di individuazione.  
  
 [Procedura: Implementare un servizio individuabile che esegue la registrazione al Proxy di individuazione](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Viene descritto come implementare un servizio WCF individuabile che esegue la registrazione al proxy di individuazione.  
  
 [Procedura: Implementare un'applicazione Client che usa il Proxy di individuazione per cercare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 Viene descritto come implementare un'applicazione client WCF che usa il proxy di individuazione per eseguire la ricerca per un servizio.  
  
 [Procedura: Testare il Proxy di individuazione](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 Descrive come testare il codice scritto nei tre argomenti precedenti.  
  
## <a name="see-also"></a>Vedere anche

- [WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [Procedura: A livello di codice aggiungere funzionalità di individuazione a un Client e servizio WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
