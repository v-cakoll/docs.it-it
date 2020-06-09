---
title: Implementazione di un proxy di individuazione
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 382df95fef2108d338e4ea327da9185c856eca5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579241"
---
# <a name="implementing-a-discovery-proxy"></a>Implementazione di un proxy di individuazione
Contenuto della sezione vengono descritti i passaggi necessari per implementare un proxy di individuazione. Un proxy di individuazione è un servizio autonomo che contiene un repository di servizi. I client possono eseguire una query su un proxy di individuazione per cercare servizi individuabili noti al proxy. La modalità di popolamento di un proxy con i servizi dipende dall'implementatore. Un proxy di individuazione può ad esempio connettersi a un repository del servizio esistente e può rendere individuabili tali informazioni, un amministratore può usare un'interfaccia API di gestione per aggiungere servizi individuabili a un proxy o un proxy di individuazione può usare la funzionalità degli annunci per aggiornare la cache interna.  
  
 L'implementazione WCF fornisce classi di base che consentono di compilare con facilità un proxy. È possibile usare queste API per compilare un proxy di individuazione sul repository esistente.  
  
 Il proxy di individuazione implementato è simile a qualsiasi altro servizio WCF. È infatti possibile renderlo individuabile e fare in modo che i client ne individuino gli endpoint.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: implementare un proxy di individuazione](how-to-implement-a-discovery-proxy.md)  
 Descrive come implementare un proxy di individuazione.  
  
 [Procedura: implementare un servizio individuabile che esegue la registrazione al proxy di individuazione](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Viene descritto come implementare un servizio WCF individuabile che esegue la registrazione con il proxy di individuazione.  
  
 [Procedura: implementare un'applicazione client che usa il proxy di individuazione per cercare un servizio](client-app-discovery-proxy-to-find-a-service.md)  
 Viene descritto come implementare un'applicazione client WCF che utilizza il proxy di individuazione per cercare un servizio.  
  
 [Procedura: test del proxy di individuazione](how-to-test-the-discovery-proxy.md)  
 Descrive come testare il codice scritto nei tre argomenti precedenti.  
  
## <a name="see-also"></a>Vedere anche

- [WCF Discovery](wcf-discovery.md)
- [Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
