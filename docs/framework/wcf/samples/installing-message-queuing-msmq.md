---
title: Installazione accodamento messaggi (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 118143f2d434e9f4399c3e9141743fc0254b61ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039616"
---
# <a name="installing-message-queuing-msmq"></a>Installazione accodamento messaggi (MSMQ)
Le procedure seguenti mostrano come installare Accodamento messaggi 4.0 e Accodamento messaggi 3.0.  
  
> [!NOTE]
> La versione 4.0 del sistema di accodamento dei messaggi non è disponibile in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows Server 2008 o in Windows Server 2008 R2  
  
1. In Server Manager fare clic su **funzionalità**.  
  
2. Nel riquadro di destra in **Riepilogo funzionalità**fare clic su **Aggiungi funzionalità**.  
  
3. Nella finestra risultante espandere Accodamento **messaggi**.  
  
4. Espandere **Servizi Accodamento messaggi**.  
  
5. Fare clic su **integrazione servizi directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto http**.  
  
6. Fare clic su **Avanti**, quindi su **Installa**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows 7 o in windows Vista  
  
1. Aprire il **Pannello di controllo**.  
  
2. Fare clic su **programmi** e quindi in **programmi e funzionalità**fare clic **su attivazione e disattivazione delle funzionalità Windows**.  
  
3. Espandere il server di accodamento messaggi Microsoft (MSMQ), espandere il server di base di accodamento messaggi Microsoft (MSMQ) e quindi selezionare le caselle di controllo per l’installazione delle funzionalità di Accodamento messaggi seguenti:  
  
    - Integrazione dei Servizi di dominio Active Directory MSMQ (per computer aggiunti a un Dominio).  
  
    - Supporto HTTP MSMQ.  
  
4. Fare clic su **OK**.  
  
5. Se viene richiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Per installare la versione 3.0 di Accodamento messaggi in Windows XP o Windows Server 2003  
  
1. Aprire il **Pannello di controllo**.  
  
2. Fare clic su **Aggiungi Rimuovi programmi** , quindi su **Aggiungi componenti di Windows**.  
  
3. Selezionare Accodamento messaggi e fare clic su **Dettagli**.  
  
    > [!NOTE]
    > Se è in esecuzione [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], selezionare Server applicazioni per accedere a Accodamento messaggi.  
  
4. Assicurarsi che l'opzione Supporto HTTP MSMQ sia selezionata nella pagina dei dettagli.  
  
5. Fare clic su **OK** per chiudere la pagina dei dettagli, quindi fare clic su **Avanti**. Completare l'installazione.  
  
6. Se viene richiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni di configurazione](../../../../docs/framework/wcf/samples/set-up-instructions.md)
