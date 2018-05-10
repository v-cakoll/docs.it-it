---
title: Istruzioni per la configurazione di directory virtuali
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 3ff578b69590071ef2135e777b3105e7c226563e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="virtual-directory-setup-instructions"></a>Istruzioni per la configurazione di directory virtuali
Gli esempi di Windows Communication Foundation (WCF) devono condividere una directory virtuale comune denominata servicemodelsamples che viene eseguito il mapping alla cartella %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
> [!NOTE]
>  %SystemDrive% è in genere C: o D:, a seconda della posizione dell'unità dove è installato IIS (Internet Information Services).  
  
 È possibile eseguire i file Setupvroot.bat e Cleanupvroot.bat il [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) per creare la directory virtuale. Se si preferisce creare la directory virtuale manualmente, utilizzare le procedure seguenti.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>Per creare una directory virtuale in IIS 7.0 o 7.5  
  
1.  Dal **avviare** menu, fare clic su **eseguire**, quindi digitare **inetmgr** per aprire lo snap-in MMC di Internet Information Services (IIS).  
  
2.  Nel riquadro sinistro, espandere il nodo con il nome del computer e quindi espandere il **siti** nodo.  
  
3.  Fare doppio clic su **sito Web predefinito**, quindi selezionare **Aggiungi applicazione** per aprire la **finestra Aggiungi applicazione**.  
  
4.  Nella finestra, digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.  
  
5.  Creare la directory seguente: %SystemDrive%\inetpub\wwwroot\servicemodelsamples  
  
6.  Impostare il percorso fisico su %SystemDrive%\inetpub\wwwroot\\servicemodelsamples.  Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.  
  
7.  Fare clic su **OK**. L'applicazione Web è stata creata per gli esempi WCF.  
  
    > [!NOTE]
    >  Questa attività deve essere eseguita una sola volta, poiché tutti gli esempi WCF utilizzano la stessa applicazione Web servicemodelsamples.  
  
    > [!NOTE]
    >  Ai fini di questa documentazione, il termine `virtual directory` è sinonimo di `Web application`.  
  
     Oltre a creare la directory virtuale, è necessario impostare anche le relative proprietà per abilitare i servizi WCF per l'esecuzione. Di seguito sono riportate informazioni dettagliate.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>Per creare una directory virtuale in IIS 5.1 o 6.0  
  
1.  Aprire una finestra del prompt dei comandi e digitare `start inetmgr` per aprire lo snap-in MMC di Internet Information Services (IIS).  
  
2.  Nel riquadro sinistro, espandere il nodo con il nome del computer e quindi espandere il **siti Web** nodo.  
  
3.  Fare doppio clic su **sito Web predefinito** e selezionare **nuovo, Directory virtuale** per aprire la creazione guidata Directory virtuale.  
  
4.  Nella procedura guidata, digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.  
  
5.  Impostare il percorso su %SystemDrive%\inetpub\wwwroot\servicemodelsamples. Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.  
  
6.  Scegliere **Avanti**.  
  
7.  Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:  
  
    -   **Lettura**  
  
    -   **Eseguire gli script (ad esempio, ASP)**  
  
8.  Fare clic su **Avanti**, quindi fare clic su **fine** per completare la procedura guidata.  
  
    > [!NOTE]
    >  Questa attività deve essere eseguita solo una volta poiché tutti gli esempi WCF utilizzano la stessa directory virtuale servicemodelsamples.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Per impostare proprietà aggiuntive della directory virtuale in IIS 7.0 o 7.5  
  
1.  Fare clic sul nodo servicemodelsamples. Lungo la parte inferiore della finestra sono elencate due visualizzazioni. Selezionare **visualizzazione funzionalità** se non è già selezionato.  
  
2.  Fare doppio clic sulla voce per **esplorazione Directory**.  
  
3.  Nel riquadro azioni, selezionare il **abilitare** opzione. In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.  
  
 Infine, è necessario impostare le proprietà di sicurezza della cartella servicemodelsamples per renderla accessibile ad altri. Di seguito sono riportate informazioni dettagliate.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>Per impostare proprietà aggiuntive della directory virtuale in IIS 5.1 o 6.0  
  
1.  Fare doppio clic sul nodo servicemodelsamples e quindi fare clic su **proprietà**.  
  
2.  Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:  
  
    -   **Lettura**  
  
    -   **Registrazione visite**  
  
    -   **Indicizza questa risorsa**  
  
3.  Selezionare il **esplorazione Directory** casella di controllo. In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>Per impostare le proprietà di sicurezza della cartella in IIS 7.0 o 7.5  
  
1.  Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Fare clic sulla cartella servicemodelsamples e fare clic su **condivisione** o **Condividi con**.  
  
3.  Fare clic sulla freccia rivolta verso il basso a sinistra del **Aggiungi** pulsante.  
  
4.  Selezionare il **trovare** voce. Il **Seleziona utenti o gruppi** verrà visualizzata la finestra.  
  
