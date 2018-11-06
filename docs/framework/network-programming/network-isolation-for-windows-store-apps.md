---
title: Isolamento rete per app di Windows Store
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 537d94201b3e0ae92707c858f10032848a690004
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182671"
---
# <a name="network-isolation-for-windows-store-apps"></a>Isolamento rete per app di Windows Store
Le classi negli spazi dei nomi <xref:System.Net>, <xref:System.Net.Http> e <xref:System.Net.Http.Headers> possono essere usate per sviluppare app di Windows Store o app desktop. Quando vengono usate in un'app di Windows Store, le classi in questi spazi dei nomi sono interessate dall'isolamento rete, parte del modello di sicurezza delle applicazioni usato da [!INCLUDE[win8](../../../includes/win8-md.md)]. Le funzionalità di rete appropriate devono essere abilitate nel manifesto dell'app per un'app di Windows Store affinché il sistema consenta l'accesso alla rete.  
  
## <a name="checklist-for-network-isolation"></a>Elenco di controllo per l'isolamento rete  
 Usare questo elenco di controllo per assicurarsi che l'isolamento rete sia configurato per l'app di Windows Store.  
  
1.  Determinare la direzione delle richieste di accesso alla rete necessaria per l'app. Può trattarsi di richieste in uscita avviate dal client o di richieste in ingresso non sollecitate oppure di una combinazione di entrambi i tipi di richiesta di rete.  
  
2.  Determinare il tipo di risorse di rete con cui comunicherà l'app. Un'app potrebbe avere l'esigenza di comunicare con risorse attendibili in una rete domestica o aziendale. Per un'app potrebbe essere necessario comunicare con risorse su Internet. Un'app potrebbe dover disporre dell'accesso a entrambi i tipi di risorse di rete.  
  
3.  Configurare le funzionalità di isolamento rete minime richieste nel manifesto dell'app.  
  
4.  Distribuire ed eseguire l'app per testarla usando gli strumenti di isolamento rete forniti per la risoluzione dei problemi.  
  
 Per informazioni più dettagliate su come configurare le funzionalità di rete e gli strumenti di isolamento usati per la risoluzione dei problemi dell'isolamento rete, vedere [Come impostare le funzionalità di rete](https://go.microsoft.com/fwlink/?LinkID=228265) nella documentazione per gli sviluppatori di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Connecting to a web service](https://go.microsoft.com/fwlink/?LinkID=245696) (Connessione a servizi Web)  
 [Linee guida ed elenco di controllo per l'isolamento rete](https://go.microsoft.com/fwlink/?LinkID=228265)  
 [Quickstart: Connecting using HttpClient](https://go.microsoft.com/fwlink/?LinkId=245697) (Guida introduttiva: Connessione tramite HttpClient)  
 [How to use HttpClient handlers](https://go.microsoft.com/fwlink/?LinkId=245699) (Come usare i gestori HttpClient)  
 [How to secure HttpClient connections](https://go.microsoft.com/fwlink/?LinkId=245698) (Come proteggere le connessioni HttpClient)  
 [HttpClient Sample](https://go.microsoft.com/fwlink/?LinkId=242550) (Esempio con HttpClient)
