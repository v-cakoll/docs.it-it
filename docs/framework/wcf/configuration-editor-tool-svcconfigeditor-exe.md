---
title: Strumento Editor di configurazione (SvcConfigEditor.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 75657786135fd13222c6c7edd5acfa122cc72e52
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a>Strumento Editor di configurazione (SvcConfigEditor.exe)
L'Editor di configurazione dei servizi di Windows Communication Foundation (WCF), ovvero il file SvcConfigEditor.exe, consente ad amministratori e sviluppatori di creare e modificare le impostazioni di configurazione dei servizi WCF tramite un'interfaccia utente grafica (GUI). Con questo strumento è possibile gestire le impostazioni di associazioni, comportamenti, servizi e diagnostica WCF senza la necessità di modificare direttamente i file di configurazione XML.  
  
 L'Editor di configurazione dei servizi si trova nella cartella C:\Programmi\Microsoft SDKs\Windows\v6.0\Bin.  
  
## <a name="the-wcf-configuration-editor"></a>Editor di configurazione dei servizi di WCF  
 L’Editor di configurazione dei servizi dispone di una procedura guidata che descrive le fasi per configurare un servizio o un client WCF. Si consiglia di utilizzare direttamente la procedura guidata anziché l'editor.  
  
 Se si dispone già di alcuni file di configurazione conformi allo schema System.Configuration standard, tramite l'interfaccia utente è possibile gestire impostazioni specifiche relative ad associazioni, comportamenti, servizi e diagnostica. Oltre alle impostazioni dei file di configurazione di WCF esistenti, l’Editor di configurazione dei servizi consente di gestire file eseguibili, servizi COM+ e servizi ospitati su Web. Quando si apre un servizio ospitato su Web con l'Editor di configurazione dei servizi, vengono visualizzate sia la configurazione del servizio stesso che le sezioni di configurazione ereditate dei nodi di livello superiore.  
  
 Dato che le impostazioni di configurazione di WCF si trovano nella sezione `<system.serviceModel>` del file di configurazione, l'editor opera esclusivamente sul contenuto di questo elemento e non accede gli altri elementi nello stesso file. È possibile accedere direttamente ai file di configurazione esistenti oppure selezionare un assembly contenente un servizio, una directory virtuale o un servizio COM+. L'editor carica il file di configurazione per quel particolare servizio e consente all'utente di aggiungere elementi nuovi o di modificare elementi esistenti annidati nella sezione `<system.serviceModel>` del file di configurazione.  
  
 L'editor supporta IntelliSense e richiede la conformità con lo schema. L'editor garantisce che l’output risultante sia conforme con lo schema del file di configurazione e che i valori dei dati siano sintatticamente corretti. Tuttavia, l'editor non garantisce che il file di configurazione siano semanticamente validi. In altre parole, l'editor non garantisce che il file di configurazione pussa funzionare con il servizio che configura.  
  
> [!CAUTION]
>  L'editor non può cancellare un elemento di configurazione dal file di configurazione una volta che l’elemento è stato modificato. Ad esempio, se si utilizza l'editor per impostare il nome dell'endpoint su una stringa non vuota e per salvarlo, il file di configurazione avrà il contenuto mostrato nell'esempio seguente:  
>   
>  `<endpoint binding="basicHttpBinding" name="somename" />`  
>   
>  Se si tenta di rimuovere il nome impostandolo su una stringa vuota e salvando il file, il file di configurazione contiene ancora l'attributo `name`, come mostrato nell'esempio seguente.  
>   
>  `<endpoint binding="basicHttpBinding" name="" />`  
>   
>  Per cancellare l'attributo si deve modificare manualmente l'elemento utilizzando un altro editor di testo.  
>   
>  È necessario prestare particolare attenzione a questo problema quando si utilizza l'elemento `issueToken` del comportamento dell’endpoint `clientCredential`. In particolare, l'attributo `address` del sottoelemento `localIssuer` non deve essere una stringa vuota. Se si è modificato l'attributo `address` utilizzando l'Editor di configurazione e si desidera rimuoverlo completamente, è necessario utilizzare uno strumento diverso dall'Editor. In caso contrario, l'attributo conterrà una stringa vuota e l'applicazione genererà un'eccezione.  
  
## <a name="using-the-configuration-editor"></a>Utilizzo dell’Editor di configurazione  
 L'Editor di configurazione dei servizi si trova nel seguente percorso di installazione di Windows SDK:  
  
 C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe  
  
 Dopo aver avviato l'Editor di configurazione del servizio, è possibile utilizzare il **File/Apri** menu per cercare il servizio o l'assembly che si desidera gestire. È possibile aprire direttamente file di configurazione, cercare i servizi WCF /COM+ e aprire i file di configurazione per i servizi ospitati su Web.  
  
 L'interfaccia utente dell'Editor di configurazione dei servizi è suddivisa nelle aree seguenti:  
  
-   Il riquadro di visualizzazione albero, in cui gli elementi di configurazione sono visualizzati in una struttura ad albero a sinistra. Per eseguire operazioni sull'albero è possibile fare clic con il pulsante destro del mouse sui nodi.  
  
-   Il riquadro attività, in cui le attività comuni degli elementi correnti sono visualizzate nell'angolo inferiore sinistro della finestra.  
  
-   Il riquadro dettagli, in cui vengono visualizzate le impostazioni dettagliate del nodo di configurazione selezionato nella visualizzazione albero a destra.  
  
### <a name="opening-a-configuration-file"></a>Apertura di un file di configurazione  
  
1.  Avviare l'Editor configurazione servizi utilizzando una finestra di comando per passare al percorso di installazione di WCF e quindi digitare `SvcConfigEditor.exe`.  
  
2.  Dal **File** dal menu **aprire** e fare clic sul tipo di file che si desidera gestire.  
  
3.  Nel **aprire** finestra di dialogo casella, passare al file specifico che si desidera gestire e fare doppio clic.  
  
 Il visualizzatore segue automaticamente il percorso del merge delle configurazioni e crea una visualizzazione della configurazione unita. Ad esempio, la configurazione effettiva di un servizio non ospitato è una combinazione di Machine.config e App.config. Le modifiche vengono apportate al file attivo nell'editor SvcConfigEditor. Se si desidera modificare un file specifico all'interno del percorso di unione delle configurazioni, è necessario aprirlo direttamente.  
  
> [!NOTE]
>  L'Editor di configurazione ricarica il file di configurazione attualmente aperto quando quest’ultimo è stato modificato fuori dell'Editor. Quando si verifica questa condizione, tutte le modifiche che non sono state salvate in modo durevole nell'Editor verranno perse. Se il nuovo caricamento si verifica costantemente, la causa più probabile è un servizio che accede continuamente al file di configurazione, ad esempio un software antivirus in esecuzione in background. Per risolvere questo problema, assicurarsi che l'Editor di configurazione sia l’unico processo solo che può accedere al file quando è aperto.  
  
### <a name="services"></a>Servizi  
 Il **servizi** nodo consente di visualizzare tutti i servizi attualmente assegnati nel file di configurazione. Ogni nodo secondario nella struttura corrisponde a un sottoelemento di <`services`> elemento nel file di configurazione.  
  
 Quando si fa clic il **servizi** nodo, è possibile visualizzare o eseguire attività nel servizio di pagina di riepilogo di **dettaglio** riquadro.  
  
#### <a name="creating-a-new-service-configuration"></a>Creazione di una nuova configurazione di un servizio  
 Per creare una nuova configurazione di un servizio, è possibile procedere nei modi seguenti:  
  
-   Tramite una procedura guidata: fare clic sul collegamento **creare un nuovo servizio...** nel riquadro attività o nella pagina di riepilogo per avviare la procedura guidata. È inoltre possibile eseguire questa operazione nel **File** -> menu **Aggiungi nuovo elemento**.  
  
-   Creare manualmente: È possibile fare doppio clic il **servizi** nodo e scegliere **nuovo servizio**.  
  
#### <a name="creating-a-new-service-endpoint-configuration"></a>Creazione di una nuova configurazione di endpoint di servizio  
 Per creare una nuova configurazione di endpoint di servizio, è possibile procedere nei modi seguenti:  
  
-   Creazione tramite una procedura guidata: fare clic sul collegamento **creare un nuovo Endpoint del servizio...** nel riquadro attività o nella pagina di riepilogo per avviare la procedura guidata. È inoltre possibile eseguire questa operazione nel **File** -> menu **Aggiungi nuovo elemento**.  
  
-   Creare manualmente: una volta creato un servizio, è possibile fare doppio clic il **endpoint** nodo e scegliere "**nuovo Endpoint del servizio**".  
  
#### <a name="editing-a-service-configuration"></a>Modifica della configurazione di un servizio  
  
1.  Fare clic su un **servizio** nodo.  
  
2.  Modificare le impostazioni nelle griglie delle proprietà.  
  
#### <a name="editing-a-service-endpoint-configuration"></a>Modifica della configurazione di un endpoint di servizio  
  
1.  Fare clic su un **Endpoint del servizio** nodo.  
  
2.  Modificare le impostazioni nelle griglie delle proprietà.  
  
#### <a name="adding-a-base-address"></a>Aggiunta di un indirizzo di base  
  
1.  Fare clic su di **Host** nodo.  
  
2.  Fare clic sul **New...** pulsante di **gli indirizzi di Base** sezione.  
  
3.  Immettere l'indirizzo URI di base nella finestra di dialogo.  
  
4.  Fare clic su **OK**.  
  
> [!NOTE]
>  Non è possibile modificare il valore di [ \<baseAddressPrefixFilters >](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) all'interno di questo strumento. Per aggiungere o modificare questo elemento è necessario utilizzare un editor di testo o Visual Studio.  
  
### <a name="client"></a>Client  
 Il **Client** nodo consente di visualizzare tutti gli endpoint client nel file di configurazione. Ogni nodo secondario nella struttura corrisponde a un sottoelemento di <`client`> elemento nel file di configurazione.  
  
 Quando si fa clic il **Client** nodo, è possibile visualizzare o eseguire attività sul client **pagina riepilogo** nel **riquadro dei dettagli**.  
  
#### <a name="creating-a-new-client-endpoint-configuration"></a>Creazione di una nuova configurazione di endpoint client  
 Per creare una nuova configurazione di endpoint client, è possibile procedere nei modi seguenti:  
  
-   Creazione tramite procedura guidata: fare clic sul collegamento **creare un nuovo Client...** nel **riquadro** in basso a sinistra della finestra, o **pagina riepilogo** per avviare la procedura guidata. È inoltre possibile eseguire questa operazione nel **File** -> menu **Aggiungi nuovo elemento**. Verrà richiesto di individuare la posizione della configurazione del servizio, da cui viene generata la configurazione client. A questo punto è possibile specificare l'endpoint del servizio a cui connettersi.  
  
-   Creare manualmente: destro la **endpoint** nodo **Client**e scegliere **nuovo Endpoint Client**.  
  
#### <a name="editing-a-client-endpoint-configuration"></a>Modifica di una configurazione di endpoint client  
  
1.  Fare clic su un **Endpoint Client** nodo.  
  
2.  Modificare le impostazioni nelle griglie delle proprietà.  
  
### <a name="standard-endpoint"></a>Endpoint standard  
 Gli endpoint standard sono endpoint specializzati in cui uno o più aspetti dell'indirizzo, del contratto e dell'associazione sono impostati sui valori predefiniti.  
  
 Tali impostazioni di configurazione vengono archiviate nel **Endpoint Standard** nodo. Il **Endpoint Standard** nodo consente di visualizzare tutte le impostazioni di endpoint standard nel file di configurazione. Ogni nodo secondario nella struttura corrisponde a un sottoelemento dell'elemento nel `<standardEndpoints>` elemento nel file di configurazione.  
  
 Quando si fa clic il **Endpoint Standard** nodo, è possibile visualizzare o eseguire attività di endpoint standard **pagina riepilogo** nel **riquadro dei dettagli**.  
  
#### <a name="creating-a-new-standard-endpoint-configuration"></a>Creazione di una nuova configurazione di endpoint standard  
 Per creare una nuova configurazione di endpoint standard, è possibile procedere nei modi seguenti:  
  
-   Fare doppio clic sui **Standardendpointelement** nodo e selezionare **configurazione nuovo Endpoint Standard...** Selezionare il tipo di associazione nella finestra di dialogo e fare clic su **OK**.  
  
-   Selezionare il **Standardendpointelement** nodo e fare clic su **configurazione nuovo Endpoint Standard...** nel **riquadro** in basso a sinistra della finestra.  
  
 Il **creando un nuovo Endpoint Standard** la finestra di dialogo Visualizza ed elenca registrati tutti i tipi di endpoint standard.  
  
#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a>Visualizzazione e modifica di una configurazione di endpoint standard  
 Per aprire una configurazione di endpoint standard per la visualizzazione e la modifica, è possibile procedere nei modi seguenti:  
  
-   Fare clic per espandere il **Endpoint Standard** nodo e fare clic sul sottonodo rispettivi endpoint.  
  
-   Fare clic su di **Endpoint Standard** nodo e fare clic sul rispettivo endpoint nel riquadro dei dettagli.  
  
 Gli attributi dell'endpoint vengono visualizzati nel riquadro di destra per la modifica.  
  
#### <a name="deleting-a-standard-endpoint-configuration"></a>Eliminazione di una configurazione di endpoint standard  
 Per eliminare una configurazione di endpoint standard, è possibile procedere nei modi seguenti:  
  
-   Fare clic per espandere il **Endpoint Standard** nodo e pulsante destro del mouse sul sottonodo dell'endpoint corrispondente. Utilizzare il comando di contesto **Elimina configurazione Endpoint Standard** eliminare l'endpoint.  
  
-   Fare clic su di **Endpoint Standard** nodo. Nel **attività** riquadro, fare clic su **Elimina configurazione Endpoint Standard**.  
  
 Se si utilizza l'endpoint standard, viene visualizzato un messaggio di avviso quando si tenta di eliminarlo: **Endpoint standard in uso. Se lo si elimina ora, assicurarsi di eliminare tutti i relativi riferimenti presenti in altre parti della configurazione (ad esempio, nell'endpoint del servizio). In caso contrario la configurazione non sarà valida e non potrà essere aperta in seguito. Confermare se che si desidera eliminare l'endpoint standard?"**  
  
