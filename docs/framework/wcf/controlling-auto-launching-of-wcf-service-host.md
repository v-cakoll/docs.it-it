---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: fe936ee3ff42b586c733de597de808b86f3e2575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controllo dell'avvio automatico di Host servizio WCF
È possibile controllare le funzionalità di avvio automatico dell'Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) per un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] progetto libreria di servizi, quando si esegue il debug di un altro progetto nella stessa soluzione di Visual Studio contenente più progetti .  
  
 A tale scopo, fare doppio clic su di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] progetto di servizio in **Esplora**, scegliere **proprietà**, fare clic su **opzioni WCF** scheda. Il **avvia Host servizio WCF durante il debug di un altro progetto nella stessa soluzione** casella di controllo è abilitata per impostazione predefinita. È possibile deselezionare la casella in modo che l'host del servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per questo progetto specifico non venga avviato durante il debug di un altro progetto nella stessa soluzione.  
  
 Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.  
  
 Questa opzione è disponibile per i progetti seguenti:  
  
-   Progetto Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Progetto Libreria di servizi del flusso di lavoro sequenziale.  
  
-   Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.  
  
-   Progetto Libreria di servizi di diffusione.  
  
## <a name="see-also"></a>Vedere anche  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
