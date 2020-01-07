---
title: Istruzioni del firewall
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: e2c4dd8e784599a5e110e7454d9d0e709cbc5776
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544786"
---
# <a name="firewall-instructions"></a>Istruzioni del firewall
È necessario abilitare più porte o programmi nel firewall in modo che gli esempi di Windows Communication Foundation (WCF) possano funzionare. In molti degli esempi la comunicano avviene tramite le porte comprese nell'intervallo 8000-8003 e la porta 9000. Il firewall viene attivato per impostazione predefinita e impedisce l'accesso a queste porte. Per abilitare il firewall per gli esempi, completare una delle procedure descritte di seguito, a seconda dei requisiti e dell’ambiente di sicurezza:  
  
- Opzione 1: abilitazione degli esempi in modo interattivo durante l’esecuzione. Non apportare nessuna modifica alla configurazione del firewall in anticipo e procedere con l’avvio e l’esecuzione degli esempi. Quando viene eseguito un esempio, viene visualizzata una finestra di dialogo **avviso di sicurezza di Windows** . Il programma di esempio in questione può essere quindi aggiunto, in modo interattivo, a un elenco sbloccato. Questa procedura può richiedere il riavvio dell'esempio.  
  
- Opzione 2: abilitazione dei programmi di esempio in anticipo. Avviare l'applet del **Pannello di controllo Windows Firewall** e abilitare i programmi di esempio che si intende eseguire. Per creare file eseguibili, è necessario prima compilare i programmi. Informazioni più dettagliate sono descritte nella procedura seguente.  
  
- Opzione 3: abilitazione dell’intervallo delle porte in anticipo. Avviare l' **Windows Firewall** applet del **Pannello di controllo** e abilitare le porte 80, 443, 8000-8003 e 9000, utilizzate dagli esempi. Informazioni più dettagliate sono descritte nella procedura seguente. Questa opzione è meno sicura rispetto alle altre in quanto consente a qualsiasi programma di utilizzare queste porte, non solo agli esempi.  
  
 In caso di dubbi su quale procedura utilizzare, scegliere la prima opzione. Se si sta eseguendo un firewall di un altro fornitore, potrebbe essere necessario apportare modifiche simili.  
  
> [!IMPORTANT]
> La modifica della configurazione del firewall influisce sulla sicurezza. È consigliabile registrare le modifiche apportate e rimuoverle una volta completate le operazioni con gli esempi.  
  
### <a name="to-enable-samples-programs-in-advance"></a>Abilitazione dei programmi di esempio in anticipo.  
  
1. Compilare l'esempio.  
  
2. Fare clic sul pulsante **Start**, scegliere **esegui**e digitare `firewall.cpl`. Verrà visualizzata l'applet del **Pannello di controllo Windows Firewall** .  
  
    > [!NOTE]
    > Per modificare le impostazioni del firewall ed eseguire gli esempi che richiedono la possibilità di comunicare con Windows Firewall, è necessario disporre delle autorizzazioni necessarie. Se alcune impostazioni del firewall non sono disponibili e il computer è connesso a un dominio, è possibile che queste impostazioni vengano controllate dall'amministratore di sistema tramite Criteri di gruppo.  
  
3. Completare uno dei passaggi operativi specifici seguente per consentire a un programma l'accesso con Windows Firewall:  
  
    - In Windows 7 o Windows Server 2008 R2 fare clic su **Consenti programma o funzionalità tramite Windows Firewall**. Fare clic su **Cambia impostazioni**, Consenti **un altro programma...** .  
  
    - In Windows Vista o Windows Server 2008, fare clic su **Consenti programma tramite Windows Firewall**.  
  
4. Nella scheda **eccezioni** fare clic su **Aggiungi programma**.  
  
5. Fare clic sul pulsante **Sfoglia** e selezionare il file eseguibile dell'esempio che si intende eseguire.  
  
6. Ripetere i passaggi 4 e 5 fino a quando non sono stati aggiunti i file eseguibili di tutti gli esempi che si prevede di eseguire.  
  
7. Fare clic su **OK** per chiudere l'applet del firewall.  
  
### <a name="to-enable-a-port-range-in-advance"></a>Abilitazione di un intervallo delle porte in anticipo.  
  
1. Fare clic sul pulsante **Start**, scegliere **esegui**e digitare `firewall.cpl`. Verrà visualizzata l'applet del **Pannello di controllo Windows Firewall** .  
  
2. In Windows 7 o Windows Server 2008 R2 attenersi alla procedura seguente:  
  
    1. Fare clic su **Impostazioni avanzate** nella colonna a sinistra della finestra di Windows Firewall.  
  
    2. Fare clic su **regole in ingresso** nella colonna a sinistra.  
  
    3. Fare clic su **nuove regole** nella colonna a destra.  
  
    4. Selezionare **porta** e fare clic su **Avanti**.  
  
    5. Selezionare **TCP** e immettere `8000, 8001, 8002, 8003, 9000, 80, 443` nel campo **porte locali specifiche** .  
  
    6. Scegliere **Avanti**.  
  
    7. Selezionare **Consenti la connessione**e fare clic su **Avanti** .  
  
    8. Selezionare **dominio** e **privato**e fare clic su **Avanti**.  
  
    9. Assegnare alla regola il nome `WCF-WF 4.0 Samples`, quindi fare clic su **fine**.  
  
    10. Fare clic su **regole in uscita** e ripetere i passaggi da c a h.  
  
3. In Windows Vista o Windows Server 2008, attenersi alla seguente procedura.  
  
    1. Fare clic su **Consenti programma con Windows Firewall**.  
  
    2. Nella scheda **eccezioni** fare clic su **Aggiungi porta**.  
  
    3. Immettere un nome, immettere 8000 come numero di porta e selezionare l'opzione **TCP** .  
  
    4. Fare clic sul pulsante **Cambia ambito** , selezionare l'opzione solo **rete** (subnet) e fare clic su **OK**.  
  
    5. Ripetere i passaggi da B a D per le porte 8001, 8002, 8003, 9000, 80 e 443.  
  
4. Fare clic su **OK** per chiudere l'applet del firewall.  
  
> [!NOTE]
> Rimuovere qualsiasi eccezione del firewall una volta completate le operazioni con gli esempi. A tale scopo, aprire l' **Windows Firewall** applet del pannello di controllo e rimuovere tutti i programmi o le voci di porta aggiunti dalle procedure precedenti.
