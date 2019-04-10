---
title: Istruzioni del firewall
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: f1b576b4e413fa3bae70ef1eb8f8ed768e28e309
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295159"
---
# <a name="firewall-instructions"></a>Istruzioni del firewall
È necessario abilitare più porte o programmi nel firewall in modo che possono funzionare gli esempi di Windows Communication Foundation (WCF). In molti degli esempi la comunicano avviene tramite le porte comprese nell'intervallo 8000-8003 e la porta 9000. Il firewall viene attivato per impostazione predefinita e impedisce l'accesso a queste porte. Per abilitare il firewall per gli esempi, completare una delle procedure descritte di seguito, a seconda dei requisiti e dell’ambiente di sicurezza:  
  
-   Opzione 1: Abilitare in modo interattivo gli esempi durante l'esecuzione. Non apportare nessuna modifica alla configurazione del firewall in anticipo e procedere con l’avvio e l’esecuzione degli esempi. Quando si esegue un esempio, un **avviso di sicurezza di Windows** verrà visualizzata la finestra di dialogo. Il programma di esempio in questione può essere quindi aggiunto, in modo interattivo, a un elenco sbloccato. Questa procedura può richiedere il riavvio dell'esempio.  
  
-   Opzione 2: Abilitare i programmi di esempio in anticipo. Avviare il **Pannello di controllo di Windows Firewall** applet e abilitare i programmi di esempio si intende eseguire. Per creare file eseguibili, è necessario prima compilare i programmi. Informazioni più dettagliate sono descritte nella procedura seguente.  
  
-   Opzione 3: Abilitare un intervallo di porte in anticipo. Avviare il **Windows Firewall** **Pannello di controllo** applet e abilitare le porte 80, 443, 8000-8003 e 9000, utilizzate dagli esempi. Informazioni più dettagliate sono descritte nella procedura seguente. Questa opzione è meno sicura rispetto alle altre in quanto consente a qualsiasi programma di utilizzare queste porte, non solo agli esempi.  
  
 In caso di dubbi su quale procedura utilizzare, scegliere la prima opzione. Se si sta eseguendo un firewall di un altro fornitore, potrebbe essere necessario apportare modifiche simili.  
  
> [!IMPORTANT]
>  La modifica della configurazione del firewall influisce sulla sicurezza. È consigliabile registrare le modifiche apportate e rimuoverle una volta completate le operazioni con gli esempi.  
  
### <a name="to-enable-samples-programs-in-advance"></a>Abilitazione dei programmi di esempio in anticipo.  
  
1. Compilare l'esempio.  
  
2. Fare clic su **avviare**, fare clic su **eseguito**e il tipo `firewall.cpl`. Verrà visualizzata la **Pannello di controllo di Windows Firewall** applet.  
  
    > [!NOTE]
    >  Per modificare le impostazioni del firewall ed eseguire gli esempi che richiedono la possibilità di comunicare con Windows Firewall, è necessario disporre delle autorizzazioni necessarie. Se alcune impostazioni del firewall non sono disponibili e il computer è connesso a un dominio, è possibile che queste impostazioni vengano controllate dall'amministratore di sistema tramite Criteri di gruppo.  
  
3. Completare uno dei passaggi operativi specifici seguente per consentire a un programma l'accesso con Windows Firewall:  
  
    -   In Windows 7 o Windows Server 2008 r2, fare clic su **consentono a un programma o funzionalità attraverso Windows Firewall**. Fare clic su **modificare le impostazioni**, consentire **un altro programma...** .  
  
    -   Sul [!INCLUDE[wv](../../../../includes/wv-md.md)] oppure [!INCLUDE[lserver](../../../../includes/lserver-md.md)], fare clic su **consentire a un programma attraverso Windows Firewall**.  
  
4. Nel **eccezioni** scheda, fare clic su **Aggiungi programma**.  
  
5. Scegliere il **esplorare** e selezionare il file eseguibile dell'esempio si prevede di eseguire.  
  
6. Ripetere i passaggi 4 e 5 finché vengono aggiunti i file eseguibili di tutti gli esempi che si intende eseguire.  
  
7. Fare clic su **OK** per chiudere l'applet del firewall.  
  
### <a name="to-enable-a-port-range-in-advance"></a>Abilitazione di un intervallo delle porte in anticipo.  
  
1. Fare clic su **avviare**, fare clic su **eseguito**e il tipo `firewall.cpl`. Verrà visualizzata la **Pannello di controllo di Windows Firewall** applet.  
  
2. In Windows 7 o Windows Server 2008 R2 attenersi alla procedura seguente:  
  
    1.  Fare clic su **impostazioni avanzate** nella colonna sinistra della finestra di Windows Firewall.  
  
    2.  Fare clic su **regole connessioni in entrata** nella colonna sinistra.  
  
    3.  Fare clic su **nuove regole** nella colonna destra.  
  
    4.  Selezionare **porta** e fare clic su **successivo**.  
  
    5.  Selezionare **TCP** e immettere `8000, 8001, 8002, 8003, 9000, 80, 443` nel **porte locali specifiche** campo.  
  
    6.  Scegliere **Avanti**.  
  
    7.  Selezionare **Consenti solo connessioni**, fare clic su **successivo** .  
  
    8.  Selezionare **Domain** e **privato**, fare clic su **Next**.  
  
    9. Denominare la regola `WCF-WF 4.0 Samples`, fare clic su **fine**.  
  
    10. Fare clic su **regole in uscita** e ripetere i passaggi da c a h.  
  
3. In [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)] attenersi alla procedura seguente:  
  
    1.  Fare clic su **consentire a un programma attraverso Windows Firewall**.  
  
    2.  Nel **eccezioni** scheda, fare clic su **Aggiungi porta**.  
  
    3.  Immettere un nome, immettere 8000 come numero di porta e selezionare il **TCP** opzione.  
  
    4.  Fare clic sui **Cambia ambito** pulsante, seleziona la **rete personale** unica opzione disponibile (subnet) e fare clic su **OK**.  
  
    5.  Ripetere i passaggi da B a D per le porte 8001, 8002, 8003, 9000, 80 e 443.  
  
4. Fare clic su **OK** per chiudere l'applet del firewall.  
  
> [!NOTE]
>  Rimuovere qualsiasi eccezione del firewall una volta completate le operazioni con gli esempi. A tale scopo, aprire il **Pannello di controllo di Windows Firewall** applet e rimuovere eventuali programmi o trasferire le voci che sono state aggiunte alle procedure precedenti.
