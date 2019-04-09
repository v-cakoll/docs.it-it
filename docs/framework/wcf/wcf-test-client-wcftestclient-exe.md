---
title: Client di test WCF (WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: cd6f0d7a98ca5bc5f6bee45ad296341a5b91b2a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106769"
---
# <a name="wcf-test-client-wcftestclientexe"></a>Client di test WCF (WcfTestClient.exe)
Il Client di prova di Windows Communication Foundation (WCF) (WcfTestClient.exe) è un strumento GUI che consente agli utenti di immettere parametri di test, inviare tale input al servizio e Visualizza la risposta restituita dal servizio. Fornisce un servizio facile test combinazione con Host servizio WCF.  
  
 In genere, è possibile trovare il Client di prova WCF (WcfTestClient.exe) nel percorso seguente: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` - Community può essere uno dei "Enterprise", "Professional" o "Community" a seconda di quale livello di Visual Studio è installata.
  
## <a name="scenarios-for-using-test-client"></a>Scenari per l'uso di Client di test  
 Le sezioni seguenti illustrano gli scenari più comuni in cui è possibile usare Client di prova WCF per semplificare il processo di sviluppo.  
  
### <a name="inside-visual-studio"></a>All'interno di Visual Studio  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>Host servizio WCF avvia Client di test WCF con un solo servizio  
 Dopo aver creato un nuovo progetto di servizio WCF e premere F5 per avviare il debugger, l'Host del servizio WCF inizia a ospitare il servizio nel progetto. Quindi, Client di prova WCF apre e visualizza un elenco di endpoint di servizio definito nel file di configurazione. È possibile testare i parametri e richiamare il servizio e ripetere il processo per testare e convalidare continuamente il servizio.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>Host servizio WCF avvia Client di test WCF con più servizi  
 È anche possibile usare Client di prova WCF per eseguire il debug di un progetto di servizio contenente più servizi. Quando si apre il Client di prova WCF, automaticamente scorre l'elenco dei servizi nel progetto e li apre per il test.  
  
### <a name="outside-visual-studio"></a>All'esterno di Visual Studio  
 È anche possibile richiamare il Client di prova WCF (WcfTestClient.exe) esterno a Visual Studio per testare un servizio arbitrario su Internet. Per individuare lo strumento, passare al percorso seguente:  
  
 `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (dove community può essere uno tra "Enterprise", "Professional" o "Community", a seconda di quale livello di Visual Studio è installato nel computer)
  
 Per usare lo strumento, fare doppio clic sul nome del file per aprirlo da questo percorso oppure avviarlo da una riga di comando.  
  
 Client di prova WCF accetta un numero arbitrario di URI come argomenti della riga di comando.  Di seguito sono riportati gli URI dei servizi che è possibile sottoporre a test.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Dopo che viene aperta la finestra Client di prova WCF, fare clic su **File**->**Aggiungi servizio**e immettere l'indirizzo dell'endpoint del servizio che si desidera aprire.  
  
## <a name="wcf-test-client-user-interface"></a>Interfaccia utente di Client di test WCF  
 È possibile usare Client di prova WCF con un singolo servizio o più servizi.  
  
### <a name="service-operations"></a>Operazioni di servizio  
 Il riquadro sinistro della finestra principale di Client di prova WCF Elenca tutti i servizi disponibili, insieme ai rispettivi endpoint e operazioni.  
  
 Quando si fa doppio clic su un'operazione, è possibile visualizzare il relativo contenuto nel riquadro di destra all'interno di una nuova scheda con il nome dell'operazione.  
  
 Nel riquadro di sinistra sono elencati i anche file di configurazione client. Fare doppio clic sugli elementi per visualizzare il contenuto del file in una nuova finestra a schede nel riquadro di destra.  
  
### <a name="entering-test-parameters"></a>Immissione dei parametri del test  
 Per visualizzare i parametri del test, fare doppio clic su un'operazione per aprirla nel riquadro di destra. I parametri vengono mostrati nella **formattato** Visualizza per impostazione predefinita, ed è possibile immettere valori arbitrari dei parametri per il test del servizio.  
  
 Per visualizzare il XML del messaggio, fare clic su **XML**. Per inviarli al servizio, fare clic su **Invoke**.  
  
 Per un parametro di set di dati, fare clic su di **...** accanto alla **modifica...** per modificarlo in una nuova finestra che mostra la griglia dati. Si noti l'aspetto del **copia DataSet** e **Incolla DataSet** pulsanti. Se lo schema dell'oggetto the DataSet non è noto alla prima modifica, il DataGrid sarà vuoto. È necessario incollare un oggetto DataSet object con lo stesso schema nell'oggetto corrente nel DataGrid (tenere presente che è necessario copiare lo schema da un'altra posizione prima di incollare). È inoltre possibile copiare un oggetto set di dati per l'utilizzo futuro facendo il **copia DataSet** pulsante.  
  
 La risposta del servizio viene visualizzata sotto i parametri del test.  
  