### <a name="binding"></a>Binding  
 Le configurazioni di associazione consentono di configurare le associazioni sugli endpoint. Tali impostazioni di configurazione vengono archiviate nel **associazione** nodo. Gli endpoint fanno riferimento alle configurazioni di associazione in base al nome. Inoltre, più endpoint possono fare riferimento a una stessa configurazione di associazione.  
  
 Il **associazioni** nodo vengono visualizzate tutte le impostazioni dell'associazione nel file di configurazione. Ogni nodo secondario nella struttura corrisponde a un sottoelemento dell'elemento nel <`bindings`> elemento nel file di configurazione.  
  
 Quando si fa clic il **associazioni** nodo, è possibile visualizzare o eseguire operazioni sull'associazione **pagina riepilogo** nel **riquadro dei dettagli**.  
  
#### <a name="creating-a-new-binding-configuration"></a>Creazione di una nuova configurazione di associazione  
 Per creare una nuova configurazione dell’associazione, è possibile procedere nei modi seguenti.  
  
-   Fare doppio clic su di **associazioni** nodo e selezionare **nuova configurazione dell'associazione**... Selezionare il tipo di associazione nella finestra di dialogo e fare clic su **OK**.  
  
-   Selezionare il **associazioni** nodo e fare clic su **nuova configurazione dell'associazione**... nel **riquadro** in basso a sinistra della finestra.  
  
