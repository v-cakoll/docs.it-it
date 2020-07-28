---
title: Mage.exe (Strumento per la generazione e la modifica di manifesti)
description: Per iniziare a usare Mage.exe, Strumento per la generazione e la modifica di manifesti. Questo strumento supporta la creazione e la modifica dei manifesti dell'applicazione e della distribuzione.
ms.date: 12/06/2018
helpviewer_keywords:
- Manifest Generation and Editing tool
- Mage.exe
ms.assetid: 77dfe576-2962-407e-af13-82255df725a1
ms.openlocfilehash: 864d3d7bd7cf32b5c2a5ce83819f4e78cd8ce043
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164261"
---
# <a name="mageexe-manifest-generation-and-editing-tool"></a>Mage.exe (Strumento per la generazione e la modifica di manifesti)

Lo Strumento per la generazione e la modifica di manifesti (*Mage.exe*) è uno strumento da riga di comando che supporta la creazione e la modifica dei manifesti delle applicazioni e delle distribuzioni. Come strumento della riga di comando, *Mage.exe* può essere eseguito da script batch e altre applicazioni basate su Windows, incluse le applicazioni ASP.NET.

È inoltre possibile utilizzare *MageUI.exe*, un'applicazione grafica, anziché *Mage.exe*. Per altre informazioni, vedere [MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).

Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio. Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).

Due versioni di *Mage.exe* e *MageUI.exe* sono incluse con Visual Studio. Per visualizzare le informazioni sulla versione, eseguire *MageUI.exe*, scegliere **?** e quindi **Informazioni su**. In questa documentazione viene descritta la versione 4.0. x. x di *Mage.exe* e *MageUI.exe*.

## <a name="syntax"></a>Sintassi

```console
Mage [commands] [commandOptions]
```

## <a name="parameters"></a>Parametri

