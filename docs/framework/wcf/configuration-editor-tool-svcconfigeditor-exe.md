---
title: Strumento Editor di configurazione (SvcConfigEditor.exe)
description: Informazioni su come gestire le impostazioni per associazioni, comportamenti, servizi e diagnostica WCF mediante l'editor di configurazione dei servizi WCF.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 258437ff616b969d40feabbfff364ad2cc6b25bc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247649"
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
> L'editor non può cancellare un elemento di configurazione dal file di configurazione una volta che l’elemento è stato modificato. Ad esempio, se si utilizza l'editor per impostare il nome dell'endpoint su una stringa non vuota e per salvarlo, il file di configurazione avrà il contenuto mostrato nell'esempio seguente:
>
> `<endpoint binding="basicHttpBinding" name="somename" />`
>
> Se si tenta di rimuovere il nome impostandolo su una stringa vuota e salvando il file, il file di configurazione contiene ancora l'attributo `name`, come mostrato nell'esempio seguente.
>
> `<endpoint binding="basicHttpBinding" name="" />`
>
> Per cancellare l'attributo si deve modificare manualmente l'elemento utilizzando un altro editor di testo.
>
> È necessario prestare particolare attenzione a questo problema quando si utilizza l'elemento `issueToken` del comportamento dell’endpoint `clientCredential`. In particolare, l'attributo `address` del sottoelemento `localIssuer` non deve essere una stringa vuota. Se si è modificato l'attributo `address` utilizzando l'Editor di configurazione e si desidera rimuoverlo completamente, è necessario utilizzare uno strumento diverso dall'Editor. In caso contrario, l'attributo conterrà una stringa vuota e l'applicazione genererà un'eccezione.

## <a name="using-the-configuration-editor"></a>Utilizzo dell’Editor di configurazione

L'Editor di configurazione dei servizi si trova nel seguente percorso di installazione di Windows SDK:

C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe

Dopo aver avviato l'editor di configurazione dei servizi, è possibile utilizzare il menu **file/Apri** per cercare il servizio o l'assembly che si desidera gestire. È possibile aprire direttamente file di configurazione, cercare i servizi WCF /COM+ e aprire i file di configurazione per i servizi ospitati su Web.

L'interfaccia utente dell'Editor di configurazione dei servizi è suddivisa nelle aree seguenti:

- Il riquadro di visualizzazione albero, in cui gli elementi di configurazione sono visualizzati in una struttura ad albero a sinistra. Per eseguire operazioni sulla struttura è possibile fare clic con il pulsante destro del mouse sui nodi.

- Il riquadro attività, in cui le attività comuni degli elementi correnti sono visualizzate nell'angolo inferiore sinistro della finestra.

- Il riquadro dettagli, in cui vengono visualizzate le impostazioni dettagliate del nodo di configurazione selezionato nella visualizzazione albero a destra.

### <a name="opening-a-configuration-file"></a>Apertura di un file di configurazione

1. Avviare l'editor di configurazione dei servizi utilizzando una finestra di comando per passare al percorso di installazione di WCF e quindi digitare `SvcConfigEditor.exe` .

2. Scegliere **Apri** dal menu **file** e quindi fare clic sul tipo di file che si desidera gestire.

3. Nella finestra di dialogo **Apri** passare al file specifico che si desidera gestire e fare doppio clic su di esso.

Il visualizzatore segue automaticamente il percorso del merge delle configurazioni e crea una visualizzazione della configurazione unita. La configurazione effettiva di un servizio non ospitato, ad esempio, è costituita da una combinazione di Machine.config e App.config. Tutte le modifiche vengono applicate al file attivo in SvcConfigEditor. Se si desidera modificare un file specifico all'interno del percorso di merge delle configurazioni, è necessario aprirlo direttamente.

> [!NOTE]
> L'Editor di configurazione ricarica il file di configurazione attualmente aperto quando quest’ultimo è stato modificato fuori dell'Editor. Quando si verifica questa condizione, tutte le modifiche che non sono state salvate in modo durevole nell'Editor verranno perse. Se il nuovo caricamento si verifica costantemente, la causa più probabile è un servizio che accede continuamente al file di configurazione, ad esempio un software antivirus in esecuzione in background. Per risolvere questo problema, assicurarsi che l'Editor di configurazione sia l’unico processo solo che può accedere al file quando è aperto.

