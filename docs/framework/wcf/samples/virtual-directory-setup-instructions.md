---
title: Istruzioni per la configurazione di directory virtuali
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 2d9443431601ffc712da40bd1c085f595471336b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602362"
---
# <a name="virtual-directory-setup-instructions"></a>Istruzioni per la configurazione di directory virtuali
Gli esempi di Windows Communication Foundation (WCF) sono destinati a condividere una directory virtuale comune denominata servicemodelsamples di cui è stato eseguito il mapping alla cartella%SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
> [!NOTE]
> %SystemDrive% è in genere C: o D:, a seconda della posizione dell'unità dove è installato IIS (Internet Information Services).  
  
 È possibile eseguire i file Setupvroot. bat e Cleanupvroot. bat dalla [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md) per creare la directory virtuale. Se si preferisce creare la directory virtuale manualmente, utilizzare le procedure seguenti.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>Per creare una directory virtuale in IIS 7,0 o 7,5  
  
1. Dal menu **Start** fare clic su **Esegui**, quindi digitare **inetmgr** per aprire lo snap-in MMC Internet Information Services (IIS).  
  
2. Nel riquadro sinistro espandere il nodo con il nome del computer, quindi espandere il nodo **siti** .  
  
3. Fare clic con il pulsante destro del mouse su **sito Web predefinito**e selezionare **Aggiungi applicazione** per aprire la **finestra Aggiungi applicazione**.  
  
4. Nella finestra di digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.  
  
5. Creare la directory seguente: %SystemDrive%\inetpub\wwwroot\servicemodelsamples  
  
6. Impostare il percorso fisico su %SystemDrive%\inetpub\wwwroot\\servicemodelsamples.  Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.  
  
7. Fare clic su **OK**. L'applicazione Web è stata creata per gli esempi WCF.  
  
    > [!NOTE]
    > Questa attività deve essere eseguita solo una volta, poiché tutti gli esempi WCF utilizzano la stessa applicazione Web servicemodelsamples.  
  
    > [!NOTE]
    > Ai fini di questa documentazione, il termine `virtual directory` è sinonimo di `Web application`.  
  
     Oltre a creare la directory virtuale, è inoltre necessario impostare le proprietà per consentire l'esecuzione dei servizi WCF. Per informazioni dettagliate, vedi di seguito.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>Per creare una directory virtuale in IIS 5.1 o 6.0  
  
1. Aprire una finestra del prompt dei comandi e digitare `start inetmgr` per aprire lo snap-in MMC Internet Information Services (IIS).  
  
2. Nel riquadro sinistro espandere il nodo con il nome del computer, quindi espandere il nodo **siti Web** .  
  
3. Fare clic con il pulsante destro del mouse su **sito Web predefinito** e selezionare **nuovo, directory virtuale** per aprire la creazione guidata directory virtuale.  
  
4. Nella procedura guidata digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.  
  
5. Impostare il percorso su %SystemDrive%\inetpub\wwwroot\servicemodelsamples. Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.  
  
6. Fare clic su **Avanti**.  
  
7. Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:  
  
    - **Lettura**  
  
    - **Esecuzione script (ad esempio, ASP)**  
  
8. Fare clic su **Avanti**e quindi su **fine** per completare la procedura guidata.  
  
    > [!NOTE]
    > Questa attività deve essere eseguita solo una volta poiché tutti gli esempi WCF utilizzano la stessa directory virtuale servicemodelsamples.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Per impostare proprietà aggiuntive della directory virtuale in IIS 7,0 o 7,5  
  
1. Fare clic sul nodo servicemodelsamples. Lungo la parte inferiore della finestra sono elencate due visualizzazioni. Selezionare **visualizzazione funzionalità** se non è già selezionata.  
  
2. Fare doppio clic sulla voce per l' **esplorazione directory**.  
  
3. Nel riquadro azioni selezionare l'opzione **Abilita** . In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.  
  
 Infine, è necessario impostare le proprietà di sicurezza della cartella servicemodelsamples per renderla accessibile ad altri. Per informazioni dettagliate, vedi di seguito.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>Per impostare proprietà aggiuntive della directory virtuale in IIS 5.1 o 6.0  
  
1. Fare clic con il pulsante destro del mouse sul nodo servicemodelsamples, quindi scegliere **Proprietà**.  
  
2. Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:  
  
    - **Lettura**  
  
    - **Log visite**  
  
    - **Indicizza questa risorsa**  
  
3. Selezionare la casella di controllo **esplorazione directory** . In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>Per impostare le proprietà di sicurezza della cartella in IIS 7,0 o 7,5  
  
1. Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Fare clic con il pulsante destro del mouse sulla cartella servicemodelsamples e scegliere **Condividi** o **Condividi con**.  
  
3. Fare clic sulla freccia verso il basso a sinistra del pulsante **Aggiungi** .  
  
