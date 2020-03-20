---
title: Isolamento rete per app di Windows Store
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 390a0281f03b08322cc1bee469b601fd5a1547c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74802173"
---
# <a name="network-isolation-for-windows-store-apps"></a>Isolamento rete per app di Windows Store

Le classi <xref:System.Net> <xref:System.Net.Http>negli <xref:System.Net.Http.Headers> spazi dei nomi , e possono essere usate per sviluppare app di Windows Store o app desktop. Se usate in un'app di Windows Store, le classi in questi spazi dei nomi sono interessate dall'isolamento della rete, parte del modello di sicurezza dell'applicazione usato da Windows 8. Le funzionalità di rete appropriate devono essere abilitate nel manifesto dell'app per un'app di Windows Store affinché il sistema consenta l'accesso alla rete.  
  
## <a name="checklist-for-network-isolation"></a>Elenco di controllo per l'isolamento rete  

Usare questo elenco di controllo per assicurarsi che l'isolamento rete sia configurato per l'app di Windows Store.  
  
1. Determinare la direzione delle richieste di accesso alla rete necessaria per l'app. Può trattarsi di richieste in uscita avviate dal client o di richieste in ingresso non sollecitate oppure di una combinazione di entrambi i tipi di richiesta di rete.  
  
2. Determinare il tipo di risorse di rete con cui comunicherà l'app. Un'app potrebbe avere l'esigenza di comunicare con risorse attendibili in una rete domestica o aziendale. Per un'app potrebbe essere necessario comunicare con risorse su Internet. Un'app potrebbe dover disporre dell'accesso a entrambi i tipi di risorse di rete.  
  
3. Configurare le funzionalità di isolamento rete minime richieste nel manifesto dell'app.  
  
4. Distribuire ed eseguire l'app per testarla usando gli strumenti di isolamento rete forniti per la risoluzione dei problemi.  
  
Per informazioni più dettagliate su come configurare le funzionalità di rete e gli strumenti di isolamento utilizzati per la risoluzione dei problemi di isolamento rete, vedere [Come configurare le funzionalità](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10)) di isolamento rete nella documentazione per gli sviluppatori di Windows 8.x Store.
  
## <a name="see-also"></a>Vedere anche

- [Connessione a servizi Web](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10))
- [Linee guida ed elenco di controllo per l'isolamento rete](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))
- [Quickstart: Connecting using HttpClient](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10)) (Guida introduttiva: Connessione tramite HttpClient)
- [How to use HttpClient handlers (Come usare i gestori HttpClient)](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10))
- [How to secure HttpClient connections (Come proteggere le connessioni HttpClient)](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10))
- [HttpClient Sample](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664) (Esempio con HttpClient)
