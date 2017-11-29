---
title: Client di test WCF (WcfTestClient.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
caps.latest.revision: "45"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc189ab1c68edfc41267e493a6ca6bccf9fe519a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-test-client-wcftestclientexe"></a>Client di test WCF (WcfTestClient.exe)
Client di test [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfTestClient.exe) è un strumento GUI che consente agli utenti di immettere parametri di test, inviare l'input immesso al servizio e visualizzare la risposta restituita dal servizio. In combinazione con Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] offre una funzione di test del servizio trasparente.  
  
 Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) è disponibile nel percorso seguente: C:\Programmi\Microsoft Visual Studio 9.0\Common7\IDE\  
  
## <a name="scenarios-for-using-test-client"></a>Scenari per l'uso di Client di test  
 Nelle sezioni seguenti sono illustrati gli scenari più comuni nei quali è possibile usare Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per semplificare il processo di sviluppo.  
  
### <a name="inside-visual-studio"></a>All'interno di Visual Studio  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>Host servizio WCF avvia Client di test WCF con un solo servizio  
 Dopo avere creato un nuovo progetto di servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e avere premuto F5 per avviare il debugger, Servizio Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] avvia l'hosting del servizio nel progetto. Quindi, Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] apre e visualizza un elenco degli endpoint di servizio definiti nel file di configurazione. È possibile testare i parametri e richiamare il servizio e ripetere il processo per testare e convalidare continuamente il servizio.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>Host servizio WCF avvia Client di test WCF con più servizi  
 È inoltre possibile usare Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per il debug di un progetto di servizio contenente più servizi. All'apertura, Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] esegue automaticamente l'iterazione dell'elenco dei servizi nel progetto e li apre per il test.  
  
### <a name="outside-visual-studio"></a>All'esterno di Visual Studio  
 È inoltre possibile richiamare Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) dall'esterno di Visual Studio per eseguire il test di un servizio arbitrario su Internet. Per individuare lo strumento, passare al percorso seguente:  
  
 C:\Programmi\Microsoft Visual Studio 9.0\Common7\IDE\  
  
 Per usare lo strumento, fare doppio clic sul nome del file per aprirlo da questo percorso oppure avviarlo da una riga di comando.  
  
 Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usa un numero arbitrario di URI come argomenti della riga di comando.  Di seguito sono riportati gli URI dei servizi che è possibile sottoporre a test.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Dopo il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] finestra Client di Test viene aperto, fare clic su **File**->**Aggiungi servizio**, quindi immettere l'indirizzo dell'endpoint del servizio che si desidera aprire.  
  
## <a name="wcf-test-client-user-interface"></a>Interfaccia utente di Client di test WCF  
 È possibile usare Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con uno o più servizi.  
  
### <a name="service-operations"></a>Operazioni di servizio  
 Nel riquadro di sinistra della finestra principale di Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sono elencati tutti i servizi disponibili, insieme ai rispettivi endpoint e operazioni.  
  
 Quando si fa doppio clic su un'operazione, è possibile visualizzare il relativo contenuto nel riquadro di destra all'interno di una nuova scheda con il nome dell'operazione.  
  
 Nel riquadro di sinistra sono elencati i anche file di configurazione client. Fare doppio clic sugli elementi per visualizzare il contenuto del file in una nuova finestra a schede nel riquadro di destra.  
  
### <a name="entering-test-parameters"></a>Immissione dei parametri del test  
 Per visualizzare i parametri del test, fare doppio clic su un'operazione per aprirla nel riquadro di destra. I parametri vengono mostrati **formattato** Visualizza per impostazione predefinita ed è possibile immettere valori arbitrari per i parametri testare il servizio.  
  
 Per visualizzare il XML del messaggio, fare clic su **XML**. Per inviarli al servizio, fare clic su **Invoke**.  
  
 Per un parametro di set di dati, fare clic su di **...** accanto al pulsante **modifica...** per modificarlo in una nuova finestra che mostra la griglia dati. Si noti l'aspetto del **copia DataSet** e **Incolla DataSet** pulsanti. Se lo schema dell'oggetto the DataSet non è noto alla prima modifica, il DataGrid sarà vuoto. È necessario incollare un oggetto DataSet object con lo stesso schema nell'oggetto corrente nel DataGrid (tenere presente che è necessario copiare lo schema da un'altra posizione prima di incollare). È inoltre possibile copiare un oggetto set di dati per l'utilizzo futuro facendo il **copia DataSet** pulsante.  
  
 La risposta del servizio viene visualizzata sotto i parametri del test.  
  
> [!NOTE]
>  Se il valore restituito previsto è una stringa, il risultato verrà visualizzato come una stringa tra virgolette anche se l'input fornito non era tra virgolette.  
  
 Se una particolare operazione viene specificata come unidirezionale quando si crea il contratto per il servizio, non viene visualizzata alcuna risposta del servizio. Non appena il messaggio viene accodato per il recapito, viene visualizzata una finestra di dialogo per notificare che il messaggio è stato inviato correttamente.  
  
