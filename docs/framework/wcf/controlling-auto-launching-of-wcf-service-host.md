---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: f7f58a684449819fe945ad1ba5bff12f425c8294
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712392"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controllo dell'avvio automatico di Host servizio WCF
È possibile controllare la funzionalità avvio automatico dell'Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) per un progetto libreria di servizi WCF, quando si esegue il debug di un altro progetto nella stessa soluzione di Visual Studio che contiene più progetti.  
  
 A tale scopo, fare doppio clic il progetto di servizio WCF in **Esplora soluzioni**, scegliere **delle proprietà**, fare clic su **opzioni WCF** scheda. Il **avvia Host del servizio WCF durante il debug di un altro progetto nella stessa soluzione** casella di controllo è abilitata per impostazione predefinita. È possibile deselezionare la casella in modo che l'Host del servizio WCF per questo progetto specifico non viene avviata quando viene eseguito il debug di un altro progetto nella stessa soluzione.  
  
 Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.  
  
 Questa opzione è disponibile per i progetti seguenti:  
  
-   Progetto libreria di servizi WCF.  
  
-   Progetto Libreria di servizi del flusso di lavoro sequenziale.  
  
-   Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.  
  
-   Progetto Libreria di servizi di diffusione.  
  
## <a name="see-also"></a>Vedere anche
- [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
