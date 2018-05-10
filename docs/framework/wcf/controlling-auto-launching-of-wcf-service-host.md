---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 63c3ca00c0cdc0b28de0fe245b616acd04ca50fe
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controllo dell'avvio automatico di Host servizio WCF
È possibile controllare le funzionalità di avvio automatico dell'Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) per un progetto libreria di servizi WCF, quando si esegue il debug di un altro progetto nella stessa soluzione di Visual Studio contenente più progetti.  
  
 A tale scopo, fare clic sul progetto nel servizio WCF **Esplora soluzioni**, scegliere **delle proprietà**, fare clic su **opzioni WCF** scheda. Il **avvia Host servizio WCF durante il debug di un altro progetto nella stessa soluzione** casella di controllo è abilitata per impostazione predefinita. È possibile deselezionare la casella in modo che l'Host del servizio WCF per questo progetto specifico non venga avviato durante il debug di un altro progetto nella stessa soluzione.  
  
 Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.  
  
 Questa opzione è disponibile per i progetti seguenti:  
  
-   Progetto libreria di servizi WCF.  
  
-   Progetto Libreria di servizi del flusso di lavoro sequenziale.  
  
-   Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.  
  
-   Progetto Libreria di servizi di diffusione.  
  
## <a name="see-also"></a>Vedere anche  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