### <a name="services"></a>Servizi

Il nodo **Servizi** Visualizza tutti i servizi attualmente assegnati nel file di configurazione. Ogni sottonodo dell'albero corrisponde a un sottoelemento della <`services`> elemento nel file di configurazione.

Quando si fa clic sul nodo **Servizi** , è possibile visualizzare o eseguire attività nella pagina di riepilogo del servizio nel riquadro dei **Dettagli** .

#### <a name="creating-a-new-service-configuration"></a>Creazione di una nuova configurazione di un servizio

Per creare una nuova configurazione di un servizio, è possibile procedere nei modi seguenti:

- Utilizzo di una procedura guidata: fare clic sul collegamento **Crea un nuovo servizio...** nel riquadro attività o nella pagina di riepilogo per avviare la procedura guidata. Questa operazione può essere eseguita anche nel menu **File** > **Aggiungi nuovo elemento**.

- Creazione manuale: è possibile fare clic con il pulsante destro del mouse sul nodo **Servizi** e scegliere **nuovo servizio**.

#### <a name="creating-a-new-service-endpoint-configuration"></a>Creazione di una nuova configurazione di endpoint di servizio

Per creare una nuova configurazione di endpoint di servizio, è possibile procedere nei modi seguenti:

- Creazione tramite una procedura guidata: fare clic sul collegamento **Crea un nuovo endpoint del servizio...** nel riquadro attività o nella pagina di riepilogo per avviare la procedura guidata. Questa operazione può essere eseguita anche nel menu **File** > **Aggiungi nuovo elemento**.

- Creazione manuale: dopo aver creato un servizio, è possibile fare clic con il pulsante destro del mouse sul nodo **endpoint** e scegliere "**nuovo endpoint servizio**".

#### <a name="editing-a-service-configuration"></a>Modifica della configurazione di un servizio

1. Fare clic su un nodo del **servizio** .

2. Modificare le impostazioni nelle griglie delle proprietà.

#### <a name="editing-a-service-endpoint-configuration"></a>Modifica della configurazione di un endpoint di servizio

1. Fare clic su un nodo **endpoint di servizio** .

2. Modificare le impostazioni nelle griglie delle proprietà.

#### <a name="adding-a-base-address"></a>Aggiunta di un indirizzo di base

1. Fare clic sul nodo **host** .

2. Fare clic sul pulsante **Nuovo** nella sezione **indirizzi di base** .

3. Immettere l'indirizzo URI di base nella finestra di dialogo.

4. Fare clic su **OK**.

> [!NOTE]
> Non è possibile modificare il valore di [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) all'interno di questo strumento. Per aggiungere o modificare questo elemento è necessario utilizzare un editor di testo o Visual Studio.

### <a name="client"></a>Client

Il nodo **client** Visualizza tutti gli endpoint client nel file di configurazione. Ogni sottonodo dell'albero corrisponde a un sottoelemento dell'<`client`> elemento nel file di configurazione.

Quando si fa clic sul nodo **client** , è possibile visualizzare o eseguire attività nella **pagina Riepilogo** client nel **riquadro dettagli**.

#### <a name="creating-a-new-client-endpoint-configuration"></a>Creazione di una nuova configurazione di endpoint client

Per creare una nuova configurazione di endpoint client, è possibile procedere nei modi seguenti:

- Creazione tramite procedura guidata: fare clic sul collegamento **Crea un nuovo client...** nel **riquadro attività** nella parte inferiore sinistra della finestra o nella **pagina di riepilogo** per avviare la procedura guidata. Questa operazione può essere eseguita anche nel menu **File** > **Aggiungi nuovo elemento**. Verrà richiesto di individuare la posizione della configurazione del servizio, da cui viene generata la configurazione client. A questo punto è possibile specificare l'endpoint del servizio a cui connettersi.