5.  Scegliere **Avanzate**.  
  
6.  Fare clic su **percorsi**. Il **percorsi** viene aperta la finestra.  
  
7.  Selezionare la voce per il computer utilizzato. È importante selezionare il computer locale e non una voce per qualsiasi dominio o reti elencati. Dopo aver selezionato il computer, fare clic su **OK**.  
  
8.  Fare clic su **trova**. Nei risultati di ricerca vengono inseriti gli oggetti associati al computer locale.  
  
9. Trovare il **IIS_IUSRS** voce il **nome (nome distinto relativo)** colonna. Selezionare tale voce e fare clic su **OK** finestra dei risultati per chiudere la ricerca.  
  
10. Fare clic su **OK** per chiudere la **Seleziona utenti o gruppi** finestra.  
  
11. Fare clic su **condivisione** per rendere permanenti le modifiche.  
  
12. Dopo aver completate le modifiche per abilitare la condivisione, fare clic su **eseguita** per chiudere la **la condivisione di File** finestra.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>Per impostare le proprietà di sicurezza della cartella in IIS 5.1 o 6.0  
  
1.  Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Fare doppio clic sui **servicemodelsamples** cartella e quindi fare clic su **condivisione e sicurezza.**  
  
3.  Fare clic sulla scheda **Sicurezza** .  
  
4.  Se si utilizza IIS 6.0, nel **nomi utente o gruppo** , casella di controllo se **Account Internet Guest** è elencato.  
  
     Se non è elencato:  
  
    1.  Fare clic su **avviare** e quindi fare clic su **Pannello di controllo**.  
  
    2.  Se non viene visualizzato il **gli account utente** icona, fare clic su **passare alla visualizzazione per categorie**.  
  
    3.  Fare clic su di **gli account utente** icona.  
  
    4.  In "o seleziona un'icona del Pannello di controllo" fare clic su **gli account utente**.  
  
    5.  Nel **gli account utente** la finestra di dialogo, fare clic su di **avanzate** scheda.  
  
    6.  Scegliere **Avanzate**.  
  
    7.  Nel **utenti e gruppi locali** la finestra di dialogo, fare clic per espandere il **utenti** cartella.  
  
    8.  Nel riquadro destro fare doppio clic su **Account Internet Guest**.  
  
    9. Nel **proprietà** della finestra di dialogo Copia il nome utilizzato come account Internet guest. Per impostazione predefinita, il nome inizia con “USR_” seguito dal nome del computer.  
  
    10. Chiudere la finestra di dialogo **Proprietà** .  
  
    11. Chiudi il **utenti e gruppi locali** la finestra di dialogo.  
  
    12. Chiudi il **gli account utente** la finestra di dialogo.  
  
    13. Chiudere l'altra **gli account utente** la finestra di dialogo.  
  
    14. Nel **proprietà-servicemodelsamples** della finestra di dialogo di **sicurezza** scheda, fare clic su **Aggiungi**.  
  
    15. Digitare il nome del computer seguito da una barra rovesciata, quindi incollare il nome dell'account utente di Internet, ad esempio, myMachineName\\InternetGuestAccountName %  
  
    16. Fare clic su **Controlla nomi** per verificare l'aggiunta. Se è valido, il nome è composto di tutti caratteri maiuscoli ed è sottolineato.  
  
5.  Per IIS 6.0, controllare anche che il servizio di rete sia elencato nel **nomi utente o gruppo** casella.  
  
     Se SERVIZIO DI RETE non è elencato:  
  
    1.  Fare clic su **Aggiungi**.  
  
    2.  Nel **Seleziona utenti o gruppi** la finestra di dialogo digitare il nome del computer seguito da una barra rovesciata.  
  
    3.  Tipo **servizio** dopo la barra rovesciata (senza spazi).  
  
    4.  Fare clic su **Controlla nomi**.  
  
    5.  Se vengono trovati più nomi, selezionare **servizio di rete** e fare clic su **OK**.  
  
    6.  Fare clic su **OK** per chiudere la **Seleziona utenti o gruppi** la finestra di dialogo.  
  
6.  Se si utilizza Windows XP SP2 con IIS 5.1, controllare che Account Internet Guest e ASPNET siano elencati nel **nomi utente o gruppo** casella.  
  
     Si noti che l'utente ASPNET può essere un membro di incorporati **utenti** gruppo di sicurezza. In questo caso, quindi, se il **utenti** gruppo è elencato nella finestra di dialogo, non è necessario aggiungerlo come elemento separato per l'elenco di utenti autorizzati.  
  
     Per controllare se ASPNET fa parte di **utenti** gruppo di sicurezza:  
  
    1.  Nel **avviare** menu, fare clic su **Pannello di controllo**.  
  
    2.  Fare clic su di **gli account utente** icona.  
  
    3.  Nel **gruppo** colonna, verificare che il valore per **ASPNET** è "Users".  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzioni per l'hosting su Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
