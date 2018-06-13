---
title: Installazione accodamento messaggi (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: b54fab13d644cafda8a070280d672c60cf71b675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501468"
---
# <a name="installing-message-queuing-msmq"></a>Installazione accodamento messaggi (MSMQ)
Le procedure seguenti mostrano come installare Accodamento messaggi 4.0 e Accodamento messaggi 3.0.  
  
> [!NOTE]
>  La versione 4.0 del sistema di accodamento dei messaggi non è disponibile in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows Server 2008 o in Windows Server 2008 R2  
  
1.  In Server Manager, fare clic su **funzionalità**.  
  
2.  Nel riquadro destro, in **Riepilogo funzionalità**, fare clic su **Aggiungi funzionalità**.  
  
3.  Nella finestra risulta, espandere **Accodamento**.  
  
4.  Espandere **servizi di accodamento dei messaggi**.  
  
5.  Fare clic su **integrazione servizi Directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto HTTP**.  
  
6.  Fare clic su **Avanti**, quindi fare clic su **installare**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows 7 o in windows Vista  
  
1.  Aprire il **Pannello di controllo**.  
  
2.  Fare clic su **programmi** e quindi in **programmi e funzionalità**, fare clic su **funzionalità di Windows di attivare e disattivare**.  
  
3.  Espandere il server di accodamento messaggi Microsoft (MSMQ), espandere il server di base di accodamento messaggi Microsoft (MSMQ) e quindi selezionare le caselle di controllo per l’installazione delle funzionalità di Accodamento messaggi seguenti:  
  
    -   Integrazione dei Servizi di dominio Active Directory MSMQ (per computer aggiunti a un Dominio).  
  
    -   Supporto HTTP MSMQ.  
  
4.  Fare clic su **OK**.  
  
5.  Se viene chiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Per installare la versione 3.0 di Accodamento messaggi in Windows XP o Windows Server 2003  
  
1.  Aprire il **Pannello di controllo**.  
  
2.  Fare clic su **Installazione applicazioni** e quindi fare clic su **Installazione componenti di Windows**.  
  
3.  Selezionare il servizio Accodamento messaggi e fare clic su **dettagli**.  
  
    > [!NOTE]
    >  Se è in esecuzione [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], selezionare Server applicazioni per accedere a Accodamento messaggi.  
  
4.  Assicurarsi che l'opzione Supporto HTTP MSMQ sia selezionata nella pagina dei dettagli.  
  
5.  Fare clic su **OK** per uscire dalla pagina dei dettagli, quindi fare clic su **Avanti**. Completare l'installazione.  
  
6.  Se viene chiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzioni di configurazione](../../../../docs/framework/wcf/samples/set-up-instructions.md)
