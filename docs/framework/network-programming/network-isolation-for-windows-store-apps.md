---
title: Isolamento rete per app di Windows Store
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 390a0281f03b08322cc1bee469b601fd5a1547c4
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802173"
---
# <a name="network-isolation-for-windows-store-apps"></a>Isolamento rete per app di Windows Store

È possibile usare le classi negli spazi dei nomi <xref:System.Net>, <xref:System.Net.Http>e <xref:System.Net.Http.Headers> per sviluppare app di Windows Store o applicazioni desktop. Quando vengono usati in un'app di Windows Store, le classi in questi spazi dei nomi sono interessate dall'isolamento rete, parte del modello di sicurezza dell'applicazione utilizzato da Windows 8. Le funzionalità di rete appropriate devono essere abilitate nel manifesto dell'app per un'app di Windows Store affinché il sistema consenta l'accesso alla rete.  
  
## <a name="checklist-for-network-isolation"></a>Elenco di controllo per l'isolamento rete  

Usare questo elenco di controllo per assicurarsi che l'isolamento rete sia configurato per l'app di Windows Store.  
  
1. Determinare la direzione delle richieste di accesso alla rete necessaria per l'app. Può trattarsi di richieste in uscita avviate dal client o di richieste in ingresso non sollecitate oppure di una combinazione di entrambi i tipi di richiesta di rete.  
  
2. Determinare il tipo di risorse di rete con cui comunicherà l'app. Un'app potrebbe avere l'esigenza di comunicare con risorse attendibili in una rete domestica o aziendale. Per un'app potrebbe essere necessario comunicare con risorse su Internet. Un'app potrebbe dover disporre dell'accesso a entrambi i tipi di risorse di rete.  
  
3. Configurare le funzionalità di isolamento rete minime richieste nel manifesto dell'app.  
  
4. Distribuire ed eseguire l'app per testarla usando gli strumenti di isolamento rete forniti per la risoluzione dei problemi.  
  
Per informazioni più dettagliate su come configurare le funzionalità di rete e gli strumenti di isolamento utilizzati per la risoluzione dei problemi di isolamento rete, vedere [come configurare le funzionalità di isolamento rete](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10)) nella documentazione per sviluppatori di Windows 8. x Store.
  
## <a name="see-also"></a>Vedere anche

- [Connecting to a web service](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10)) (Connessione a servizi Web)
- [Linee guida ed elenco di controllo per l'isolamento rete](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))
- [Quickstart: Connecting using HttpClient](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10)) (Guida introduttiva: Connessione tramite HttpClient)
- [How to use HttpClient handlers](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10)) (Come usare i gestori HttpClient)
- [How to secure HttpClient connections](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10)) (Come proteggere le connessioni HttpClient)
- [HttpClient Sample](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664) (Esempio con HttpClient)