- Creazione manuale: fare clic con il pulsante destro del mouse sul nodo **endpoint** in **client**e scegliere **nuovo endpoint client**.

#### <a name="editing-a-client-endpoint-configuration"></a>Modifica di una configurazione di endpoint client

1. Fare clic su un nodo **endpoint client** .

2. Modificare le impostazioni nelle griglie delle proprietà.

### <a name="standard-endpoint"></a>Endpoint standard

Gli endpoint standard sono endpoint specializzati in cui uno o più aspetti dell'indirizzo, del contratto e dell'associazione sono impostati sui valori predefiniti.

Tali impostazioni di configurazione vengono archiviate nel nodo **endpoint standard** . Il nodo **endpoint standard** Visualizza tutte le impostazioni dell'endpoint standard nel file di configurazione. Ogni sottonodo dell'albero corrisponde a un sottoelemento dell' `<standardEndpoints>` elemento nel file di configurazione.

Quando si fa clic sul nodo **endpoint standard** , è possibile visualizzare o eseguire attività nella **pagina Riepilogo** endpoint standard nel **riquadro dettagli**.

#### <a name="creating-a-new-standard-endpoint-configuration"></a>Creazione di una nuova configurazione di endpoint standard

Per creare una nuova configurazione di endpoint standard, è possibile procedere nei modi seguenti:

- Fare clic con il pulsante destro del mouse sul nodo **endpoint standard** e selezionare **nuova configurazione endpoint standard...** Selezionare il tipo di binding nella finestra di dialogo e fare clic su **OK**.

- Selezionare il nodo **endpoint standard** e fare clic su **nuova configurazione endpoint standard...** nel **riquadro attività** in basso a sinistra della finestra.

Viene visualizzata la finestra di dialogo **creazione di un nuovo endpoint standard** in cui sono elencati tutti i tipi di endpoint standard registrati.

#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a>Visualizzazione e modifica di una configurazione di endpoint standard

Per aprire una configurazione di endpoint standard per la visualizzazione e la modifica, è possibile procedere nei modi seguenti:

- Fare clic per espandere il nodo **endpoint standard** e fare clic sul rispettivo sottonodo endpoint.

- Fare clic sul nodo **endpoint standard** e fare clic sul rispettivo endpoint nel riquadro dei dettagli.

Gli attributi dell'endpoint vengono visualizzati nel riquadro di destra per la modifica.

#### <a name="deleting-a-standard-endpoint-configuration"></a>Eliminazione di una configurazione di endpoint standard

Per eliminare una configurazione di endpoint standard, è possibile procedere nei modi seguenti:

- Fare clic per espandere il nodo **endpoint standard** e fare clic con il pulsante destro del mouse sul rispettivo sottonodo dell'endpoint. Usare il comando Context **Elimina configurazione endpoint standard** per eliminare l'endpoint.

- Fare clic sul nodo **endpoint standard** . Nel riquadro **attività** fare clic su **Elimina configurazione endpoint standard**.

Se si utilizza l'endpoint standard, viene visualizzato un messaggio di avviso quando si tenta di eliminarlo: **l'endpoint standard è in uso. Se lo si elimina ora, assicurarsi di eliminare tutti i relativi riferimenti in altre parti della configurazione, ad esempio nell'endpoint del servizio o nel client. In caso contrario, la configurazione non sarà valida e non potrà essere aperta la volta successiva. Eliminare l'endpoint standard? "**

### <a name="binding"></a>Binding

Le configurazioni di associazione consentono di configurare le associazioni sugli endpoint. Tali impostazioni di configurazione vengono archiviate nel nodo di **associazione** . Gli endpoint fanno riferimento alle configurazioni di associazione in base al nome. Inoltre, più endpoint possono fare riferimento a una stessa configurazione di associazione.

Nel nodo **associazioni** vengono visualizzate tutte le impostazioni di associazione nel file di configurazione. Ogni sottonodo dell'albero corrisponde a un sottoelemento nel <`bindings`> elemento nel file di configurazione.

Quando si fa clic sul nodo **Binding** , è possibile visualizzare o eseguire attività nella **pagina Riepilogo** binding nel **riquadro dettagli**.