Nella tabella seguente sono illustrati i comandi supportati da *Mage.exe*. Per altre informazioni sulle opzioni supportate da questi comandi, vedere [Opzioni dei comandi New e Update](#new-and-update-command-options) e [Opzioni del comando Sign](#sign-command-options).

|Comando|Descrizione|
|-------------|-----------------|
|**-cc, ClearApplicationCache**|Cancella il contenuto della cache di download di tutte le applicazioni solo online.|
|**-n, -New** *fileType [newOptions]*|Crea un nuovo file del tipo specificato. I tipi validi sono:<br /><br /> -   `Deployment`: crea un nuovo manifesto di distribuzione.<br />-   `Application`: crea un nuovo manifesto di applicazione.<br /><br /> Se non si specificano parametri aggiuntivi con questo comando, verrà creato automaticamente un file del tipo appropriato, con gli adeguati tag e valori di attributo predefiniti.<br /><br /> Usare l'opzione **-ToFile** (vedere la tabella seguente) per specificare il nome e il percorso del nuovo file.<br /><br /> Usare l'opzione **-FromDirectory** (vedere la tabella seguente) per creare un manifesto dell'applicazione con tutti gli assembly per un'applicazione aggiunti alla \<dependency> sezione del manifesto.|
|**-u, -Update** *[filePath] [updateOptions]*|Esegue una o più modifiche in un file manifesto. Non è necessario specificare il tipo di file che si sta modificando. Mage.exe esaminerà il file utilizzando un set di regole euristiche per determinare se si tratta di un manifesto di distribuzione o di un manifesto di applicazione.<br /><br /> Se un file è già stato firmato con un certificato, **-Update** rimuoverà il blocco della firma con chiave. Questo è necessario perché la firma con chiave contiene un hash del file e la modifica di quest'ultimo rende l'hash non valido.<br /><br /> Usare l'opzione **-ToFile** (vedere la tabella seguente) per specificare un nuovo nome e percorso del file anziché sovrascrivere il file esistente.|
|**-s, -Sign** `[signOptions]`|Utilizza una coppia di chiavi o il certificato X509 per firmare un file. Le firme vengono inserite nei file come elementi XML.<br /><br /> È necessario essere connessi a Internet quando si firma un manifesto che specifica un valore **-TimestampUri** .|
|**-ver, -Verify** *[nomefile-manifesto]*|Verifica che il manifesto sia firmato correttamente. Non può essere combinato con altri comandi. <br/><br/>**Disponibile in .NET Framework 4.7 e versioni successive.**|
|**-h, -?, -Help** *[verbose]*|Descrive tutti i comandi disponibili e le rispettive opzioni. Specificare `verbose` per ottenere informazioni dettagliate.|

## <a name="new-and-update-command-options"></a>Opzioni dei comandi New e Update

La tabella seguente illustra le opzioni supportate dai comandi `-New` e `-Update`:

|Opzioni|Valore predefinito|Si applica a|Descrizione|
|-------------|-------------------|----------------|-----------------|
|**-a, -Algorithm**|sha1RSA|Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|Specifica l'algoritmo con cui generare i digest di dipendenza. Il valore deve essere "sha256RSA" o "sha1RSA".<br /><br /> Utilizzare con l'opzione "-Update". Questa opzione viene ignorata quando si utilizza l'opzione "-Sign".|
|**-appc, -AppCodeBase** `manifestReference`||Manifesti di distribuzione.|Inserisce un riferimento a un URL o a percorso di file nel file manifesto dell'applicazione. Questo valore deve corrispondere al percorso completo del manifesto dell'applicazione.|
|**-appm, -AppManifest** `manifestPath`||Manifesti di distribuzione.|Inserisce un riferimento a un manifesto dell'applicazione di distribuzione nel relativo manifesto di distribuzione.<br /><br /> Se il file indicato in `manifestPath` non esiste, *Mage.exe* genera un errore. Se il file a cui fa riferimento `manifestPath` non è un manifesto dell'applicazione, *Mage.exe* genererà un errore.|
|**-cf, -CertFile** `filePath`||Tutti i tipi di file.|Specifica il percorso di un certificato digitale X509 per la firma di un manifesto o di un file di licenza. Questa opzione può essere usata insieme all'opzione **-Password** se il certificato richiede una password per i file PFX (Personal Information Exchange). A partire da .NET Framework 4.7, se il file non contiene una chiave privata, è necessario usare una combinazione delle opzioni **-CryptoProvider** e **-KeyContainer**.<br/><br/>A partire da .NET Framework 4.6.2, *Mage.exe* firma i manifesti con certificati CNG e CAPI.|
|**-ch, -CertHash** `hashSignature`||Tutti i tipi di file.|Hash di un certificato digitale contenuto nell'archivio dei certificati personali del computer client. Corrisponde alla stringa di identificazione digitale di un certificato digitale visualizzata nella console dei certificati di Windows.<br /><br /> Il parametro`hashSignature` può essere costituito da caratteri maiuscoli o minuscoli e può essere specificato sia come stringa singola sia con gli ottetti dell'identificazione digitale separati da spazi e l'intera identificazione digitale racchiusa tra virgolette.|
|**-csp, -CryptoProvider** `provider-name`||Tutti i tipi di file.|Specifica il nome di un provider del servizio di crittografia (CSP) che include il contenitore di chiavi private. È necessaria l'opzione **-KeyContainer**.<br/><br/>Questa opzione è disponibile a partire da .NET Framework 4.7.|
|**-fd, -FromDirectory** `directoryPath`||Manifesti di applicazione.|Inserisce nel manifesto dell'applicazione le descrizioni di tutti gli assembly e i file trovati in `directoryPath`, incluse tutte le sottodirectory, dove `directoryPath` corrisponde alla directory contenente l'applicazione che si desidera distribuire. Per ogni file nella directory, *Mage.exe* decide se il file è un assembly o un file statico. Nel primo caso, verranno aggiunti un tag `<dependency>` e un attributo `installFrom` all'applicazione con il nome, la codebase e la versione dell'assembly. Nel secondo caso, verrà aggiunto un tag `<file>` . *Mage.exe* utilizzerà anche un semplice set di regole euristiche per rilevare il file eseguibile principale dell'applicazione e lo contrassegnerà come punto di ingresso dell'applicazione ClickOnce nel manifesto.<br /><br /> *Mage.exe* non contrassegna mai i file come file di dati. L'operazione deve essere eseguita manualmente. Per altre informazioni, vedere [procedura: includere un file di dati in un'applicazione ClickOnce](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application).<br /><br /> *Mage.exe* genera anche un hash per ogni file in base alla relativa dimensione. Gli hash vengono utilizzati da ClickOnce per verificare che i file di distribuzione non siano stati manomessi dopo la creazione del manifesto. Se uno dei file della distribuzione viene modificato, è possibile eseguire *Mage.exe* con il comando **-Update** e l'opzione **-FromDirectory** per aggiornare gli hash e le versioni degli assembly di tutti i file a cui viene fatto riferimento.<br /><br /> L'opzione **-FromDirectory** includerà tutti i file in tutte le sottodirectory trovate all'interno di `directoryPath`.<br /><br /> Se si usa **-FromDirectory** con il comando **-Update**, *Mage.exe* rimuove dal manifesto dell'applicazione i file che non sono più presenti nella directory.|
|**-if, -IconFile**  `filePath`||Manifesti di applicazione.|Specifica il percorso completo di un file icona (.ICO). Questa icona viene visualizzata accanto al nome dell'applicazione nel menu Start e nella voce in Installazione applicazioni. Se non viene fornita nessun'icona, viene utilizzata l'icona predefinita.|
|**-ip, -IncludeProviderURL**  `url`|true|Manifesti di distribuzione.|Indica se il manifesto di distribuzione include il valore del percorso di aggiornamento impostato da **-ProviderURL**.|
|**-i, -Install** `willInstall`|true|Manifesti di distribuzione.|Indica se installare o meno l'applicazione ClickOnce nel computer locale o se eseguirla dal Web. Se l'applicazione viene installata, nel menu **Start** di Windows verrà creato un collegamento corrispondente. I valori validi sono "true" (o "t") e "false" (o "f").<br /><br /> Se si specifica l'opzione **-MinVersion** e l'utente ha una versione precedente rispetto a **-MinVersion** , l'applicazione verrà sempre installata, indipendentemente dal valore passato a **-Install**.<br /><br /> Non è possibile usare questa opzione con l'opzione **-BrowserHosted** . Il tentativo di specificare entrambe le opzioni per lo stesso manifesto genera un errore.|
|**-kc, -KeyContainer** `name`||Tutti i tipi di file.|Specifica il contenitore di chiavi che include il nome della chiave privata. È necessaria l'opzione **CryptoProvider**.<br/><br/>Questa opzione è disponibile a partire da .NET Framework 4.7.|
|**-mv, -MinVersion**  `[version]`|Versione indicata nel manifesto di distribuzione ClickOnce, come specificata dal flag **-Version** .|Manifesti di distribuzione.|Versione minima dell'applicazione che può essere eseguita da un utente. Il flag contrassegna la versione denominata dell'applicazione come aggiornamento obbligatorio. Se si rilascia una versione del prodotto contenente un aggiornamento relativo a una modifica importante o a una correzione di un difetto critico nella sicurezza, è possibile utilizzare tale flag per specificare che l'aggiornamento è obbligatorio e che l'utente non può continuare a eseguire versioni precedenti.<br /><br /> Il parametro`version` ha la stessa semantica dell'argomento del flag **-Version** .|
|**-n,-nome**`nameString`|Distribuire|Tutti i tipi di file.|Nome utilizzato per identificare l'applicazione. Questo nome verrà utilizzato da ClickOnce per identificare l'applicazione nel menu **Start** (se l'applicazione è configurata per l'installazione) e nelle finestre di dialogo relative all'elevazione delle autorizzazioni. **Nota:**  Se si aggiorna un manifesto esistente e non si specifica il nome di un server di pubblicazione con questa opzione, *Mage.exe* aggiorna il manifesto con il nome dell'organizzazione definito nel computer. Per utilizzare un nome diverso, assicurarsi di utilizzare questa opzione e specificare il nome dell'editore desiderato.|
|**-pwd, -Password** `passwd`||Tutti i tipi di file.|Password utilizzata per firmare un manifesto con un certificato digitale. Questa opzione deve essere usata insieme a **-CertFile** .|
|**-p, Processor** `processorValue`|Msil|Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|Architettura del microprocessore sulla quale verrà eseguita la distribuzione. Questo valore è obbligatorio se si preparano installazioni con assembly precompilati per un microprocessore specifico. I valori validi includono `msil`, `x86`, `ia64`e `amd64`. `msil` sta per Microsoft Intermediate Language. Questo indica che tutti gli assembly sono indipendenti dalla piattaforma e verranno sottoposti a una compilazione JIT (just-in-time) in Common Language Runtime (CLR) alla prima esecuzione dell'applicazione.|
|**-pu,** **-ProviderURL** `url`||Manifesti di distribuzione.|Specifica l'URL che verrà esaminato da ClickOnce per verificare la disponibilità di aggiornamenti dell'applicazione.|
|**-pub, -Publisher** `publisherName`||Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|Aggiunge il nome dell'editore all'elemento di descrizione del manifesto di distribuzione o del manifesto dell'applicazione. Se usata sul manifesto di un'applicazione, l'opzione **-UseManifestForTrust** deve essere specificata anche con il valore "true" (o "t"). In caso contrario, il parametro genererà un errore.|
|**-s, -SupportURL**  `url`||Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|Specifica il collegamento visualizzato per l'applicazione ClickOnce in Installazione applicazioni.|
|**-ti, -TimestampUri** `uri`||Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|URL di un servizio di aggiunta di timestamp digitale. L'aggiunta di timestamp nei manifesti evita la necessità di firmarli nuovamente in caso di scadenza del certificato digitale prima della distribuzione della versione successiva dell'applicazione. Per altre informazioni, vedere [Windows root certificate program members](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11))(Membri del programma Windows Root Certificate).|
|**-t, -ToFile** `filePath`|-   Nuovo:<br />-   Distribuzione: deploy.application<br />-   Applicazione: application.exe.manifest<br />-   Aggiornamento:<br />-   File di input.|Tutti i tipi di file.|Specifica il percorso di output del file creato o modificato.<br /><br /> Se non si specifica **-ToFile** quando si usa **-New**, l'output viene scritto nella directory di lavoro corrente. Se non si specifica **-ToFile** quando si usa **-Update**, *Mage.exe* riscrive il file nel file di input.|
|**-tr, -TrustLevel** `level`|Basato sulla zona in cui risiede l'URL dell'applicazione.|Manifesti di applicazione.|Livello di attendibilità da concedere all'applicazione nei computer client. I valori possibili sono "Internet","Intranet" e "FullTrust".|
|**-um, -UseManifestForTrust** `willUseForTrust`|False|Manifesti di applicazione.|Specifica se la firma digitale del manifesto dell'applicazione verrà utilizzata per prendere decisioni di attendibilità quando l'applicazione è in esecuzione sul client. Se il valore è impostato su "true" (o "t"), il manifesto dell'applicazione viene utilizzato per prendere decisioni di attendibilità. Se il valore è impostato su "false" (o "f"), verrà utilizzata la firma del manifesto di distribuzione.|
|**-v,-versione**`versionNumber`|1.0.0.0|Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|Versione della distribuzione. L'argomento deve essere una stringa di versione valida nel formato "*N.N.N.N*", dove "*N*" è un Integer senza segno a 32 bit.|
|**-wpf, -WPFBrowserApp**  `isWPFApp`|false|Manifesti di applicazione.<br /><br /> Manifesti di distribuzione.|Utilizzare questo flag unicamente se si tratta di un'applicazione Windows Presentation Foundation (WPF) che verrà ospitata all'interno di Internet Explorer e non è un file eseguibile autonomo. I valori validi sono "true" (o "t") e "false" (o "f").<br /><br /> Per i manifesti di applicazione, inserisce l'attributo `hostInBrowser` nell'elemento `entryPoint` del manifesto.<br /><br /> Per i manifesti di distribuzione, imposta l'attributo `install` dell'elemento `deployment` su false e salva il manifesto di distribuzione con l'estensione .xbap. Se l'argomento è specificato insieme all'argomento **-Install** , viene generato un errore dovuto al fatto che un'applicazione ospitata dal browser non può essere un'applicazione installata offline.|