### <a name="session-support"></a>Supporto della sessione  
 Il **avvia un nuovo proxy** casella di controllo nella scheda dell'operazione del servizio consente di attivare o disattivare il supporto della sessione. Per impostazione predefinita, la casella è deselezionata.  
  
 Quando si immettono i parametri di test per un'operazione specifica (o un'altra operazione nell'endpoint del servizio stesso) e fare clic su **Invoke** più volte con la casella di controllo deselezionata, tali operazioni condividono un unico proxy e lo stato del servizio è persistente tra più operazioni.  
  
 Se il **avvia un nuovo proxy** casella di controllo è selezionata, viene avviato un nuovo proxy per ogni **Invoke**, lo scenario di sessione precedente è stato terminato e viene reimpostato lo stato del servizio.  
  
### <a name="editing-client-configuration"></a>Modifica della configurazione client  
 Nel riquadro di sinistra della finestra principale del Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sono elencati i file di configurazione client. Fare doppio clic su uno degli elementi per visualizzare il contenuto del file nel riquadro di destra.  
  
#### <a name="edit-with-service-configuration-editor"></a>Apportare modifiche con l'Editor configurazione servizi  
 Fare doppio clic su **File di configurazione** nel riquadro sinistro e selezionare il menu di scelta rapida **modifica con SvcConfigEditor**. Editor configurazione servizi verrà avviato con il contenuto della configurazione client. Sarà possibile modificare la configurazione e salvarla all'interno dello strumento.  
  
 Dopo avere salvato il file nell'Editor di configurazione dei servizi, Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] visualizzerà un messaggio di avviso per informare che il file è stato modificato all'esterno e chiedere se si desidera ricaricarlo.  
  
 Se si seleziona **Sì**, il contenuto della configurazione nella scheda "Client.dll. config" rifletterà le modifiche apportate nell'editor.  
  
 Se si seleziona **n**, il contenuto della configurazione nella scheda "Client.dll. config" rimarrà invariato e il contenuto modificato viene salvato automaticamente al file di origine.  
  
#### <a name="restore-to-default-configuration"></a>Ripristinare la configurazione predefinita  
 Se si desidera annullare tutte le modifiche e ripristinare la configurazione del client predefinito, fare doppio clic su **File di configurazione** nel riquadro sinistro e selezionare il menu di scelta rapida **Ripristina configurazione predefinita**. Il valore di configurazione predefinito viene caricato e viene ripristinato il contenuto nella scheda "Client.dll. config".  
  
#### <a name="validate-changes"></a>Convalidare le modifiche  
 Quando le modifiche salvate vengono caricate in Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], viene verificata la validità della configurazione rispetto allo schema [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Se vengono rilevati errori, verrà visualizzata una finestra di dialogo contenente i dettagli degli errori.  
  
 Durante la generazione del proxy, compilazione binaria o di richiamo del servizio, le voci di menu che supportano la modifica (vale a dire, "Modifica...", "Restore …" e così via) sono disabilitate. La chiamata del servizio risulta inoltre disattivata durante il caricamento della configurazione aggiornata in Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
#### <a name="persist-client-configuration"></a>Rendere persistente la configurazione client  
 Il **strumenti**->**opzioni**->**configurazione Client** scheda contiene un **sempre rigenerare la configurazione durante l'avvio Servizi** opzione, abilitata per impostazione predefinita. Questa opzione specifica che ogni volta che Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] carica un servizio, il file di configurazione viene rigenerato automaticamente in base ai file App.config del contratto di servizio e del servizio più recenti.  
  
 Se è stata modificata la configurazione del client per il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizio e si desidera usare sempre il file aggiornato per eseguire il debug del servizio, è possibile deselezionare il **rigenerare** opzione. In tal modo, anche quando si aggiorna il servizio e si riapre Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], il file Client.dll.config corrisponderà a quello aggiornato in precedenza dall'utente anziché a un file rigenerato in base al servizio aggiornato.  
  
 Potrebbe tuttavia essere necessario modificare il file di configurazione per renderlo coerente con il proxy rigenerato. Se il proxy e file di configurazione rigenerati non corrispondono perché un servizio è stato aggiornato, si verificheranno errori quando il servizio viene richiamato.  
  
> [!CAUTION]
>  Se il file di configurazione client è stato modificato e si è scelto di riusarlo in futuro, il file sarà disponibile nel percorso seguente:  
>   
>  \Documents and Settings\\[Account utente] \My Documents\Test Client Projects.  
>   
>  Le informazioni sulle credenziali aggiornate archiviate nel file di configurazione client sono protette dall'elenco di controllo dell'accesso (ACL) di questa cartella.  
  