#### <a name="creating-a-new-binding-configuration"></a>Creazione di una nuova configurazione di associazione

Per creare una nuova configurazione dell’associazione, è possibile procedere nei modi seguenti.

- Fare clic con il pulsante destro del mouse sul nodo **associazioni** e scegliere **nuova configurazione binding**... Selezionare il tipo di binding nella finestra di dialogo e fare clic su **OK**.

- Selezionare il nodo **Binding** e fare clic su **nuova configurazione binding**... nel **riquadro attività** in basso a sinistra della finestra.

- Nella pagina Riepilogo servizio o client fare clic su **fare clic per creare** nel campo **configurazione binding** per creare una configurazione di binding per l'endpoint corrispondente.

#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a>Aggiunta di estensioni degli elementi di associazione a un'associazione personalizzata

1. Selezionare l'associazione a cui si desidera aggiungere un elemento di estensione.

2. Scegliere **Aggiungi**.

3. Nell'elenco di estensioni disponibili, selezionare l'estensione degli elementi di associazione che si desidera aggiungere. Per selezionare più elementi, premere contemporaneamente CTRL.

4. Scegliere **Aggiungi**.

#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a>Impostazione della posizione dell'estensione in un'associazione personalizzata

Un'associazione personalizzata è una raccolta di elementi di associazione organizzati in uno stack. Ogni elemento di associazione dello stack può essere configurato in modo specifico. L'ordine delle estensioni degli elementi di associazione in un'associazione personalizzata indica la posizione occupata da ogni estensione nello stack. Gli elementi all'inizio dello stack vengono applicati per primi. Per modificare l'ordine:

1. Selezionare il nodo dell'associazione personalizzata.

2. Selezionare un elemento di estensione di binding nella sezione **posizione dell'estensione dell'elemento di binding** .

3. Utilizzare il pulsante **su o** **giù** sul lato sinistro dell'elenco per modificare la posizione dell'elemento selezionato.

#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a>Modifica della configurazione di estensioni degli elementi di associazione in un'associazione personalizzata

1. Selezionare il nodo dell'associazione nell'albero.

2. Selezionare l'associazione personalizzata contenente l'elemento che si desidera modificare.

3. Selezionare l'estensione degli elementi di associazione che si desidera modificare. Le impostazioni dell'elemento verranno visualizzate nel riquadro di destra, in cui è inoltre possibile modificarle.

### <a name="diagnostics"></a>Diagnostica

Nel nodo **diagnostica** vengono visualizzate tutte le impostazioni di diagnostica nel file di configurazione. Consente di attivare o disattivare i contatori delle prestazioni, abilitare o disabilitare Strumentazione gestione Windows (WMI), configurare la traccia WCF e configurare la registrazione dei messaggi WCF. Le impostazioni nel nodo **diagnostica** corrispondono alla `system.diagnostics` sezione <> e alla `<diagnostics>` sezione nel `<system.serviceModel>` file di configurazione.

Quando si fa clic sul nodo **diagnostica** , è possibile visualizzare o eseguire attività nella **pagina Riepilogo** diagnostica nel **riquadro dettagli**.

#### <a name="configuring-performance-counters-and-wmi"></a>Configurazione dei contatori delle prestazioni e di WMI

1. Fare clic sul nodo **diagnostica** .

2. Fare clic su Visualizza **/Nascondi contatori delle prestazioni**. Il contatore delle prestazioni prevede tre stati: Disattivo (predefinito), Solo servizio e Tutto. Il collegamento consente di attivare/disattivare l'impostazione degli stati.

#### <a name="configuring-wmi-provider"></a>Configurazione del provider WMI

1. Fare clic sul nodo **diagnostica** .

2. Per abilitare il provider WMI, fare clic sul collegamento **Abilita provider WMI** .

#### <a name="enabling-wcf-tracing"></a>Abilitazione della traccia WCF

È possibile creare un file di traccia WCF con le proprietà standard oppure configurare un file di log personalizzato.

1. Fare clic sul nodo **diagnostica** .

2. Fare clic su **Abilita traccia**.