## <a name="sign-command-options"></a>Opzioni del comando Sign

Nella tabella seguente sono descritte le opzioni supportate dal comando `-Sign` , valide per tutti i tipi di file.

|Opzioni|Descrizione|
|-------------|-----------------|
|**-cf, -CertFile** `filePath`|Specifica il percorso di un certificato digitale per la firma di un manifesto. Questa opzione può essere usata insieme all'opzione **-Password** se il certificato richiede una password per i file PFX (Personal Information Exchange). A partire da .NET Framework 4.7, se il file non contiene una chiave privata, è necessario usare una combinazione delle opzioni **-CryptoProvider** e **-KeyContainer**.<br/><br/>A partire da .NET Framework 4.6.2, *Mage.exe* firma i manifesti con certificati CNG e CAPI.|
|**-ch, -CertHash** `hashSignature`|Hash di un certificato digitale contenuto nell'archivio dei certificati personali del computer client. Corrisponde alla proprietà Thumbprint di un certificato digitale visualizzata nella console dei certificati di Windows.<br /><br /> Il parametro`hashSignature` può essere costituito da caratteri maiuscoli o minuscoli e può essere specificato sia come stringa singola sia con gli ottetti dell'identificazione digitale separati da spazi e l'intera identificazione digitale racchiusa tra virgolette.|
**-csp, -CryptoProvider** `provider-name`|Specifica il nome di un provider del servizio di crittografia (CSP) che include il contenitore di chiavi private. È necessaria l'opzione **-KeyContainer**.<br/><br/>Questa opzione è disponibile a partire da .NET Framework 4.7.|
|**-kc, -KeyContainer** `name`|Specifica il contenitore di chiavi che include il nome della chiave privata. È necessaria l'opzione **CryptoProvider**.<br/><br/>Questa opzione è disponibile a partire da .NET Framework 4.7.|
|**-pwd, -Password** `passwd`|Password utilizzata per firmare un manifesto con un certificato digitale. Questa opzione deve essere usata insieme a **-CertFile** .|
|**-t, -ToFile** `filePath`|Specifica il percorso di output del file creato o modificato.|