### <a name="adding-removing-and-refreshing-services"></a>Aggiunta, rimozione e aggiornamento di servizi  
  
#### <a name="add-service"></a>Aggiungere un servizio  
 Fare clic su **File**->**Aggiungi servizio** per aggiungere un servizio a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di Test. Verrà quindi richiesto di digitare l'URI (indirizzo endpoint) del servizio da aggiungere. L'indirizzo del servizio può corrispondere a un indirizzo mex o a un indirizzo WSDL.  
  
 È inoltre possibile trovare un elenco di endpoint 10 servizio aggiunti recentemente nel **servizi recenti** sottomenu. Se si seleziona uno di questi endpoint, il servizio specificato verrà aggiunto a Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 È anche possibile fare doppio clic la radice dell'albero del servizio **progetti di servizi**e selezionare **Aggiungi servizio** per ottenere lo stesso risultato.  
  
 Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano l'aggiunta di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.  
  
#### <a name="remove-service"></a>Rimuovere un servizio  
 Fare doppio clic sulla radice del servizio del servizio da rimuovere e selezionare **Rimuovi servizio** per rimuovere un servizio da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di Test.  
  
 Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano la rimozione di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.  
  
#### <a name="refresh-service"></a>Aggiornare un servizio  
 Se viene apportata una modifica al servizio mentre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è in esecuzione il Client di Test e si desidera assicurarsi che il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementazione Client di Test per il servizio è aggiornato, la radice del servizio del servizio e scegliere **Aggiorna Servizio**. Si noti che dopo l'aggiornamento lo stato del servizio viene reimpostato.  
  
 Durante il processo di generazione proxy, di compilazione binaria o di richiamo del servizio, le voci di menu che supportano l'aggiornamento di un servizio risultano disabilitate. Anche la chiamata del servizio è disabilitata.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>Percorso dei file generati da Client di test  
 Per impostazione predefinita, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] archivia di Client di prova generati file di codice e la configurazione di client nella cartella "%appdata%\Local\temp\Test Client Projects". Questa cartella viene eliminata dopo la chiusura di Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Se un file di configurazione viene modificato in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di prova e **sempre rigenerare la configurazione all'avvio dei servizi** opzione è disabilitata, il file modificato verrà copiato nella cartella "Cached Config" nel percorso personale" Client Projects Documents\Test Client Projects"con un file XML di mapping (metadati-indirizzo-a--nome file) come indice.  
  
 È inoltre possibile avviare Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in una riga di comando, usare l'opzione `/ProjectPath` per specificare il percorso desiderato per l'archiviazione dei file generati oppure usare l'opzione `/RestoreProjectPath` per ripristinare il percorso predefinito. La sintassi è la seguente:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 L'esecuzione di questo comando non determina l'apertura di Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], ma solo la modifica del percorso della cartella. È possibile eseguire questo comando indipendentemente dal fatto che Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sia o meno in esecuzione. Il nuovo percorso verrà applicato al riavvio di Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Le informazioni sul percorso possono essere salvati nel Registro di sistema o nel file WcfTestClient.exe Option nella cartella "%appdata%\Local\temp\Test Client Projects".  
  
## <a name="features-supported-by-wcf-test-client"></a>Funzionalità supportate da Client di prova WCF  
 Nell'elenco seguente sono incluse le funzionalità supportate da Client di prova [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Chiamata al servizio: messaggio di richiesta/risposta e unidirezionale.  
  
-   Associazioni: tutte le associazioni supportate da Svcutil.exe.  
  
-   Controllo della sessione.  
  
-   Contratto di messaggio.  
  
-   Serializzazione XML.  
  
 Nell'elenco seguente sono incluse le funzionalità non supportate da Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Tipi: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipi che implementano l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>, tra cui l'attributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> correlato, i tipi <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement> e il tipo <xref:System.Data.DataTable> di ADO.NET.  
  
-   Contratto duplex.  
  
-   Transazione.  
  
-   Sicurezza: [!INCLUDE[infocard](../../../includes/infocard-md.md)], certificato e nome utente/password.  
  
-   Associazioni: WSFederationbinding, qualsiasi associazione Context e associazione Https, WebHttpbinding (supporto per messaggi di riposta Json).  
  
## <a name="closing-wcf-test-client"></a>Chiusura di Client di test WCF  
 È possibile chiudere CLient di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] nei seguenti modi:  
  
-   Nel **File** menu, fare clic su **uscita**. In alternativa, nel [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] finestra principale del Client di Test, fare clic su **Chiudi**. Entrambe le azioni determinano inoltre l'arresto di Host automatico servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e l'interruzione del processo di debug di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] se Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è stato avviato da [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
-   Fare doppio clic su di **Host servizio WCF** sull'icona nell'area di notifica e quindi fare clic su **uscita.** Questo chiude sia Host automatico servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] che Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e arresta il processo di debug di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