3. Fare clic sul collegamento **livello traccia** per modificare il livello di traccia. Esistono sei livelli di traccia: Disattivo, Critico, Errore, Avviso, Informazioni e Dettagliato. L'opzione **traccia attività** e **propaga attività** consente di utilizzare la funzionalità di traccia attività WCF.

4. Fare clic sul nome del listener di traccia per specificare il file e le opzioni di traccia.

#### <a name="enabling-wcf-logging"></a>Abilitazione della registrazione WCF

È possibile creare un file di traccia WCF con le proprietà standard oppure configurare un file di log personalizzato.

1. Fare clic sul nodo **diagnostica** .

2. Fare clic su **Abilita registrazione messaggi**.

3. Fare clic sul collegamento **livello log** per modificare il livello di registrazione. Esistono tre livelli di log: Messaggi in formato non valido, Messaggi servizio e Messaggi trasporto.

4. Fare clic sul nome del listener per specificare le opzioni e il file di log.

> [!NOTE]
> Se si desidera che i log di traccia e di messaggi vengano scaricati automaticamente quando l'applicazione viene chiusa, abilitare l'opzione di **scaricamento automatico** .

Nella **Diagnostics** **pagina Riepilogo** diagnostica è possibile eseguire le attività più comuni per la configurazione della diagnostica. Tuttavia, se si desidera modificare manualmente le impostazioni dei listener e delle origini, è necessario espandere il nodo **diagnostica** e modificare le impostazioni nel nodo **registrazione messaggi**, **listener** e **origini** .

#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a>Abilitazione della traccia o della registrazione dei messaggi personalizzata di WCF

1. Fare clic sul nodo **diagnostica** ed espanderlo.

2. Fare clic con il pulsante destro del mouse sul nodo **listener** e scegliere **nuovo listener**.

3. Digitare il nome del file di traccia nel campo **initdata** . È possibile fare clic su "..." pulsante per passare a un percorso.

4. Facendo clic sulla riga **typeName** viene visualizzato un "..." pulsante. Fare clic su questo pulsante per aprire il **browser dei tipi di listener di traccia**, che è possibile utilizzare per trovare i listener di traccia preconfigurati già installati.

5. Si noti la sezione **source** . Fare clic su **Aggiungi** in questa sezione per aprire una finestra di dialogo con un menu a discesa in cui sono elencate le origini di traccia disponibili. Selezionare un'origine di traccia e fare clic su **OK**.

6. Per modificare le impostazioni di registrazione dei messaggi, fare clic sul nodo **registrazione messaggi** . Le impostazioni possono essere modificate nella griglia delle proprietà.

### <a name="advanced"></a>Avanzate

#### <a name="behaviors"></a>Comportamenti

Nel nodo **comportamenti** vengono visualizzati i comportamenti attualmente definiti nel file di configurazione.

Le configurazioni dei comportamenti consentono di impostare i comportamenti di endpoint e servizi. Tali impostazioni di configurazione vengono archiviate nel nodo **avanzato** in **comportamenti del servizio** e **comportamenti dell'endpoint**. I comportamenti del servizio sono utilizzati dai servizi, mentre i comportamenti degli endpoint sono utilizzati dagli endpoint.

I comportamenti sono una raccolta di elementi di estensione organizzati in uno stack. L'elemento all'inizio dello stack viene applicato per primo. Ogni elemento di estensione può essere configurato in modo specifico.

##### <a name="creating-a-new-behavior-configuration"></a>Creazione di una nuova configurazione di un comportamento

Per creare una nuova configurazione di un comportamento, è possibile procedere nei due modi seguenti:

- Fare clic con il pulsante destro del mouse su uno dei nodi del comportamento e selezionare "**nuova configurazione del comportamento...**

- Selezionare uno dei nodi del comportamento e fare clic sulla **nuova configurazione del comportamento**... nel **riquadro attività** in basso a sinistra della finestra.

##### <a name="adding-behavior-element-extensions-to-a-behavior"></a>Aggiunta di estensioni degli elementi del comportamento a un comportamento

1. selezionare uno dei nodi dei comportamenti.