4. Selezionare la voce **trova** . Verrà visualizzata la finestra **Selezione utenti o gruppi** .  
  
5. Fare clic su **Avanzate**.  
  
6. Fare clic su **percorsi**. La finestra **percorsi** è ora aperta.  
  
7. Selezionare la voce per il computer utilizzato. È importante selezionare il computer locale e non una voce per qualsiasi dominio o reti elencati. Dopo aver selezionato il computer, fare clic su **OK**.  
  
8. Fai clic su **Trova**. Nei risultati di ricerca vengono inseriti gli oggetti associati al computer locale.  
  
9. Trovare la voce **IIS_IUSRS** nella colonna **nome (nome distinto relativo)** . Selezionare la voce e fare clic su **OK** per chiudere la finestra dei risultati della ricerca.  
  
10. Fare clic su **OK** per chiudere la finestra **Selezione utenti o gruppi** .  
  
11. Fare clic su **Condividi** per salvare in modo permanente le modifiche.  
  
12. Una volta completate le modifiche per abilitare la condivisione, **fare clic su Chiudi per** chiudere la finestra **condivisione file** .  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>Per impostare le proprietà di sicurezza della cartella in IIS 5.1 o 6.0  
  
1. Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Fare clic con il pulsante destro del mouse sulla cartella **servicemodelsamples** , quindi scegliere **condivisione e sicurezza.**  
  
3. Fare clic sulla scheda **Sicurezza**.  
  
4. Se si utilizza IIS 6,0, nella casella **nome gruppo o utente** verificare se è elencato l' **account Internet Guest** .  
  
     In caso contrario:  
  
    1. Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.  
  
    2. Se l'icona **account utente** non viene visualizzata, fare clic su **passa alla visualizzazione categoria**.  
  
    3. Fare clic sull'icona **account utente** .  
  
    4. In "o selezionare un'icona del pannello di controllo" fare clic su **account utente**.  
  
    5. Nella finestra di dialogo **account utente** fare clic sulla scheda **Avanzate** .  
  
    6. Fare clic su **Avanzate**.  
  
    7. Nella finestra di dialogo **utenti e gruppi locali** fare clic per espandere la cartella **utenti** .  
  
    8. Nel riquadro destro fare doppio clic su **account Internet Guest**.  
  
    9. Nella finestra di dialogo **Proprietà** copiare il nome utilizzato come account Internet Guest. Per impostazione predefinita, il nome inizia con “USR_” seguito dal nome del computer.  
  
    10. Chiudere la finestra di dialogo **Proprietà** .  
  
    11. Chiudere la finestra **di dialogo utenti e gruppi locali** .  
  
    12. Chiudere la finestra di dialogo **account utente** .  
  
    13. Chiudere la finestra di dialogo altri **account utente** .  
  
    14. Nella scheda **sicurezza** della finestra di dialogo **Proprietà servicemodelsamples** fare clic su **Aggiungi**.  
  
    15. Digitare il nome del computer seguito da una barra rovesciata, quindi incollare il nome dell'account utente Internet, ad esempio, nomecomputer \\ % InternetGuestAccountName%  
  
    16. Fare clic su **Controlla nomi** per verificare l'aggiunta. Se è valido, il nome è composto di tutti caratteri maiuscoli ed è sottolineato.  
  
5. Per IIS 6,0, verificare anche che servizio di rete sia elencato nella casella **nome gruppo o utente** .  
  
     Se SERVIZIO DI RETE non è elencato:  
  
    1. Scegliere **Aggiungi**.  
  
    2. Nella finestra di dialogo **Seleziona utenti o gruppi** Digitare il nome del computer seguito da una barra rovesciata.  
  
    3. Digitare **Service** dopo la barra rovesciata (senza spazio).  
  
    4. Fare clic su **Controlla nomi**.  
  
    5. Se vengono trovati più nomi, selezionare **servizio di rete** e fare clic su **OK**.  
  
    6. Fare clic su **OK** per chiudere la finestra di dialogo **Seleziona utenti o gruppi** .  
  
6. Se si utilizza Windows XP SP2 con IIS 5,1, verificare che sia l'account Guest Internet che ASPNET siano elencati nella casella **nome gruppo o utente** .  
  
     Si noti che l'utente ASPNET può essere un membro del gruppo di sicurezza predefinito **Users** . In tal caso, se il gruppo **utenti** è elencato nella finestra di dialogo, non è necessario aggiungerlo come elemento separato all'elenco degli utenti autorizzati.  
  
     Per verificare se ASPNET fa parte del gruppo di sicurezza **Users** :  
  
    1. Fare clic sul menu **Start** e scegliere **Pannello di controllo**.  
  
    2. Fare clic sull'icona **account utente** .  
  
    3. Nella colonna **gruppo** verificare che il valore per **ASPNET** sia "Users".  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni per l'hosting su IIS (Internet Information Services)](internet-information-service-hosting-instructions.md)