-   Nella pagina Riepilogo servizio o client, fare clic su **fare clic per creare** nel **configurazione dell'associazione** campo per creare una configurazione di associazione per l'endpoint corrispondente.  
  
#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a>Aggiunta di estensioni degli elementi di associazione a un'associazione personalizzata  
  
1.  Selezionare l'associazione a cui si desidera aggiungere un elemento di estensione.  
  
2.  Fare clic su **Aggiungi**.  
  
3.  Nell'elenco di estensioni disponibili, selezionare l'estensione degli elementi di associazione che si desidera aggiungere. Per selezionare più elementi, premere contemporaneamente CTRL.  
  
4.  Fare clic su **Aggiungi**.  
  
#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a>Impostazione della posizione dell'estensione in un'associazione personalizzata  
 Un'associazione personalizzata è una raccolta di elementi di associazione organizzati in uno stack. Ogni elemento di associazione dello stack può essere configurato in modo specifico. L'ordine delle estensioni degli elementi di associazione in un'associazione personalizzata indica la posizione occupata da ogni estensione nello stack. Gli elementi all'inizio dello stack vengono applicati per primi. Per modificare l'ordine:  
  
1.  Selezionare il nodo dell'associazione personalizzata.  
  
2.  Selezionare un elemento di estensione di associazione nel **posizione dell'estensione di elemento di associazione** sezione.  
  