2. Selezionare il comportamento che si desidera modificare.

3. Scegliere **Aggiungi**.

4. Nell'elenco di estensioni disponibili, selezionare l'estensione degli elementi del comportamento che si desidera aggiungere.

5. Scegliere **Aggiungi**.

##### <a name="adjusting-the-extension-position-in-a-behavior"></a>Impostazione della posizione dell'estensione in un Comportamento

I comportamenti sono raccolte di elementi organizzati in uno stack. Ogni elemento dello stack può essere configurato in modo specifico. L'ordine delle estensioni degli elementi di comportamento in un comportamento indica la posizione occupata da ogni estensione nello stack. Gli elementi all'inizio dello stack vengono applicati per primi. Per modificare l'ordine:

1. selezionare uno dei nodi dei comportamenti.

2. Selezionare il comportamento che si desidera modificare.

3. Selezionare un elemento di estensione del comportamento nella sezione **posizione dell'estensione degli elementi di comportamento** .

4. Utilizzare il pulsante **su o** **giù** sul lato sinistro dell'elenco per modificare la posizione dell'elemento selezionato.

##### <a name="editing-the-configuration-of-behavior-element-extensions"></a>Modifica della configurazione delle estensioni degli elementi del comportamento

1. Selezionare uno dei nodi dei comportamenti nell'albero.

2. Selezionare il comportamento contenente l'elemento che si desidera modificare.

3. Selezionare l'estensione dell'elemento del comportamento che si desidera modificare. Le impostazioni dell'elemento sono visualizzate nel riquadro a destra, in cui è inoltre possibile modificarle.

#### <a name="protocolmapping"></a>ProtocolMapping

Contenuto della sezione è possibile impostare i tipi di associazione predefiniti per i vari protocolli, quali http, tcp, MSMQ e net.pipe, tramite il mapping definito tra gli schemi di indirizzi dei protocolli e le possibili associazioni. È inoltre possibile aggiungere nuovi mapping ad altri protocolli.

#### <a name="extensions"></a>Estensioni

Le nuove estensioni di binding, le estensioni degli elementi di binding, le estensioni degli endpoint standard e le estensioni di comportamento possono essere registrate per l'uso nella configurazione WCF. Ogni estensione è costituita da una coppia nome/tipo. Il primo elemento della coppia definisce il nome dell'estensione nella configurazione, mentre il secondo implementa l'estensione. Esistono quattro tipi di estensione:

- Le estensioni di associazione definiscono un intero tipo di associazione. Esempio: `basicHttpBinding`.

- Le estensioni degli elementi di associazione definiscono un elemento di un'associazione. Esempio: `textMessageEncoding`.

- Le estensioni degli endpoint standard definiscono un endpoint standard intero. Esempio: `discoveryEndpoint`.

- Le estensioni degli elementi di un comportamento definiscono un elemento di un comportamento. Esempio: `clientVia`.

 Le estensioni registrate nella configurazione possono essere utilizzate come qualsiasi altro componente WCF dello stesso tipo.

##### <a name="adding-a-new-extension"></a>Aggiunta di una nuova estensione

Selezionare uno dei nodi delle estensioni nei nodi avanzati:

1. Fare clic su **New**.

2. Immettere un nome e un tipo.

3. Fare clic su **OK**.

4. L'estensione verrà quindi visualizzata nella sezione appropriata dell'editor. Se ad esempio si aggiunge un'estensione di un elemento di un comportamento, questa verrà visualizzata nell'elenco delle estensioni disponibili.

#### <a name="hosting-environment"></a>Ambiente host

Questa sezione consente di definire le impostazioni di creazione delle istanze per l'ambiente host del servizio.

### <a name="creating-a-configuration-file-using-the-wizard"></a>Creazione di un File di configurazione utilizzando la procedura guidata

Un modo per creare un nuovo file di configurazione è tramite la Creazione guidata nuovo elemento del servizio. La procedura guidata consente di individuare i tipi di servizio e gli altri elementi compatibili con WCF nel computer, tra cui COM+ e le directory virtuali ospitate su Web, e di caricarli per semplificare la creazione della configurazione.

