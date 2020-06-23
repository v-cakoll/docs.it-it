---
title: Client di test WCF (WcfTestClient.exe)
description: Informazioni sul client di prova WCF, che fornisce test di servizio senza problemi in combinazione con l'host del servizio WCF. Inviare i valori del test client e visualizzare le risposte del servizio.
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: 4f636698c538809f89ee356159839a37b73adb57
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245661"
---
# <a name="wcf-test-client-wcftestclientexe"></a>Client di test WCF (WcfTestClient.exe)
Windows Communication Foundation (WCF) client di test (WcfTestClient.exe) è uno strumento GUI che consente agli utenti di immettere parametri di test, inviare tale input al servizio e visualizzare la risposta restituita dal servizio. Offre un'esperienza di test dei servizi senza problemi in combinazione con l'host del servizio WCF.

È in genere possibile trovare il client di prova WCF (WcfTestClient.exe) nel percorso seguente: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` -community può essere una delle "Enterprise", "Professional" o "community" a seconda del livello di Visual Studio installato.

## <a name="scenarios-for-using-test-client"></a>Scenari per l'uso di Client di test

Nelle sezioni seguenti vengono illustrati gli scenari più comuni in cui è possibile utilizzare il client di prova WCF per semplificare il processo di sviluppo.

### <a name="inside-visual-studio"></a>All'interno di Visual Studio

#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>Host servizio WCF avvia Client di test WCF con un solo servizio

Dopo aver creato un nuovo progetto di servizio WCF e premuto F5 per avviare il debugger, l'host del servizio WCF inizia a ospitare il servizio nel progetto. Viene quindi aperto il client di prova WCF e viene visualizzato un elenco di endpoint di servizio definiti nel file di configurazione. È possibile testare i parametri e richiamare il servizio e ripetere il processo per testare e convalidare continuamente il servizio.

#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>Host servizio WCF avvia Client di test WCF con più servizi

È inoltre possibile utilizzare il client di prova WCF per eseguire il debug di un progetto di servizio che contiene più servizi. Quando il client di prova WCF si apre, scorre automaticamente l'elenco dei servizi nel progetto e li apre per il test.

### <a name="outside-visual-studio"></a>All'esterno di Visual Studio

È anche possibile richiamare il client di prova WCF (WcfTestClient.exe) al di fuori di Visual Studio per testare un servizio arbitrario su Internet. Per individuare lo strumento, passare al percorso seguente:

`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE`(dove la community può essere una delle "Enterprise", "Professional" o "community" a seconda del livello di Visual Studio installato nel computer)

Per usare lo strumento, fare doppio clic sul nome del file per aprirlo da questo percorso oppure avviarlo da una riga di comando.

Il client di prova WCF accetta un numero arbitrario di URI come argomenti della riga di comando.  Di seguito sono riportati gli URI dei servizi che è possibile sottoporre a test.

`wcfTestClient.exe URI1 URI2 …`

Dopo aver aperto la finestra client di test WCF, fare clic su **file** -> **Aggiungi servizio**e immettere l'indirizzo dell'endpoint del servizio che si desidera aprire.

## <a name="wcf-test-client-user-interface"></a>Interfaccia utente di Client di test WCF

È possibile utilizzare il client di prova WCF con un solo servizio o più servizi.

### <a name="service-operations"></a>Operazioni di servizio

Il riquadro sinistro della finestra principale del client di test WCF elenca tutti i servizi disponibili, insieme ai rispettivi endpoint e operazioni.

Quando si fa doppio clic su un'operazione, è possibile visualizzare il relativo contenuto nel riquadro di destra all'interno di una nuova scheda con il nome dell'operazione.

Nel riquadro di sinistra sono elencati i anche file di configurazione client. Fare doppio clic sugli elementi per visualizzare il contenuto del file in una nuova finestra a schede nel riquadro di destra.

### <a name="entering-test-parameters"></a>Immissione dei parametri del test

Per visualizzare i parametri del test, fare doppio clic su un'operazione per aprirla nel riquadro di destra. Per impostazione predefinita, i parametri vengono visualizzati nella visualizzazione **formattata** ed è possibile immettere valori arbitrari per i parametri per il test del servizio.

Per visualizzare il codice XML del messaggio, fare clic su **XML**. Per inviarli al servizio, fare clic su **richiama**.

Per un parametro del set di dati, fare clic su **...** pulsante accanto a **modifica...** per modificarlo in una nuova finestra che mostra il DataGrid. Si noti l'aspetto dei pulsanti **copia set di dati** e **Incolla set di dati** . Se lo schema dell'oggetto the DataSet non è noto alla prima modifica, il DataGrid sarà vuoto. È necessario incollare un oggetto DataSet object con lo stesso schema nell'oggetto corrente nel DataGrid Si noti che è necessario copiare lo schema da un'altra posizione prima dell'operazione Incolla. È anche possibile copiare un oggetto DataSet per utilizzi futuri facendo clic sul pulsante **copia set di dati** .

La risposta del servizio viene visualizzata sotto i parametri del test.

> [!NOTE]
> Se il valore restituito previsto è una stringa, il risultato verrà visualizzato come una stringa tra virgolette anche se l'input fornito non era tra virgolette.

Se una particolare operazione viene specificata come unidirezionale quando si crea il contratto per il servizio, non viene visualizzata alcuna risposta del servizio. Non appena il messaggio viene accodato per il recapito, viene visualizzata una finestra di dialogo per notificare che il messaggio è stato inviato correttamente.

### <a name="session-support"></a>Supporto della sessione

La casella di controllo **avvia un nuovo proxy** nella scheda di un'operazione del servizio consente di attivare o disabilitare il supporto della sessione. Per impostazione predefinita, la casella è deselezionata.

Quando si immettono parametri di test per un'operazione specifica (o un'altra operazione nello stesso endpoint del servizio) e si fa clic più volte su **richiama** con la casella di controllo deselezionata, tali operazioni condividono un proxy e lo stato del servizio viene reso permanente tra più operazioni.

Se la casella di controllo **avvia un nuovo proxy** è selezionata, viene avviato un nuovo proxy per ogni **richiamo**, lo scenario della sessione precedente viene terminato e lo stato del servizio viene reimpostato.

### <a name="editing-client-configuration"></a>Modifica della configurazione client

Il riquadro sinistro della finestra principale del client di test WCF elenca i file di configurazione client. Fare doppio clic su uno degli elementi per visualizzare il contenuto del file nel riquadro di destra.

#### <a name="edit-with-service-configuration-editor"></a>Apportare modifiche con l'Editor configurazione servizi

Fare clic con il pulsante destro del mouse su **file di configurazione** nel riquadro sinistro e selezionare il menu di scelta rapida **modifica con SvcConfigEditor**. Editor configurazione servizi verrà avviato con il contenuto della configurazione client. Sarà possibile modificare la configurazione e salvarla all'interno dello strumento.

Dopo aver salvato il file nell'editor di configurazione dei servizi, il client di prova WCF Visualizza un messaggio di avviso per informare che il file è stato modificato all'esterno e chiede se si desidera ricaricarlo.

Se si seleziona **Sì**, il contenuto della configurazione nella scheda "Client.dll.config" riflette le modifiche apportate nell'editor.

Se si seleziona **No**, il contenuto della configurazione nella scheda "Client.dll.config" rimane invariato e il contenuto modificato viene salvato automaticamente nel file di origine.

#### <a name="restore-to-default-configuration"></a>Ripristinare la configurazione predefinita

Se si desidera annullare tutte le modifiche e ripristinare la configurazione client predefinita, fare clic con il pulsante destro del mouse su **file di configurazione** nel riquadro sinistro e selezionare il menu di scelta rapida **Ripristina configurazione predefinita**. Il valore di configurazione predefinito viene caricato e il contenuto nella scheda "Client.dll.config" viene ripristinato.

#### <a name="validate-changes"></a>Convalidare le modifiche

Quando le modifiche salvate vengono caricate nel client di prova WCF, viene verificata la validità della configurazione rispetto allo schema WCF. Se vengono rilevati errori, verrà visualizzata una finestra di dialogo contenente i dettagli degli errori.

Durante la generazione del proxy, la compilazione binaria o il richiamo del servizio, le voci di menu che supportano la modifica, ovvero "modifica...", "ripristino..." e così via, sono disabilitate. La chiamata al servizio viene inoltre disabilitata durante il caricamento della configurazione aggiornata nel client di prova WCF.

#### <a name="persist-client-configuration"></a>Rendere persistente la configurazione client

La **Tools** -> **Options** -> scheda**configurazione client** opzioni strumenti contiene un'opzione **Rigenera sempre la configurazione all'avvio dei servizi** , abilitata per impostazione predefinita. Questa opzione specifica che ogni volta che il client di prova WCF carica un servizio, rigenera un file di configurazione in base al contratto di servizio e ai file di App.config del servizio più recenti.

Se è stata modificata la configurazione client per il servizio WCF e si desidera utilizzare sempre questo file aggiornato per eseguire il debug del servizio, è possibile deselezionare l'opzione **Rigenera** . In questo modo, anche quando si aggiorna il servizio e si riapre il client di prova WCF, il file di Client.dll.config è quello che è stato aggiornato in precedenza anziché uno rigenerato in base al servizio aggiornato.

Potrebbe tuttavia essere necessario modificare il file di configurazione per renderlo coerente con il proxy rigenerato. Se il proxy e file di configurazione rigenerati non corrispondono perché un servizio è stato aggiornato, si verificheranno errori quando il servizio viene richiamato.

> [!CAUTION]
> Se il file di configurazione client è stato modificato e si è scelto di riusarlo in futuro, il file sarà disponibile nel percorso seguente:
>
> \Documents and Settings \\ [user account] \My Documents\Test Client Projects.
>
> Le informazioni sulle credenziali aggiornate archiviate nel file di configurazione client sono protette dall'elenco di controllo dell'accesso (ACL) di questa cartella.

### <a name="adding-removing-and-refreshing-services"></a>Aggiunta, rimozione e aggiornamento di servizi

#### <a name="add-service"></a>Aggiungere un servizio

Fare clic su **file** -> **Aggiungi servizio** per aggiungere un servizio al client di prova WCF. Verrà quindi richiesto di digitare l'URI (indirizzo endpoint) del servizio da aggiungere. L'indirizzo del servizio può corrispondere a un indirizzo mex o a un indirizzo WSDL.

È anche possibile trovare un elenco di 10 endpoint dei servizi aggiunti di recente nel sottomenu **Servizi recenti** . Se si seleziona uno di essi, il servizio specificato viene aggiunto al client di prova WCF.

È anche possibile fare clic con il pulsante destro del mouse sulla radice dell'albero dei servizi **progetti di servizio**e selezionare **Aggiungi servizio** per ottenere lo stesso risultato.

Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano l'aggiunta di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.

#### <a name="remove-service"></a>Rimuovere un servizio

Fare clic con il pulsante destro del mouse sulla radice del servizio da rimuovere, quindi scegliere **Rimuovi servizio** per rimuovere un servizio da client di prova WCF.

Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano la rimozione di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.

#### <a name="refresh-service"></a>Aggiornare un servizio

Se viene apportata una modifica al servizio mentre il client di prova WCF è in esecuzione e si desidera assicurarsi che l'implementazione del client di prova WCF per il servizio sia aggiornata, fare clic con il pulsante destro del mouse sulla radice del servizio e selezionare **Aggiorna servizio**. Si noti che dopo l'aggiornamento lo stato del servizio viene reimpostato.

Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano l'aggiornamento di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.

## <a name="location-of-files-generated-by-the-test-client"></a>Percorso dei file generati da Client di test

Per impostazione predefinita, il client di prova WCF archivia il codice client e i file di configurazione generati nella cartella "%appdata%\Local\temp\Test Client Projects". Questa cartella viene eliminata dopo la chiusura del client di test WCF. Se un file di configurazione viene modificato nel client di prova WCF e l'opzione **Rigenera sempre la configurazione all'avvio dei servizi** è disabilitata, il file modificato viene copiato nella cartella "CachedConfig" in "My Documents\Test Client Projects" con un file XML di mapping (Metadata-Address-to-file-name) come indice.

È anche possibile avviare il client di prova WCF in una riga di comando, usare l' `/ProjectPath` opzione per specificare un nuovo percorso desiderato per archiviare i file generati oppure usare l' `/RestoreProjectPath` opzione per ripristinare il percorso predefinito. La sintassi è la seguente:

`wcfTestClient.exe /ProjectPath [desired location]`

L'esecuzione di questo comando non consente di aprire il client di prova WCF. ma solo la modifica del percorso della cartella. È possibile eseguire questo comando se il client di prova WCF è in esecuzione o meno. La nuova posizione viene applicata quando il client di test WCF viene riavviato. Le informazioni sul percorso possono essere salvate nel registro di sistema o nel file WcfTestClient.exe. Option nella cartella "%appdata%\Local\temp\Test Client Projects".

## <a name="features-supported-by-wcf-test-client"></a>Funzioni supportate da Client di prova WCF

Di seguito è riportato un elenco delle funzionalità supportate dal client di prova WCF:

- Chiamata al servizio: messaggio di richiesta/risposta e unidirezionale.

- Associazioni: tutte le associazioni supportate da Svcutil.exe.

- Controllo della sessione.

- Contratto di messaggio.

- Serializzazione XML.

Di seguito è riportato un elenco di funzionalità non supportate dal client di prova WCF:

- Tipi: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipi che implementano l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>, tra cui l'attributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> correlato, i tipi <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement> e il tipo <xref:System.Data.DataTable> di ADO.NET.

- Contratto duplex.

- Transazione.

- Sicurezza: CardSpace, certificato e nome utente/password.

- Associazioni: WSFederationbinding, qualsiasi associazione Context e associazione Https, WebHttpbinding (supporto per messaggi di riposta Json).

## <a name="closing-wcf-test-client"></a>Chiusura di Client di test WCF

È possibile chiudere il client di prova WCF nei modi seguenti:

- Scegliere **Esci** dal menu **File**. In alternativa, nella finestra principale del client di prova WCF fare clic su **Chiudi**. Entrambe queste azioni arrestano anche l'host automatico del servizio WCF e arrestano il processo di debug di Visual Studio se il client di test WCF è stato avviato da Visual Studio.

- Fare clic con il pulsante destro del mouse sull'icona **host del servizio WCF** nell'area di notifica, quindi scegliere **Esci.** Questo arresta l'host automatico del servizio WCF e il client di prova WCF e arresta il processo di debug di Visual Studio.

## <a name="see-also"></a>Vedere anche

- [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