> [!NOTE]
>  Se il valore restituito previsto è una stringa, il risultato verrà visualizzato come una stringa tra virgolette anche se l'input fornito non era tra virgolette.  
  
 Se una particolare operazione viene specificata come unidirezionale quando si crea il contratto per il servizio, non viene visualizzata alcuna risposta del servizio. Non appena il messaggio viene accodato per il recapito, viene visualizzata una finestra di dialogo per notificare che il messaggio è stato inviato correttamente.  
  
### <a name="session-support"></a>Supporto della sessione  
 Il **avvia un nuovo proxy** casella di controllo nella scheda dell'operazione del servizio consente abilitare o disabilitare il supporto della sessione. Per impostazione predefinita, la casella è deselezionata.  
  
 Quando si immettono parametri di test per un'operazione specifica (o un'altra operazione nello stesso endpoint del servizio) e fare clic su **Invoke** più volte con la casella di controllo deselezionata, tali operazioni condividono un unico proxy e lo stato del servizio è persistente tra più operazioni.  
  
 Se il **avvia un nuovo proxy** casella di controllo è selezionata, viene avviato un nuovo proxy per ogni **Invoke**, lo scenario di sessione precedente è stata interrotta e viene reimpostato lo stato del servizio.  
  
### <a name="editing-client-configuration"></a>Modifica della configurazione client  
 Il riquadro sinistro della finestra principale di Client di prova WCF sono elencati i file di configurazione client. Fare doppio clic su uno degli elementi per visualizzare il contenuto del file nel riquadro di destra.  
  
#### <a name="edit-with-service-configuration-editor"></a>Apportare modifiche con l'Editor configurazione servizi  
 Fare doppio clic su **File di configurazione** nel riquadro a sinistra e selezionare il menu di scelta rapida **modifica con SvcConfigEditor**. Editor configurazione servizi verrà avviato con il contenuto della configurazione client. Sarà possibile modificare la configurazione e salvarla all'interno dello strumento.  
  
 Dopo aver salvato il file nell'Editor di configurazione di servizio, Client di prova WCF viene visualizzato un messaggio di avviso per informare l'utente che il file è stato modificato all'esterno e chiede se si desidera ricaricarlo.  
  
 Se si seleziona **Sì**, il contenuto della configurazione nella scheda "Client" riflette le modifiche apportate nell'editor.  
  
 Se si seleziona **No**, il contenuto della configurazione nella scheda "Client" rimane invariato e il contenuto modificato viene salvato automaticamente nel file di origine.  
  
#### <a name="restore-to-default-configuration"></a>Ripristinare la configurazione predefinita  
 Se si desidera annullare tutte le modifiche e ripristinare la configurazione del client predefinito, fare doppio clic su **File di configurazione** nel riquadro a sinistra e selezionare il menu di scelta rapida **Ripristina configurazione predefinita**. Il valore di configurazione predefinito viene caricato e viene ripristinato il contenuto nella scheda "Client".  
  
#### <a name="validate-changes"></a>Convalidare le modifiche  
 Quando le modifiche salvate vengono caricate in Client di prova WCF, la configurazione viene verificata la validità rispetto allo schema WCF. Se vengono rilevati errori, verrà visualizzata una finestra di dialogo contenente i dettagli degli errori.  
  
 Durante la generazione proxy, compilazione binaria o di richiamo del servizio, voci di menu che supportano la modifica (vale a dire, "Modifica in corso", "Ripristino in corso" e così via) sono disabilitate. Chiamata al servizio risulta inoltre disattivata durante il caricamento configurazione aggiornata al Client di prova WCF.  
  
#### <a name="persist-client-configuration"></a>Rendere persistente la configurazione client  
 Il **degli strumenti**->**opzioni**->**configurazione Client** scheda contiene un **sempre rigenerare la configurazione durante l'avvio Servizi** opzione, che è abilitato per impostazione predefinita. Questa opzione specifica che ogni volta che il Client di prova WCF consente di caricare un servizio, viene rigenerato automaticamente in un file di configurazione in base al contratto di servizio più recente e il file app. config del servizio.  
  
 Se si hanno modificato la configurazione del client per il servizio WCF e si desidera usare sempre il file aggiornato per il debug del servizio, è possibile deselezionare le **rigenerare** opzione. In questo modo, anche quando si aggiorna il servizio e si riapre Client di prova WCF, il file client è quello aggiornato in precedenza anziché un rigenerato in base al servizio aggiornato.  
  
 Potrebbe tuttavia essere necessario modificare il file di configurazione per renderlo coerente con il proxy rigenerato. Se il proxy e file di configurazione rigenerati non corrispondono perché un servizio è stato aggiornato, si verificheranno errori quando il servizio viene richiamato.  
  
> [!CAUTION]
>  Se il file di configurazione client è stato modificato e si è scelto di riusarlo in futuro, il file sarà disponibile nel percorso seguente:  
>   
>  \Documents and Settings\\[Account utente] \My Documents\Test Client Projects.  
>   
>  Le informazioni sulle credenziali aggiornate archiviate nel file di configurazione client sono protette dall'elenco di controllo dell'accesso (ACL) di questa cartella.  
  
