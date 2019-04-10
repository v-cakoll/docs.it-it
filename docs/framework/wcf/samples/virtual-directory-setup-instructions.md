---
title: Istruzioni per la configurazione di directory virtuali
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 7999a040dc14d75a34b75f320982dd3118eae670
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225586"
---
# <a name="virtual-directory-setup-instructions"></a>Istruzioni per la configurazione di directory virtuali
Gli esempi di Windows Communication Foundation (WCF) devono condividere una directory virtuale comune denominata servicemodelsamples associata viene eseguito il mapping alla cartella %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
> [!NOTE]
>  %SystemDrive% è in genere C: o D:, a seconda della posizione dell'unità dove è installato IIS (Internet Information Services).  
  
 È possibile eseguire i file setupvroot e cleanupvroot dal [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) per creare la directory virtuale. Se si preferisce creare la directory virtuale manualmente, utilizzare le procedure seguenti.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>Per creare una directory virtuale in IIS 7.0 o 7.5  
  
1.  Dal **avviare** menu, fare clic su **eseguito**, quindi digitare **inetmgr** per aprire lo snap-in MMC di Internet Information Services (IIS).  
  
2.  Nel riquadro sinistro, espandere il nodo con il nome del computer e quindi espandere la **siti** nodo.  
  
3.  Fare doppio clic su **sito Web predefinito**, quindi selezionare **Aggiungi applicazione** per aprire il **finestra Aggiungi applicazione**.  
  
4.  Nella finestra di, digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.  
  
5.  Creare la directory seguente: %SystemDrive%\inetpub\wwwroot\servicemodelsamples  
  
6.  Impostare il percorso fisico su %SystemDrive%\inetpub\wwwroot\\servicemodelsamples.  Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.  
  
7.  Fare clic su **OK**. L'applicazione Web è stata creata per gli esempi WCF.  
  
    > [!NOTE]
    >  Questa attività deve essere eseguita una sola volta, poiché tutti gli esempi WCF utilizzano la stessa applicazione Web servicemodelsamples.  
  
    > [!NOTE]
    >  Ai fini di questa documentazione, il termine `virtual directory` è sinonimo di `Web application`.  
  
     Oltre a creare la directory virtuale, è necessario anche impostare le proprietà per abilitare i servizi WCF per l'esecuzione. Di seguito sono riportate informazioni dettagliate.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>Per creare una directory virtuale in IIS 5.1 o 6.0  
  
1.  Aprire una finestra del prompt dei comandi e digitare `start inetmgr` per aprire lo snap-in MMC di Internet Information Services (IIS).  
  
2.  Nel riquadro sinistro, espandere il nodo con il nome del computer e quindi espandere la **siti Web** nodo.  
  
3.  Fare doppio clic su **sito Web predefinito** e selezionare **New, Virtual Directory** per aprire la procedura guidata Creazione Directory virtuale.  
  
4.  Nella procedura guidata digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.  
  
5.  Impostare il percorso su %SystemDrive%\inetpub\wwwroot\servicemodelsamples. Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.  
  
6.  Scegliere **Avanti**.  
  
7.  Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:  
  
    -   **Lettura**  
  
    -   **Esecuzione script (ad esempio, ASP)**  
  
8.  Fare clic su **successivo**, quindi fare clic su **fine** per completare la procedura guidata.  
  
    > [!NOTE]
    >  Questa attività deve essere eseguita una sola volta poiché tutti gli esempi WCF usano la stessa directory virtuale servicemodelsamples.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Per impostare proprietà aggiuntive della directory virtuale in IIS 7.0 o 7.5  
  
1.  Fare clic sul nodo servicemodelsamples. Lungo la parte inferiore della finestra sono elencate due visualizzazioni. Selezionare **visualizzazione funzionalità** se non è già selezionato.  
  
2.  Fare doppio clic sulla voce relativa **esplorazione Directory**.  
  
3.  Nel riquadro azioni, selezionare la **abilitare** opzione. In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.  
  
 Infine, è necessario impostare le proprietà di sicurezza della cartella servicemodelsamples per renderla accessibile ad altri. Di seguito sono riportate informazioni dettagliate.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>Per impostare proprietà aggiuntive della directory virtuale in IIS 5.1 o 6.0  
  
1.  Fare clic sul nodo servicemodelsamples e quindi fare clic su **proprietà**.  
  
2.  Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:  
  
    -   **Lettura**  
  
    -   **Registrazione visite**  
  
    -   **Indicizza questa risorsa**  
  
3.  Selezionare il **esplorazione Directory** casella di controllo. In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>Per impostare le proprietà di sicurezza della cartella in IIS 7.0 o 7.5  
  
1.  Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Fare doppio clic sulla cartella servicemodelsamples e scegliere **Share** oppure **Condividi con**.  
  
3.  Fare clic sulla freccia verso il basso a sinistra del **Add** pulsante.  
  
