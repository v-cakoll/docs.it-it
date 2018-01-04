---
title: 'Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4cfae36dfcb65dfd93dfc4fb1d6b64ba01e1b11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata
Una prenotazione URL consente di limitare chi può ricevere messaggi da un URL o un set di URL. Una prenotazione è costituita da un modello di URL, un elenco di controllo di accesso (ACL) e un set di flag. Il modello di URL definisce quali URL sono interessati dalla prenotazione. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]come vengono elaborati i modelli di URL, vedere [Routing delle richieste in ingresso](http://go.microsoft.com/fwlink/?LinkId=136764). L'elenco ACL controlla a quale utente o gruppo di utenti è permesso ricevere messaggi dagli URL specificati. I flag indicano se la prenotazione deve fornire a un utente o a un gruppo l'autorizzazione per ascoltare direttamente l'URL o delegare l'autorizzazione per ascoltare qualche altro processo.  
  
 Come parte della configurazione predefinita del sistema operativo, in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene creata una prenotazione globalmente accessibile per la porta 80 per consentire a tutti gli utenti di eseguire applicazioni che utilizzano un'associazione HTTP duale per la comunicazione duplex. Poiché l'elenco ACL in questa prenotazione è per tutti, gli amministratori non possono consentire o impedire in modo esplicito l'autorizzazione all'ascolto di un URL o un set di URL. In questo argomento viene illustrato come eliminare questa prenotazione e come ricrearne una con un ACL limitato.  
  
 In [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)] è possibile visualizzare tutte le prenotazioni URL HTTP da un prompt dei comandi con privilegi elevati digitando `netsh http show urlacl`.  Nell'esempio seguente viene mostrato l'aspetto di una prenotazione URL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 La prenotazione è costituita da un modello di URL che viene utilizzato quando un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza un'associazione duale HTTP per la comunicazione duplex. Gli URL di questo form vengono utilizzati per un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per restituire messaggi al client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durante la comunicazione in un'associazione duale HTTP. Tutti vengono dotati di autorizzazione per ascoltare sull'URL ma non per delegare l'ascolto di un altro processo. Infine, l'elenco ACL viene descritto nel linguaggio SSDL (Security Descriptor Definition Language). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SSDL, vedere [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>Per eliminare la prenotazione URL WCF  
  
1.  Fare clic su **avviare**, scegliere **tutti i programmi**, fare clic su **Accessori**, fare doppio clic su **prompt dei comandi** e fare clic su **runas Amministratore** nel menu di scelta rapida che viene visualizzato. Fare clic su **continua** nella finestra di controllo Account utente (UAC) che potrebbero essere richieste delle autorizzazioni per continuare.  
  
2.  Digitare **netsh http eliminare urlacl url = http: / / +:80/Temporary_Listen_Addresses/** nella finestra del prompt dei comandi.  
  
3.  Se la prenotazione viene eliminata correttamente, viene visualizzato il messaggio seguente. **Prenotazione URL eliminata**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Creazione di un nuovo gruppo di sicurezza e una nuova prenotazione URL limitata  
 Per sostituire la prenotazione URL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con una prenotazione limitata è necessario innanzitutto creare un nuovo gruppo di sicurezza. Tale gruppo può essere creato da una finestra del prompt dei comandi o dalla console di gestione del computer. Occorre scegliere una delle due modalità.  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>Per creare un nuovo gruppo di sicurezza da un prompt dei comandi  
  
1.  Fare clic su **avviare**, scegliere **tutti i programmi**, fare clic su **Accessori**, fare doppio clic su **prompt dei comandi** e fare clic su **runas Amministratore** nel menu di scelta rapida che viene visualizzato. Fare clic su **continua** nella finestra di controllo Account utente (UAC) che potrebbero essere richieste delle autorizzazioni per continuare.  
  
2.  Digitare **net localgroup "\<nome gruppo di sicurezza >" / commento: "\<descrizione del gruppo di sicurezza >" aggiungere** al prompt dei comandi. Sostituzione di  **\<nome gruppo di sicurezza >** con il nome del gruppo di sicurezza che si desidera creare e  **\<descrizione del gruppo di sicurezza >** con una descrizione adeguata per il gruppo di sicurezza.  
  
3.  Se il gruppo di sicurezza viene creato correttamente, viene visualizzato il messaggio seguente. **Comando completato correttamente.**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>Per creare un nuovo gruppo di sicurezza dalla console di gestione del computer  
  
1.  Fare clic su **avviare**, fare clic su **Pannello di controllo**, fare clic su **strumenti di amministrazione**, fare clic su **Gestione Computer** per aprire il Computer Console di gestione. Fare clic su **continua** nella finestra di controllo Account utente (UAC) che potrebbero essere richieste delle autorizzazioni per continuare.  
  
2.  Fare clic su **utilità di sistema**, fare clic su **utenti e gruppi locali**, fare doppio clic su **gruppi** cartella e fare clic su **nuovo gruppo** nel menu di scelta rapida che viene visualizzata. Tipo di oggetto desiderato **nome gruppo**, **descrizione** e altri dettagli di questo nuovo gruppo di sicurezza e fare clic su di **crea** pulsante per creare il gruppo di sicurezza.  
  
#### <a name="to-create-the-restricted-url-reservation"></a>Per creare la prenotazione URL limitata  
  
1.  Fare clic su **avviare**, scegliere **tutti i programmi**, fare clic su **Accessori**, fare doppio clic su **prompt dei comandi** e fare clic su **runas Amministratore** nel menu di scelta rapida che viene visualizzato. Fare clic su **continua** nella finestra di controllo Account utente (UAC) che potrebbero essere richieste delle autorizzazioni per continuare.  
  
2.  Digitare **netsh http aggiungere urlacl url = http: / / +: 80/Temporary_Listen_Addresses/utente = "\<nome computer >\\< nome gruppo di sicurezza\>**  al prompt dei comandi. Sostituzione di  **\<nome computer >** con il nome del computer in cui il gruppo deve essere creato e  **\<nome gruppo di sicurezza >** con il nome del gruppo di sicurezza è stato creato in precedenza.  
  
3.  Se la prenotazione viene creata correttamente, viene visualizzato il messaggio seguente. **Prenotazione URL aggiunta**.