### <a name="adding-removing-and-refreshing-services"></a>Aggiunta, rimozione e aggiornamento di servizi  
  
#### <a name="add-service"></a>Aggiungere un servizio  
 Fare clic su **File**->**Aggiungi servizio** per aggiungere un servizio a Client di prova WCF. Verrà quindi richiesto di digitare l'URI (indirizzo endpoint) del servizio da aggiungere. L'indirizzo del servizio può corrispondere a un indirizzo mex o a un indirizzo WSDL.  
  
 È anche possibile trovare un elenco di endpoint 10 servizio aggiunti recentemente nel **vizi** sottomenu. Se si seleziona uno di essi, il servizio specificato viene aggiunto al Client di prova WCF.  
  
 È anche possibile fare doppio clic la radice dell'albero di servizio **progetti di servizi**e selezionare **Aggiungi servizio** per ottenere lo stesso risultato.  
  
 Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano l'aggiunta di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.  
  
#### <a name="remove-service"></a>Rimuovere un servizio  
 Fare doppio clic la radice del servizio del servizio da rimuovere, quindi scegliere **Rimuovi servizio** per rimuovere un servizio dal Client di prova WCF.  
  
 Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano la rimozione di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.  
  
#### <a name="refresh-service"></a>Aggiornare un servizio  
 Se viene apportata una modifica al servizio mentre Client di prova WCF è in esecuzione e si desidera assicurarsi che l'implementazione Client di prova WCF per il servizio sia aggiornato, fare doppio clic su radice del servizio e selezionare **Aggiorna servizio**. Si noti che dopo l'aggiornamento lo stato del servizio viene reimpostato.  
  
 Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano l'aggiornamento di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>Percorso dei file generati da Client di test  
 Per impostazione predefinita, i file di codice e la configurazione client gli archivi di Client di prova WCF generati nella cartella "%appdata%\Local\temp\Test Client Projects". Questa cartella viene eliminata dopo la chiusura di Client di prova WCF. Se un file di configurazione viene modificato in Client di prova WCF e il **Rigenera sempre Config durante l'avvio dei servizi** opzione è disabilitata, il file modificato viene copiato nella cartella "CachedConfig" sotto "My Documents\Test Client Projects" con un file XML (metadati-indirizzo-a-file-name) mapping come indice.  
  
 È anche possibile avviare il Client di prova WCF in una riga di comando, usare il `/ProjectPath` per specificare un percorso desiderato per l'archiviazione dei file generati oppure usare il `/RestoreProjectPath` switch per ripristinare il percorso predefinito. La sintassi è la seguente:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Questo comando non viene aperto il Client di prova WCF. ma solo la modifica del percorso della cartella. È possibile eseguire questo comando se il Client di prova WCF è in esecuzione o meno. La nuova posizione viene applicata quando il Client di prova WCF viene riavviato. Le informazioni sulla posizione possono essere salvati nel Registro di sistema o nel file WcfTestClient nella cartella "%appdata%\Local\temp\Test Client Projects".  
  
## <a name="features-supported-by-wcf-test-client"></a>Funzioni supportate da Client di prova WCF  
 Di seguito è riportato un elenco delle funzionalità supportate da Client di prova WCF:  
  
-   Chiamata al servizio: Richiesta/risposta e unidirezionale.  
  
-   Associazioni: tutte le associazioni supportate da Svcutil.exe.  
  
-   Controllo della sessione.  
  
-   Contratto di messaggio.  
  
-   Serializzazione XML.  
  
 Di seguito è riportato un elenco di funzionalità non supportate dal Client di prova WCF:  
  
-   Tipi: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipi che implementano l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>, tra cui l'attributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> correlato, i tipi <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement> e il tipo <xref:System.Data.DataTable> di ADO.NET.  
  
-   Contratto duplex.  
  
-   Transazione.  
  
-   Sicurezza: [!INCLUDE[infocard](../../../includes/infocard-md.md)], certificato e nome utente/password.  
  
-   Binding: WSFederationbinding, qualsiasi associazione Context e associazione Https, WebHttpbinding (supporto di messaggi di risposta Json).  
  
## <a name="closing-wcf-test-client"></a>Chiusura di Client di test WCF  
 È possibile chiudere Client di prova WCF nei modi seguenti:  
  
-   Nel **File** menu, fare clic su **uscita**. In alternativa, nella finestra principale di Client di prova WCF fare clic su **Chiudi**. Entrambe queste azioni anche arrestare Host automatico servizio di WCF e arrestare il processo di debug di Visual Studio, se il Client di prova WCF è stato avviato da Visual Studio.  
  
-   Fare doppio clic il **Host servizio WCF** icona nell'area di notifica e quindi fare clic su **Exit.** Questo chiude sia Host automatico servizio WCF che Client di prova WCF e si arresta il processo di debug di Visual Studio.  
  
## <a name="see-also"></a>Vedere anche

- [Host servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
