---
title: 'Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata'
ms.date: 03/30/2017
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
ms.openlocfilehash: 3d14d76334b15bdb490184a48da11ba48b84deea
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544654"
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata
Una prenotazione URL consente di limitare chi può ricevere messaggi da un URL o un set di URL. Una prenotazione è costituita da un modello di URL, un elenco di controllo di accesso (ACL) e un set di flag. Il modello di URL definisce quali URL sono interessati dalla prenotazione. Per altre informazioni su come vengono elaborati i modelli di URL, vedere [routing delle richieste in ingresso](https://go.microsoft.com/fwlink/?LinkId=136764). L'elenco ACL controlla a quale utente o gruppo di utenti è permesso ricevere messaggi dagli URL specificati. I flag indicano se la prenotazione deve fornire a un utente o a un gruppo l'autorizzazione per ascoltare direttamente l'URL o delegare l'autorizzazione per ascoltare qualche altro processo.  
  
 Come parte della configurazione del sistema operativo predefinita, Windows Communication Foundation (WCF) crea una prenotazione accessibile globalmente per la porta 80 per consentire a tutti gli utenti di eseguire applicazioni che usano un binding HTTP doppio per la comunicazione duplex. Poiché l'elenco ACL in questa prenotazione è per tutti, gli amministratori non possono consentire o impedire in modo esplicito l'autorizzazione all'ascolto di un URL o un set di URL. In questo argomento viene illustrato come eliminare questa prenotazione e come ricrearne una con un ACL limitato.  
  
In Windows Vista o Windows Server 2008 è possibile visualizzare tutte le prenotazioni URL HTTP da un prompt dei comandi con privilegi elevati immettendo `netsh http show urlacl`. Nell'esempio seguente viene illustrata la somiglianza di una prenotazione URL WCF:

```
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```

 La prenotazione è costituita da un modello di URL utilizzato quando un'applicazione WCF utilizza un'associazione duale HTTP per la comunicazione duplex. Gli URL di questo form vengono utilizzati per un servizio WCF per l'invio di messaggi al client WCF durante la comunicazione tramite un'associazione duale HTTP. Tutti vengono dotati di autorizzazione per ascoltare sull'URL ma non per delegare l'ascolto di un altro processo. Infine, l'elenco ACL viene descritto nel linguaggio SSDL (Security Descriptor Definition Language). Per ulteriori informazioni su SSDL, vedere [SSDL](https://go.microsoft.com/fwlink/?LinkId=136789) .  
  
## <a name="to-delete-the-wcf-url-reservation"></a>Per eliminare la prenotazione URL WCF  
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi** e scegliere **Esegui come amministratore** nel menu di scelta rapida che viene visualizzato. Fare clic su **continua** nella finestra controllo dell'account utente (UAC) che potrebbe richiedere le autorizzazioni per continuare.  
  
2. Digitare **netsh http delete urlacl url =http://+:80/Temporary_Listen_Addresses/** nella finestra del prompt dei comandi.  
  
3. Se la prenotazione viene eliminata correttamente, viene visualizzato il messaggio seguente. **La prenotazione URL è stata eliminata**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Creazione di un nuovo gruppo di sicurezza e una nuova prenotazione URL limitata  
 Per sostituire la prenotazione URL WCF con una prenotazione limitata è necessario prima creare un nuovo gruppo di sicurezza. Tale gruppo può essere creato da una finestra del prompt dei comandi o dalla console di gestione del computer. Occorre scegliere una delle due modalità.  
  
### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>Per creare un nuovo gruppo di sicurezza da un prompt dei comandi  
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi** e scegliere **Esegui come amministratore** nel menu di scelta rapida che viene visualizzato. Fare clic su **continua** nella finestra controllo dell'account utente (UAC) che potrebbe richiedere le autorizzazioni per continuare.  
  
2. Digitare **net localgroup "\<nome del gruppo di sicurezza >"/comment: "\<Descrizione del gruppo di sicurezza >"/Add** al prompt dei comandi. Sostituendo **\<nome del gruppo di sicurezza >** con il nome del gruppo di sicurezza che si vuole creare e **\<Descrizione del gruppo di sicurezza >** con una descrizione appropriata per il gruppo di sicurezza.  
  
3. Se il gruppo di sicurezza viene creato correttamente, viene visualizzato il messaggio seguente. **Il comando è stato completato correttamente.**  
  
### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>Per creare un nuovo gruppo di sicurezza dalla console di gestione del computer  
  
1. Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, fare clic su **strumenti di amministrazione**, quindi su **Gestione computer** per aprire la console di gestione computer. Fare clic su **continua** nella finestra controllo dell'account utente (UAC) che potrebbe richiedere le autorizzazioni per continuare.  
  
2. Fare clic su **utilità di sistema**, fare clic su **utenti e gruppi locali**, fare clic con il pulsante destro del mouse su **gruppi** cartella e scegliere **nuovo gruppo** dal menu di scelta rapida visualizzato. Digitare il nome del **gruppo**desiderato, la **Descrizione** e altri dettagli del nuovo gruppo di sicurezza e fare clic sul pulsante **Crea** per creare il gruppo di sicurezza.  
  
### <a name="to-create-the-restricted-url-reservation"></a>Per creare la prenotazione URL limitata  
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi** e scegliere **Esegui come amministratore** nel menu di scelta rapida che viene visualizzato. Fare clic su **continua** nella finestra controllo dell'account utente (UAC) che potrebbe richiedere le autorizzazioni per continuare.  
  
2. Digitare **netsh http add urlacl url =http://+:80/Temporary_Listen_Addresses/ User = "\< nome computer >\\ < nome del gruppo di sicurezza\>** al prompt dei comandi. Sostituendo **\<nome computer >** con il nome del computer in cui deve essere creato il gruppo e **\<nome del gruppo di sicurezza >** con il nome del gruppo di sicurezza creato in precedenza.  
  
3. Se la prenotazione viene creata correttamente, viene visualizzato il messaggio seguente. **Aggiunta della prenotazione URL completata**.