4.  Selezionare il **trovare** voce. Il **Seleziona utenti o gruppi** verrà visualizzata la finestra.  
  
5.  Scegliere **Avanzate**.  
  
6.  Fare clic su **posizioni**. Il **posizioni** viene aperta la finestra.  
  
7.  Selezionare la voce per il computer utilizzato. È importante selezionare il computer locale e non una voce per qualsiasi dominio o reti elencati. Dopo aver selezionato il computer, fare clic su **OK**.  
  
8.  Fare clic su **trova**. Nei risultati di ricerca vengono inseriti gli oggetti associati al computer locale.  
  
9. Trovare il **IIS_IUSRS** voce il **Name (nome distinto relativo)** colonna. Selezionare una voce e fare clic su **OK** per chiudere la ricerca i risultati della finestra.  
  
10. Fare clic su **OK** per chiudere la **Seleziona utenti o gruppi** finestra.  
  
11. Fare clic su **condivisione** per rendere permanenti le modifiche.  
  
12. Una volta completate le modifiche per abilitare la condivisione, fare clic su **Completato** per chiudere la finestra **Condivisione File**.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>Per impostare le proprietà di sicurezza della cartella in IIS 5.1 o 6.0  
  
1.  Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Fare doppio clic il **servicemodelsamples** cartella e quindi fare clic su **condivisione e sicurezza.**  
  
3.  Fare clic sulla scheda **Sicurezza** .  
  
4.  Se si utilizza IIS 6.0, nella **nomi utente o gruppo** finestra di controllo se **Account Internet Guest** sia elencato.  
  
     Se non è elencato:  
  
    1.  Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.  
  
    2.  Se non viene visualizzato il **gli account utente** icona, fare clic su **passare alla visualizzazione per categorie**.  
  
    3.  Scegliere il **gli account utente** icona.  
  
    4.  In "o un'icona di Pannello di controllo di selezione" fare clic su **gli account utente**.  
  
    5.  Nel **gli account utente** finestra di dialogo, fare clic sul **avanzate** scheda.  
  
    6.  Scegliere **Avanzate**.  
  
    7.  Nel **utenti e gruppi locali** finestra di dialogo, fare clic per espandere le **utenti** cartella.  
  
    8.  Nel riquadro di destra, fare doppio clic su **Account Internet Guest**.  
  
    9. Nel **proprietà** nella finestra di dialogo, copiare il nome usato come account Internet guest. Per impostazione predefinita, il nome inizia con “USR_” seguito dal nome del computer.  
  
    10. Chiudere la finestra di dialogo **Proprietà** .  
  
    11. Chiudi il **utenti e gruppi locali** nella finestra di dialogo.  
  
    12. Chiudi il **gli account utente** nella finestra di dialogo.  
  
    13. Chiudere l'altra **gli account utente** nella finestra di dialogo.  
  
    14. Nel **proprietà-servicemodelsamples** finestra di dialogo il **Security** scheda, fare clic su **Add**.  
  
    15. Digitare il nome del computer seguito da una barra rovesciata, quindi incollare il nome dell'account utente di Internet, ad esempio, myMachineName\\InternetGuestAccountName % %  
  
    16. Fare clic su **Controlla nomi** per verificare l'aggiunta. Se è valido, il nome è composto di tutti caratteri maiuscoli ed è sottolineato.  
  
5.  Per IIS 6.0, controllare anche che servizio di rete sia elencato nel **nomi utente o gruppo** casella.  
  
     Se SERVIZIO DI RETE non è elencato:  
  
    1.  Fare clic su **Aggiungi**.  
  
    2.  Nel **Seleziona utenti o gruppi** nella finestra di dialogo digitare il nome del computer seguito da una barra rovesciata.  
  
    3.  Tipo di **servizio** dopo la barra rovesciata (senza spazi).  
  
    4.  Fare clic su **Controlla nomi**.  
  
    5.  Se vengono trovati più nomi, selezionare **servizio di rete** e fare clic su **OK**.  
  
    6.  Fare clic su **OK** per chiudere la **Seleziona utenti o gruppi** nella finestra di dialogo.  
  
6.  Se si utilizza Windows XP SP2 con IIS 5.1, controllare che sia Account Internet Guest e ASPNET siano elencati nel **nomi utente o gruppo** casella.  
  
     Si noti che l'utente ASPNET può essere un membro di incorporati **utenti** gruppo di sicurezza. In questo caso, quindi, se il **utenti** gruppo è elencato nella finestra di dialogo, non è necessario aggiungerlo come elemento separato per l'elenco di utenti autorizzati.  
  
     Per controllare se ASPNET fa parte il **utenti** gruppo di sicurezza:  
  
    1.  Nel **avviare** menu, fare clic su **Pannello di controllo**.  
  
    2.  Scegliere il **gli account utente** icona.  
  
    3.  Nel **gruppo** colonna, verificare che il valore per **ASPNET** è "Users".  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni per l'hosting su IIS (Internet Information Services)](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