3.  Utilizzare il **backup** o **verso il basso** pulsante sul lato sinistro dell'elenco per modificare la posizione dell'elemento selezionato.  
  
#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a>Modifica della configurazione di estensioni degli elementi di associazione in un'associazione personalizzata  
  
1.  Selezionare il nodo dell'associazione nell'albero.  
  
2.  Selezionare l'associazione personalizzata contenente l'elemento che si desidera modificare.  
  
3.  Selezionare l'estensione degli elementi di associazione che si desidera modificare. Le impostazioni dell'elemento verranno visualizzate nel riquadro di destra, in cui è inoltre possibile modificarle.  
  
### <a name="diagnostics"></a>Diagnostica  
 Il **diagnostica** nodo vengono visualizzate tutte le impostazioni di diagnostica nel file di configurazione. Consente di attivare o disattivare la contatori delle prestazioni, abilitare o disabilitare Strumentazione gestione Windows (WMI), configurare la traccia WCF e configurare la registrazione dei messaggi WCF. Le impostazioni di **diagnostica** nodo corrisponde al <`system.diagnostics`> sezione e `<diagnostics>` sezione `<system.serviceModel>` nel file di configurazione.  
  
 Quando si fa clic il **diagnostica** nodo, è possibile visualizzare o eseguire attività di diagnostica **pagina riepilogo** nel **riquadro dei dettagli**.  
  