#### <a name="creating-a-configuration-file"></a>Creazione di un file di configurazione

1. Avviare l'editor di configurazione dei servizi utilizzando una finestra di comando per passare al percorso di installazione di WCF e quindi digitare `SvcConfigEditor.exe` .

2. Scegliere **Apri** dal menu **file** e fare clic su **eseguibile**, **servizio com+** o **Servizio WebHosted**, a seconda del tipo di file di configurazione che si desidera creare.

3. Nella finestra di dialogo **Apri** passare al file specifico per il quale si desidera creare un file di configurazione e fare doppio clic su di esso.

4. Scegliere **Aggiungi nuovo elemento** dal menu **file** e fare clic su **servizio**. Verrà avviata la Creazione guidata nuovo elemento del servizio.

5. Attenersi alle istruzioni fornite nella procedura guidata per creare il nuovo servizio.

> [!NOTE]
> Se si desidera utilizzare NetPeerTcpBinding dal file di configurazione creato tramite la Procedura guidata, si deve aggiungere manualmente un elemento di configurazione dell’associazione e modificare l'attributo `mode` dell’elemento `security` in “None”.

## <a name="configuring-com"></a>Configurazione di COM+

L'Editor di configurazione dei servizi consente di creare un nuovo file di configurazione per un'applicazione COM+ esistente o di modificare una configurazione COM+ esistente. Il nodo del **contratto com** è visibile solo quando il <`comContract`> sezione è presente nel file di configurazione.

### <a name="creating-a-new-com-configuration"></a>Creazione di una nuova configurazione COM+

Prima di creare una nuova configurazione COM+, verificare che l'applicazione COM+ sia stata installata in Servizi componenti e registrata nella Global Assembly Cache (GAC).

1. Selezionare menu **file** -> **integrare**l'  ->  **applicazione com+.** Questa operazione determina la chiusura del file attualmente aperto. Se il file corrente contiene dati non salvati, verrà visualizzata la finestra di dialogo Salva. Viene quindi avviata l' **integrazione guidata com+** .

2. Nella prima pagina, selezionare l'applicazione COM+ nell'albero. Se risulta impossibile individuare l'applicazione COM+ nell'albero, verificare che sia stata installata in Servizi componenti e registrata nella Global Assembly Cache (GAC).

3. Nella pagina successiva, selezionare i metodi che si desidera esporre come servizi WCF. Tutti i metodi supportati dell'applicazione COM+ sono visualizzati e selezionati per impostazione predefinita.

4. Scegliere un metodo di hosting.

5. Configurare le altre impostazioni secondo le istruzioni della procedura guidata.

6. L'Editor di configurazione dei servizi utilizza in background ComSvcConfig.exe per generare un file di configurazione. Al termine di questa operazione sarà possibile esaminare un riepilogo e quindi uscire dalla procedura guidata. Verrà automaticamente aperto il file di configurazione in modo da consentirne la modifica diretta.

### <a name="editing-an-existing-com-configuration"></a>Modifica di una configurazione COM+ esistente

1. Selezionare il menu **file** > **Apri**  ->  **servizio com+**...

2. Selezionare nell'elenco il servizio COM+ che si desidera modificare.

3. Modificare le impostazioni di configurazione nel nodo **contratti com** .

    > [!NOTE]
    > È inoltre possibile aprire e modificare direttamente un file di configurazione contenente contratti COM.

## <a name="security"></a>Sicurezza

Un file di configurazione del servizio generato dall'Editor di configurazione non è necessariamente protetto. Per informazioni su come proteggere i servizi WCF, vedere la documentazione relativa alla [sicurezza](./feature-details/security.md) .

L’Editor di Configurazione, inoltre, può essere utilizzato solo per leggere e scrivere elementi di configurazione WCF validi. Lo strumento ignora elementi conformi allo schema, definiti dall'utente. L’Editor di Configurazione, inoltre, non tenta di rimuovere questi elementi dal file di configurazione o di determinarne gli effetti sugli elementi WCF conosciuti. L’utente è tenuto a determinare se questi elementi possono costituire una minaccia per l'applicazione o il sistema.