## <a name="remarks"></a>Osservazioni

Nessun argomento di *Mage.exe* fa distinzione tra maiuscole e minuscole. I comandi e le opzioni possono essere preceduti da un trattino (-) o da una barra (/).

Tutti gli argomenti usati con il comando **-Sign** possono essere usati in qualsiasi momento anche con il comando **-New** o **-Update** . I comandi indicati di seguito sono equivalenti.

```console
mage -Sign c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx
```

> [!NOTE]
> A partire da .NET Framework versione 4.6.2 sono supportati anche i certificati CNG.

 L'applicazione della firma è l'ultima attività da eseguire su un documento perché per verificare la validità della firma viene utilizzato un hash del file. Qualsiasi modifica apportata a un file firmato comporta la necessità di firmarlo nuovamente. Se si firma un documento firmato in precedenza, *Mage.exe* sostituirà la firma precedente con quella nuova.

 Quando si usa l'opzione **-AppManifest** per popolare un manifesto di distribuzione, *Mage.exe* presuppone che il manifesto dell'applicazione si trovi nella stessa directory del manifesto di distribuzione all'interno di una sottodirectory denominata in base alla versione di distribuzione corrente e configuri il manifesto di distribuzione in modo appropriato. Se il manifesto dell'applicazione si trova in un altro percorso, usare l'opzione **-AppCodeBase** per impostare il percorso alternativo.

 Prima di distribuire l'applicazione, è necessario firmare il manifesto di distribuzione e quello dell'applicazione. Per indicazioni sulla firma dei manifesti, vedere [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview).

 L'opzione **-TrustLevel** relativa ai manifesti di applicazione definisce il set di autorizzazioni necessarie per l'esecuzione dell'applicazione sul computer client. Per impostazione predefinita, alle applicazioni viene assegnato un livello di attendibilità in base all' *area* in cui si trovano i rispettivi URL. Le applicazioni distribuite in una rete aziendale vengono in genere inserite nell'area Intranet, mentre quelle distribuite su Internet vengono inserite nell'area Internet. Entrambe le aree di sicurezza limitano l'accesso dell'applicazione alle risorse locali, ma l'area Intranet è leggermente meno restrittiva dell'area Internet. Nell'area FullTrust le applicazioni dispongono dell'accesso completo alle risorse locali di un computer. Se si usa l'opzione **-trustLevel** per inserire un'applicazione in questa area, il gestore di attendibilità di CLR chiederà all'utente di decidere se concedere questo livello di attendibilità superiore. Se si distribuisce l'applicazione in una rete aziendale, è possibile utilizzare la funzionalità di distribuzione di applicazioni attendibili per aumentare il livello di attendibilità dell'applicazione senza chiedere conferma all'utente.

 Nei manifesti di applicazioni sono supportate anche sezioni Trust personalizzate. In questo modo, viene rispettato il principio di sicurezza in base al quale devono essere richieste autorizzazioni minime, poiché è possibile configurare il manifesto in modo da richiedere solo le autorizzazioni necessarie per l'esecuzione dell'applicazione. *Mage.exe* non supporta direttamente l'aggiunta di una sezione trust personalizzata. A tale scopo, è possibile usare un editor di testo, un parser XML o lo strumento con interfaccia grafica *MageUI.exe*. Per altre informazioni sull'uso di *MageUI.exe* per aggiungere sezioni Trust personalizzate, vedere [MageUI.exe (Strumento per la generazione e la modifica di manifesti, client grafico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).

Visual Studio 2017 include la versione 4.6.1 di *Mage.exe*. I manifesti creati con questa versione di *Mage.exe* usano come destinazione .NET Framework 4. Per usare come destinazione versioni precedenti di .NET Framework, usare una versione precedente di *Mage.exe*.

In caso di aggiunta o rimozione di assembly da un manifesto esistente o di nuova firma di un manifesto esistente, *Mage.exe* non aggiorna il manifesto con .NET Framework 4 come destinazione.

Nelle tabelle seguenti vengono mostrate queste funzionalità e limitazioni:

|Versione del manifesto|Operazione|Mage v2.0|Mage v4.0|
|----------------------|---------------|---------------|---------------|
|Manifesto per applicazioni destinate alla versione 2.0 o 3.x di .NET Framework|Aperta|OK|OK|
||Chiudi|OK|OK|
||Salva|OK|OK|
||Ripetere la firma|OK|OK|
||Nuovo|OK|Non supportato|
||Aggiornare (vedere di seguito)|OK|OK|
|Manifesto per applicazioni destinate alla versione 4 di .NET Framework|Aperta|OK|OK|
||Chiudi|OK|OK|
||Salva|OK|OK|
||Ripetere la firma|OK|OK|
||Nuovo|Non supportato|OK|
||Aggiornare (vedere di seguito)|Non supportato|OK|

|Versione del manifesto|Dettagli dell'operazione di aggiornamento|Mage v2.0|Mage v4.0|
|----------------------|------------------------------|---------------|---------------|
|Manifesto per applicazioni destinate alla versione 2.0 o 3.x di .NET Framework|Modificare un assembly|OK|OK|
||Aggiungere un assembly|OK|OK|
||Rimuovere un assembly|OK|OK|
|Manifesto per applicazioni destinate alla versione 4 di .NET Framework|Modificare un assembly|Non supportato|OK|
||Aggiungere un assembly|Non supportato|OK|
||Rimuovere un assembly|Non supportato|OK|

 Mage.exe crea nuovi manifesti destinati a .NET Framework 4 Client Profile. Le applicazioni ClickOnce destinate a .NET Framework 4 Client Profile possono essere eseguite sia nel profilo client .NET Framework 4 che nella versione completa del .NET Framework 4. Se l'applicazione è destinata alla versione completa di .NET Framework 4 e non può essere eseguita nel profilo client .NET Framework 4, rimuovere l' `<framework>` elemento client usando un editor di testo e firmare nuovamente il manifesto.

Di seguito è riportato un `<framework>` elemento di esempio destinato a .NET Framework 4 Client Profile:

```xml
<framework targetVersion="4.0" profile="client" supportedRuntime="4.0.20506" />
```

## <a name="examples"></a>Esempi

Nell'esempio seguente viene visualizzata l'interfaccia utente per Mage (*MageUI.Exe*).

```console
mage
```

Negli esempi seguenti vengono creati un manifesto di distribuzione e un manifesto di applicazione predefiniti. Tutti i file vengono creati nella directory di lavoro corrente e sono denominati rispettivamente deploy.application e application.exe.manifest.

```console
mage -New Deployment
mage -New Application
```

L'esempio seguente crea un manifesto dell'applicazione in cui sono inseriti tutti gli assembly e tutti i file di risorse presenti nella directory corrente.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0
```

L'esempio seguente continua l'esempio precedente specificando il nome di distribuzione e il microprocessore di destinazione. Nell'esempio viene inoltre specificato l'URL in cui ClickOnce dovrà controllare la disponibilità di aggiornamenti.

```console
mage -New Application -FromDirectory . -Name "Hello, World! Application" -Version 1.0.0.0 -Processor "x86" -ProviderUrl http://internalserver/HelloWorld/
```

Nell'esempio seguente viene dimostrato come creare una coppia di manifesti per la distribuzione di un'applicazione WPF che verrà ospitata in Internet Explorer.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0 -WPFBrowserApp true
mage -New Deployment -AppManifest 1.0.0.0\application.manifest -WPFBrowserApp true
```

L'esempio seguente crea un manifesto dell'applicazione in cui sono inseriti tutti gli assembly e tutti i file di risorse presenti nella directory corrente e applica la firma.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0 -KeyContainer keypair.snk -CryptoProvider "Microsoft Enhanced Cryptographic Provider v1.0"
```

Nell'esempio seguente viene aggiornato un manifesto di distribuzione con le informazioni provenienti da un manifesto di applicazione e viene impostata la codebase per il percorso del manifesto dell'applicazione.

```console
mage -Update HelloWorld.deploy -AppManifest 1.0.0.0\application.manifest -AppCodeBase http://internalserver/HelloWorld.deploy
```

Nell'esempio seguente viene modificato il manifesto di distribuzione in modo da imporre un aggiornamento della versione installata dall'utente.

```console
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -MinVersion 1.1.0.0
```

Nell'esempio seguente viene indicato al manifesto di distribuzione di recuperare il manifesto dell'applicazione da un'altra directory.

```console
mage -Update HelloWorld.deploy -AppCodeBase http://anotherserver/HelloWorld/1.1.0.0/
```

Nell'esempio seguente viene firmato un manifesto di distribuzione esistente mediante un certificato digitale nella directory di lavoro corrente.

```console
mage -Sign deploy.application -CertFile cert.pfx -Password <passwd>
```

L'esempio seguente firma un manifesto di distribuzione esistente tramite un certificato digitale e una chiave privata nella directory di lavoro corrente.

```console
mage -Sign deploy.application -CertFile cert.pfx -KeyContainer keyfile.snk -CryptoProvider "Microsoft Enhanced Cryptographic Provider v1.0"
```

## <a name="see-also"></a>Vedere anche

- [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Procedura dettagliata: distribuzione manuale di un'applicazione ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)
- [Panoramica della distribuzione di applicazioni attendibili](/visualstudio/deployment/trusted-application-deployment-overview)
- [MageUI.exe (Strumento per la generazione e la modifica di manifesti, client grafico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
