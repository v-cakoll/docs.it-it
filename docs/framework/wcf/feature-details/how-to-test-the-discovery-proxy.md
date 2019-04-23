---
title: 'Procedura: Testare il proxy di individuazione'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 856b86241299585b80d58c6d37582463736a5935
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316395"
---
# <a name="how-to-test-the-discovery-proxy"></a>Procedura: Testare il proxy di individuazione
Di seguito viene illustrato il quarto di quattro argomenti che indica come implementare un proxy di individuazione. Nell'argomento precedente, [come: Implementare un'applicazione Client che usa il Proxy di individuazione per cercare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), è stata implementata un'applicazione client WCF che usa il proxy di individuazione per trovare un servizio e quindi chiama il servizio. In questo argomento viene descritto come verificare che il proxy di individuazione, il servizio e l'applicazione client funzionino come previsto.  
  
### <a name="run-the-discovery-proxy"></a>Eseguire il proxy di individuazione  
  
1. Aprire un prompt dei comandi come amministratore.  
  
2. Potrebbe essere visualizzata una finestra di dialogo che afferma: Windows Firewall ha bloccato alcune funzionalità di questo programma. Se viene visualizzato questo messaggio, scegliere il **Unblock** pulsante.  
  
3. All'interno del prompt dei comandi eseguire il proxy di individuazione (DiscoveryProxy.exe).  
  
4. Nell'applicazione viene visualizzato il testo seguente: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Eseguire il servizio individuabile  
  
1. Aprire un prompt dei comandi come amministratore.  
  
2. Al prompt dei comandi eseguire il servizio individuabile Service.exe.  
  
3. Il DiscoveryProxy.exe viene visualizzato il testo seguente: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Eseguire l'applicazione client  
  
1. Aprire un prompt dei comandi.  
  
2. Al prompt dei comandi eseguire l'applicazione client.exe.  
  
3. Dopo alcuni secondi l'applicazione client Visualizza il testo seguente: La connessione a [Endpoint-servizio].  
  
4. Il service.exe viene quindi visualizzato il testo seguente: Il messaggio di saluto stata ricevuta una richiesta, risponderà.  
  
5. Il client.exe viene quindi visualizzato il testo seguente: Hello Client!  
  
### <a name="shut-down-the-applications"></a>Chiudere le applicazioni  
  
1. Chiudere l'applicazione client.  
  
2. Chiudere il servizio. Il proxy di individuazione visualizza il testo seguente: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3. Chiudere il proxy di individuazione  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Procedura: Implementare un Proxy di individuazione](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [Procedura: Implementare un servizio individuabile che esegue la registrazione al Proxy di individuazione](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [Procedura: Implementare un'applicazione Client che usa il Proxy di individuazione per cercare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