#### <a name="configuring-performance-counters-and-wmi"></a>Configurazione dei contatori delle prestazioni e di WMI  
  
1.  Fare clic su di **diagnostica** nodo.  
  
2.  Fare clic su **attivare o disattivare i contatori delle prestazioni**. Il contatore delle prestazioni prevede tre stati: Disattivo (predefinito), Solo servizio e Tutto. Il collegamento consente di attivare/disattivare l'impostazione degli stati.  
  
#### <a name="configuring-wmi-provider"></a>Configurazione del provider WMI  
  
1.  Fare clic su di **diagnostica** nodo.  
  
2.  Per abilitare il provider WMI, fare clic su di **Abilita Provider WMI** collegamento.  
  
#### <a name="enabling-wcf-tracing"></a>Abilitazione della traccia WCF  
 È possibile creare un file di traccia WCF con le proprietà standard oppure configurare un file di log personalizzato.  
  
1.  Fare clic su di **diagnostica** nodo.  
  
2.  Fare clic su **abilitare la traccia**.  
  
3.  Fare clic su di **livello di traccia** collegamento per regolare il livello di traccia. Esistono sei livelli di traccia: Disattivo, Critico, Errore, Avviso, Informazioni e Dettagliato. Il **la traccia attività** e **Propaga attività** opzione consentono di usare la funzionalità di traccia di attività WCF.  
  
4.  Fare clic sul nome del listener di traccia per specificare il file e le opzioni di traccia.  
  
#### <a name="enabling-wcf-logging"></a>Abilitazione della registrazione WCF  
 È possibile creare un file di traccia WCF con le proprietà standard oppure configurare un file di log personalizzato.  
  
1.  Fare clic su di **diagnostica** nodo.  
  
