---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 7f21cd7ea600277461146387b962a89ea0a8472b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320631"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controllo dell'avvio automatico di Host servizio WCF
È possibile controllare la funzionalità di avvio automatico dell'host del servizio Windows Communication Foundation (WCF) (WcfSvcHost. exe) per un progetto libreria di servizi WCF, quando si esegue il debug di un altro progetto nella stessa soluzione di Visual Studio che contiene più progetti.  
  
 A tale scopo, fare clic con il pulsante destro del mouse sul progetto servizio WCF in **Esplora soluzioni**, scegliere **Proprietà**, quindi fare clic sulla scheda **opzioni WCF** . La casella di controllo **Avvia host del servizio WCF durante il debug di un altro progetto nella stessa soluzione** è abilitata per impostazione predefinita. È possibile deselezionare la casella in modo che l'host del servizio WCF per questo progetto specifico non venga avviato quando viene eseguito il debug di un altro progetto nella stessa soluzione.  
  
 Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.  
  
 Questa opzione è disponibile per i progetti seguenti:  
  
- Progetto libreria di servizi WCF.  
  
- Progetto Libreria di servizi del flusso di lavoro sequenziale.  
  
- Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.  
  
- Progetto Libreria di servizi di diffusione.  
  
## <a name="see-also"></a>Vedere anche

- [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