2.  Fare clic su **abilitare la registrazione dei messaggi**.  
  
3.  Fare clic su di **livello di registrazione** collegamento per regolare il livello di registrazione. Esistono tre livelli di log: Messaggi in formato non valido, Messaggi servizio e Messaggi trasporto.  
  
4.  Fare clic sul nome del listener per specificare le opzioni e il file di log.  
  
> [!NOTE]
>  Se si desidera che i registri di traccia e dei messaggi per essere scaricato automaticamente alla chiusura dell'applicazione, abilitare il **cancellazione automatica registro** opzione.  
  
 Il **diagnostica** **pagina riepilogo** consente di eseguire le attività più comuni di configurazione di diagnostica. Tuttavia, se si desidera modificare manualmente le impostazioni listener e origini, è necessario espandere il **diagnostica** nodo e modificare le impostazioni in **registrazione messaggi**, **listener** e **Origini** nodo.  
  
#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a>Abilitazione della traccia o della registrazione dei messaggi personalizzata di WCF  
  
1.  Fare clic su di **diagnostica** nodo ed espanderlo.  
  
2.  Fare doppio clic su di **listener** nodo e selezionare **nuovo Listener**.  
  
3.  Digitare il nome del file di traccia nel **InitData** campo. È possibile fare clic sul pulsante "…" per selezionare un percorso.  
  
4.  Fare clic su di **TypeName** riga viene visualizzato un pulsante "…". Fare clic su questo pulsante per aprire la **Browser dei tipi di Listener di traccia**, che è possibile utilizzare per individuare i listener di traccia preconfigurati già installati.  
  
5.  Si noti il **origine** sezione. Fare clic su **Aggiungi** in questa sezione per aprire una finestra di dialogo contenente un menu a discesa, in cui sono elencate origini di traccia disponibili. Selezionare un'origine di traccia e fare clic su **OK**.  
  
6.  Per modificare le impostazioni di registrazione dei messaggi, fare clic su di **registrazione messaggi** nodo. Le impostazioni possono essere modificate nella griglia delle proprietà.  
  
### <a name="advanced"></a>Avanzate  
  
#### <a name="behaviors"></a>comportamenti  
 Il **comportamenti** nodo vengono visualizzati i comportamenti attualmente definiti nel file di configurazione.  
  
 Le configurazioni dei comportamenti consentono di impostare i comportamenti di endpoint e servizi. Tali impostazioni di configurazione vengono archiviate nel **avanzate** nodo **i comportamenti del servizio** e **i comportamenti dell'Endpoint**. I comportamenti del servizio sono utilizzati dai servizi, mentre i comportamenti degli endpoint sono utilizzati dagli endpoint.  
  
 I comportamenti sono una raccolta di elementi di estensione organizzati in uno stack. L'elemento all'inizio dello stack viene applicato per primo. Ogni elemento di estensione può essere configurato in modo specifico.  
  
##### <a name="creating-a-new-behavior-configuration"></a>Creazione di una nuova configurazione di un comportamento  
 Per creare una nuova configurazione di un comportamento, è possibile procedere nei due modi seguenti:  
  
-   Fare doppio clic su uno dei nodi dei comportamenti e selezionare "**nuova configurazione del comportamento...**  
  
-   Selezionare uno dei nodi dei comportamenti e fare clic su di **nuova configurazione del comportamento**... nel **riquadro** in basso a sinistra della finestra.  
  
##### <a name="adding-behavior-element-extensions-to-a-behavior"></a>Aggiunta di estensioni degli elementi del comportamento a un comportamento  
  
1.  selezionare uno dei nodi dei comportamenti.  
  
2.  Selezionare il comportamento che si desidera modificare.  
  
3.  Fare clic su **Aggiungi**.  
  
4.  Nell'elenco di estensioni disponibili, selezionare l'estensione degli elementi del comportamento che si desidera aggiungere.  
  
5.  Fare clic su **Aggiungi**.  
  
##### <a name="adjusting-the-extension-position-in-a-behavior"></a>Impostazione della posizione dell'estensione in un Comportamento  
 I comportamenti sono raccolte di elementi organizzati in uno stack. Ogni elemento dello stack può essere configurato in modo specifico. L'ordine delle estensioni degli elementi di comportamento in un comportamento indica la posizione occupata da ogni estensione nello stack. Gli elementi all'inizio dello stack vengono applicati per primi. Per modificare l'ordine:  
  
1.  selezionare uno dei nodi dei comportamenti.  
  
2.  Selezionare il comportamento che si desidera modificare.  
  
3.  Selezionare un elemento di estensione di comportamento nella **posizione dell'estensione di elemento di comportamento** sezione.  
  
4.  Utilizzare il **backup** o **verso il basso** pulsante sul lato sinistro dell'elenco per modificare la posizione dell'elemento selezionato.  
  
##### <a name="editing-the-configuration-of-behavior-element-extensions"></a>Modifica della configurazione delle estensioni degli elementi del comportamento  
  
1.  Selezionare uno dei nodi dei comportamenti nell'albero.  
  
2.  Selezionare il comportamento contenente l'elemento che si desidera modificare.  
  
3.  Selezionare l'estensione dell'elemento del comportamento che si desidera modificare. Le impostazioni dell'elemento sono visualizzate nel riquadro a destra, in cui è inoltre possibile modificarle.  
  
#### <a name="protocolmapping"></a>ProtocolMapping  
 Contenuto della sezione è possibile impostare i tipi di associazione predefiniti per i vari protocolli, quali http, tcp, MSMQ e net.pipe, tramite il mapping definito tra gli schemi di indirizzi dei protocolli e le possibili associazioni. È inoltre possibile aggiungere nuovi mapping ad altri protocolli.  
  
#### <a name="extensions"></a>Estensioni  
 Nuove estensioni di associazione, le estensioni degli elementi di associazione, le estensioni degli endpoint standard e le estensioni di comportamento possono essere registrate per l'uso nella configurazione WCF. Ogni estensione è costituita da una coppia nome/tipo. Il primo elemento della coppia definisce il nome dell'estensione nella configurazione, mentre il secondo implementa l'estensione. Esistono quattro tipi di estensione:  
  
-   Le estensioni di associazione definiscono un intero tipo di associazione. Esempio: `basicHttpBinding`.  
  
-   Le estensioni degli elementi di associazione definiscono un elemento di un'associazione. Esempio: `textMessageEncoding`.  
  
-   Le estensioni degli endpoint standard definiscono un endpoint standard intero. Esempio: `discoveryEndpoint`.  
  
-   Le estensioni degli elementi di un comportamento definiscono un elemento di un comportamento. Esempio: `clientVia`.  
  
 Le estensioni registrate nella configurazione possono essere utilizzate come qualsiasi altro componente WCF dello stesso tipo.  
  
##### <a name="adding-a-new-extension"></a>Aggiunta di una nuova estensione  
 Selezionare uno dei nodi delle estensioni nei nodi avanzati:  
  
1.  Fare clic su **Nuovo**.  
  
2.  Immettere un nome e un tipo.  
  
3.  Fare clic su **OK**.  
  
4.  L'estensione verrà quindi visualizzata nella sezione appropriata dell'editor. Se ad esempio si aggiunge un'estensione di un elemento di un comportamento, questa verrà visualizzata nell'elenco delle estensioni disponibili.  
  
#### <a name="hosting-environment"></a>Ambiente host  
 Questa sezione consente di definire le impostazioni di creazione delle istanze per l'ambiente host del servizio.  
  
### <a name="creating-a-configuration-file-using-the-wizard"></a>Creazione di un File di configurazione utilizzando la procedura guidata  
 Un modo per creare un nuovo file di configurazione è tramite la Creazione guidata nuovo elemento del servizio. La procedura guidata consente di trovare i tipi di servizio installato e altri elementi compatibili con WCF nel computer, inclusi COM+ e le directory virtuali ospitate sul Web e li carica per semplificare la configurazione notevolmente la creazione.  
  
#### <a name="creating-a-configuration-file"></a>Creazione di un file di configurazione  
  
1.  Avviare l'Editor configurazione servizi utilizzando una finestra di comando per passare al percorso di installazione di WCF e quindi digitare `SvcConfigEditor.exe`.  
  
2.  Dal **File** dal menu **aprire** e fare clic su **eseguibile**, **COM+ Service**, o **WebHosted Service**, a seconda del tipo di file di configurazione che si desidera creare.  
  
3.  Nel **aprire** finestra di dialogo casella, passare al file specifico che si desidera creare un file di configurazione e fare doppio clic.  
  
4.  Nel **File** dal menu **Aggiungi nuovo elemento** e fare clic su **servizio**. Verrà avviata la Creazione guidata nuovo elemento del servizio.  
  
5.  Attenersi alle istruzioni fornite nella procedura guidata per creare il nuovo servizio.  
  
> [!NOTE]
>  Se si desidera utilizzare NetPeerTcpBinding dal file di configurazione creato tramite la Procedura guidata, si deve aggiungere manualmente un elemento di configurazione dell’associazione e modificare l'attributo `mode` dell’elemento `security` in “None”.  
  
## <a name="configuring-com"></a>Configurazione di COM+  
 L'Editor di configurazione dei servizi consente di creare un nuovo file di configurazione per un'applicazione COM+ esistente o di modificare una configurazione COM+ esistente. Il **contratto COM** nodo è visibile solo quando il <`comContract`> sezione esiste nel file di configurazione.  
  
### <a name="creating-a-new-com-configuration"></a>Creazione di una nuova configurazione COM+  
 Prima di creare una nuova configurazione COM+, verificare che l'applicazione COM+ sia stata installata in Servizi componenti e registrata nella Global Assembly Cache (GAC).  
  
1.  Selezionare **File** -> menu **integrazione** -> **l'applicazione COM+.** Questa operazione determina la chiusura del file attualmente aperto. Se il file corrente contiene dati non salvati, verrà visualizzata la finestra di dialogo Salva. Il **integrazione guidata COM+** viene quindi avviata.  
  
2.  Nella prima pagina selezionare l'applicazione COM+ nell'albero. Se risulta impossibile individuare l'applicazione COM+ nell'albero, verificare che sia stata installata in Servizi componenti e registrata nella Global Assembly Cache (GAC).  
  
3.  Nella pagina successiva, selezionare i metodi che si desidera esporre come servizi WCF. Tutti i metodi supportati dell'applicazione COM+ sono visualizzati e selezionati per impostazione predefinita.  
  
4.  Scegliere un metodo di hosting.  
  
5.  Configurare le altre impostazioni secondo le istruzioni della procedura guidata.  
  
6.  L'Editor di configurazione dei servizi utilizza in background ComSvcConfig.exe per generare un file di configurazione. Al termine di questa operazione sarà possibile esaminare un riepilogo e quindi uscire dalla procedura guidata. Verrà automaticamente aperto il file di configurazione in modo da consentirne la modifica diretta.  
  
### <a name="editing-an-existing-com-configuration"></a>Modifica di una configurazione COM+ esistente  
  
1.  Selezionare **File** -> menu **aprire** -> **COM+ Service**...  
  
2.  Selezionare nell'elenco il servizio COM+ che si desidera modificare.  
  
3.  Modificare le impostazioni di configurazione di **contratti COM** nodo.  
  
    > [!NOTE]
    >  È inoltre possibile aprire e modificare direttamente un file di configurazione contenente contratti COM.  
  
## <a name="security"></a>Sicurezza  
 Un file di configurazione del servizio generato dall'Editor di configurazione non è necessariamente protetto. Consultare il [sicurezza](../../../docs/framework/wcf/feature-details/security.md) documentazione per informazioni su come proteggere i servizi WCF.  
  
 L’Editor di Configurazione, inoltre, può essere utilizzato solo per leggere e scrivere elementi di configurazione WCF validi. Lo strumento ignora elementi conformi allo schema, definiti dall'utente. L’Editor di Configurazione, inoltre, non tenta di rimuovere questi elementi dal file di configurazione o di determinarne gli effetti sugli elementi WCF conosciuti. L’utente è tenuto a determinare se questi elementi possono costituire una minaccia per l'applicazione o il sistema.
