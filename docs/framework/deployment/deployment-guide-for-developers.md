---
title: Guida alla distribuzione di .NET Framework per sviluppatori
description: Leggere la guida alla distribuzione di .NET per gli sviluppatori. Usare queste informazioni se si vuole installare una versione qualsiasi di .NET dalla versione 4,5 alla versione 4,8 con le app.
ms.custom: updateeachrelease
ms.date: 01/17/2020
helpviewer_keywords:
- developer's guide, deploying .NET Framework
- deployment [.NET Framework], developer's guide
ms.assetid: 094d043e-33c4-40ba-a503-e0b20b55f4cf
ms.openlocfilehash: 95c2cacc062bbe05ce0bc5c3e832bfe3006cf412
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622666"
---
# <a name="net-framework-deployment-guide-for-developers"></a>Guida alla distribuzione di .NET Framework per sviluppatori
Questo argomento offre informazioni destinate agli sviluppatori che vogliono installare qualsiasi versione di .NET Framework da .NET Framework 4.5 a [!INCLUDE[net_current](../../../includes/net-current-version.md)] con le proprie app.

È possibile scaricare i pacchetti ridistribuibili e i Language Pack per .NET Framework dalle pagine di download:

- [.NET Framework 4,8](https://dotnet.microsoft.com/download/dotnet-framework/net48)
- [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework/net472)
- [.NET Framework 4.7.1](https://dotnet.microsoft.com/download/dotnet-framework/net471)
- [.NET Framework 4,7](https://dotnet.microsoft.com/download/dotnet-framework/net47)
- [.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)
- [.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)
- [.NET framework 4.6](https://dotnet.microsoft.com/download/dotnet-framework/net46)
- [.NET Framework 4.5.2](https://dotnet.microsoft.com/download/dotnet-framework/net452)
- [.NET Framework 4.5.1](https://dotnet.microsoft.com/download/dotnet-framework/net451)
- [.NET Framework 4.5](https://dotnet.microsoft.com/download/dotnet-framework/net45)

 Note importanti:

- Le versioni di .NET Framework da .NET Framework 4.5.1 a [!INCLUDE[net_current](../../../includes/net-current-version.md)] sono aggiornamenti sul posto di .NET Framework 4.5, ovvero usano la stessa versione di runtime, ma le versioni degli assembly vengono aggiornate e includono nuovi tipi e membri.

- .NET Framework 4,5 e versioni successive sono compilate in modo incrementale in .NET Framework 4. Quando si installa .NET Framework 4,5 o versioni successive in un sistema in cui è installato .NET Framework 4, gli assembly della versione 4 vengono sostituiti con le versioni più recenti.

- Se si fa riferimento a un [pacchetto fuori programma](../get-started/the-net-framework-and-out-of-band-releases.md) di Microsoft nell'app, l'assembly verrà incluso nel pacchetto dell'app.

- Per installare .NET Framework 4,5 o versioni successive, è necessario disporre dei privilegi di amministratore.

- .NET Framework 4,5 è incluso in Windows 8 e Windows Server 2012, quindi non è necessario distribuirlo con l'app in tali sistemi operativi. Analogamente, .NET Framework 4.5.1 è incluso in Windows 8.1 e Windows Server 2012 R2. .NET Framework 4.5.2 non è incluso in nessun sistema operativo. .NET Framework 4.6 è incluso in Windows 10, .NET Framework 4.6.1 è incluso in Windows 10 November Update e .NET Framework 4.6.2 è incluso in Windows 10 Anniversary Update.  .NET Framework 4.7 è incluso in Windows 10 Creators Update, .NET Framework 4.7.1 è incluso in Windows 10 Fall Creators Update e .NET Framework 4.7.2 è incluso nell'aggiornamento di Windows 10 di ottobre 2018 e nell'aggiornamento di Windows 10 di aprile 2018. .NET Framework 4.8 è incluso nell'aggiornamento di Windows 10 di maggio 2019. Per un elenco completo dei requisiti hardware e software, vedere [Requisiti di sistema](../get-started/system-requirements.md).

- A partire da .NET Framework 4.5 gli utenti possono visualizzare un elenco di app .NET Framework in esecuzione durante l'installazione e chiuderle con facilità. In questo modo, è possibile evitare i riavvii del sistema dovuti alle installazioni di .NET Framework. Vedere [Riduzione dei riavvii del sistema](reducing-system-restarts.md).

- Con la disinstallazione di .NET Framework 4,5 o versioni successive vengono rimossi anche i file .NET Framework 4 pre-esistenti. Se si vuole tornare a .NET Framework 4, è necessario reinstallarlo insieme a tutti i relativi aggiornamenti. Vedere [installazione del .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5a4x27ek(v=vs.100)).

- Il file ridistribuibile di .NET Framework 4.5 è stato aggiornato il 9 ottobre 2012 per risolvere un problema correlato a un timestamp errato in un certificato digitale, che ha causato la scadenza anticipata della firma digitale su file creati e firmati da Microsoft. Se in precedenza è stato installato il pacchetto ridistribuibile .NET Framework 4,5 del 16 agosto 2012, è consigliabile aggiornare la copia con la versione più recente ridistribuibile dalla [pagina di download del .NET Framework](https://dotnet.microsoft.com/download/dotnet-framework/net45). Per altre informazioni su questo problema, vedere l' [avviso di sicurezza Microsoft 2749655](https://docs.microsoft.com/security-updates/SecurityAdvisories/2012/2749655).

Per informazioni su come un amministratore di sistema può distribuire .NET Framework e le relative dipendenze di sistema in una rete, vedere [Guida alla distribuzione per amministratori](guide-for-administrators.md).

## <a name="deployment-options-for-your-app"></a>Opzioni di distribuzione per le app

Quando si ritiene di poter procedere alla pubblicazione dell'applicazione in un server Web o in un'altra posizione centralizzata per consentirne l'installazione da parte degli utenti, è possibile scegliere tra diversi metodi di distribuzione. Alcuni di questi vengono forniti con Visual Studio. Nella tabella seguente sono elencate le opzioni di distribuzione per l'applicazione e viene specificato il pacchetto ridistribuibile di .NET Framework che supporta ciascuna opzione. È anche possibile scrivere un programma di installazione personalizzato per l'applicazione. Per altre informazioni, vedere la sezione [Concatenare l'installazione di .NET Framework all'installazione dell'applicazione](#chaining).

|Strategia di distribuzione per l'applicazione|Metodi di distribuzione disponibili|Pacchetto ridistribuibile di .NET Framework da usare|
|--------------------------------------|----------------------------------|-------------------------------------------|
|Installazione dal Web|- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Set di strumenti WiX](#wix)<br />- [Installazione manuale](#installing_manually)|[programma di installazione Web](#redistributable-packages)|
|Installazione da disco|- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Set di strumenti WiX](#wix)<br />- [Installazione manuale](#installing_manually)|[Programma di installazione offline](#redistributable-packages)|
|Installazione da una rete locale (per applicazioni aziendali)|- [ClickOnce](#clickonce-deployment)|[Programma di installazione Web](#redistributable-packages) (vedere [ClickOnce](#clickonce-deployment) per le restrizioni) o [programma di installazione offline](#redistributable-packages)|

## <a name="redistributable-packages"></a>Pacchetti ridistribuibili

.NET Framework è disponibile in due pacchetti ridistribuibili: programma di installazione Web (programma di avvio automatico) e programma di installazione offline (ridistribuibile autonomo). Tutti i download di .NET Framework sono ospitati nella [pagina .NET Framework di download](https://dotnet.microsoft.com/download/dotnet-framework/). Nella tabella seguente vengono confrontati i due pacchetti:

||programma di installazione Web|programma di installazione offline|
|-|-------------------|-----------------------|
|Connessione Internet necessaria?|Sì|No|
|Dimensioni del download|Minime (include il programma di installazione per la sola piattaforma di destinazione)*|Massime*|
|Language Pack|Incluso**|Deve essere [installato separatamente](#chain_langpack), a meno che non si usi il pacchetto destinato a tutti i sistemi operativi|
|Metodo di distribuzione|Supporta tutti i metodi:<br /><br />- [ClickOnce](#clickonce-deployment)<br />- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Windows Installer XML (WiX)](#wix)<br />- [Installazione manuale](#installing_manually)<br />- [Impostazione personalizzata (concatenamento)](#chaining)|Supporta tutti i metodi:<br /><br /> - [ClickOnce](#clickonce-deployment)<br />- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Windows Installer XML (WiX)](#wix)<br />- [Installazione manuale](#installing_manually)<br />- [Impostazione personalizzata (concatenamento)](#chaining)|

\* Il programma di installazione offline è di dimensioni maggiori perché contiene i componenti per tutte le piattaforme di destinazione. Al termine dell'installazione, il sistema operativo Windows memorizza nella cache solo il programma di installazione usato. Se il programma di installazione offline viene eliminato dopo l'installazione, lo spazio su disco usato equivale a quello usato dal programma di installazione Web. Se lo strumento usato, ad esempio [InstallAware](#installaware-deployment) o [InstallShield](#installshield-deployment), per creare il programma di installazione dell'applicazione fornisce una cartella per i file di installazione che viene rimossa dopo l'installazione, il programma di installazione offline può essere eliminato automaticamente inserendolo nella cartella di installazione.

\*\* Se si usa il programma di installazione Web con l'installazione personalizzata, è possibile usare le impostazioni predefinite della lingua basate sull'impostazione dell'interfaccia utente multilingue (MUI) oppure specificare un diverso Language Pack usando l'opzione `/LCID` nella riga di comando. Per alcuni esempi, vedere la sezione [Concatenamento usando l'interfaccia utente predefinita di .NET Framework](#chaining_default) .

## <a name="deployment-methods"></a>Metodi di distribuzione

 Sono disponibili quattro metodi di distribuzione:

- È possibile impostare una dipendenza da .NET Framework. È possibile specificare .NET Framework come prerequisito nell'installazione dell'applicazione, tramite uno di questi metodi:

  - usare la [distribuzione ClickOnce](#clickonce-deployment) (disponibile in Visual Studio)

  - Creare un [progetto di InstallAware](#installaware-deployment) (edizione gratuita disponibile per gli utenti di Visual Studio)

  - Creare un [progetto InstallShield](#installshield-deployment) (disponibile in Visual Studio)

  - usare il [set di strumenti WiX (Windows Installer XML)](#wix)

- È possibile chiedere agli utenti di [installare manualmente .NET Framework](#installing_manually).

- È possibile concatenare (includere) il processo di installazione di .NET Framework nell'installazione dell'applicazione e decidere come gestire l'installazione di .NET Framework:

  - [usare l'interfaccia utente predefinita](#chaining_default). Fare in modo che l'installazione venga gestita dal programma di installazione di .NET Framework.

  - [Personalizzare l'interfaccia utente](#chaining_custom) per offrire un'installazione unificata e per monitorare lo stato di avanzamento dell'installazione di .NET Framework.

Questi metodi di distribuzione vengono descritti in dettaglio nelle sezioni seguenti.

## <a name="setting-a-dependency-on-the-net-framework"></a>Impostazione di una dipendenza da .NET Framework

Se si usa ClickOnce, InstallAware, InstallShield o WiX per distribuire l'applicazione, è possibile aggiungere una dipendenza da .NET Framework in modo che possa essere installata come parte dell'app.

### <a name="clickonce-deployment"></a>distribuzione ClickOnce

È possibile usare una distribuzione ClickOnce per progetti creati con Visual Basic, Visual C#, ma non per progetti creati con Visual C++.

In Visual Studio scegliere la distribuzione ClickOnce e aggiungere una dipendenza da .NET Framework:

1. Aprire il progetto dell'applicazione che si vuole pubblicare.

2. In Esplora soluzioni aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.

3. Scegliere il riquadro **Pubblica** .

4. Scegliere il pulsante **Prerequisiti** .

5. Nella finestra di dialogo **Prerequisiti** verificare che la casella di controllo **Crea programma di installazione per installare componenti dei prerequisiti** sia selezionata.

6. Nell'elenco dei prerequisiti, individuare e selezionare la versione di .NET Framework usata per compilare il progetto.

7. Scegliere un'opzione per specificare il percorso di origine per i prerequisiti e scegliere **OK**.

     Se si fornisce un URL per il percorso di download di .NET Framework, è possibile specificare la pagina di download .NET Framework o un sito personalizzato. Se si inserisce il pacchetto ridistribuibile nel proprio server, deve essere il programma di installazione offline e non il programma di installazione Web. È possibile collegarsi al programma di installazione Web solo nella pagina di download .NET Framework. L'URL può anche specificare un disco in cui viene distribuita l'applicazione.

8. Nella finestra di dialogo **Pagine delle proprietà** scegliere **OK**.

<a name="installaware"></a>

### <a name="installaware-deployment"></a>Distribuzione di InstallAware

InstallAware compila pacchetti di app di Windows (APPX), Windows Installer (MSI), codice nativo (EXE) e App-V (virtualizzazione dell'applicazione) da una singola origine. È facilmente possibile [includere qualsiasi versione di .NET Framework](https://www.installaware.com/one-click-pre-requisite-installer.htm) nella configurazione e personalizzare facoltativamente l'installazione [modificando gli script predefiniti](https://www.installaware.com/msicode.htm). InstallAware, ad esempio, preinstalla in Windows 7 i certificati, senza i quali l'installazione di .NET Framework 4.7 ha esito negativo. Per altre informazioni su InstallAware, vedere il sito Web [InstallAware for Windows Installer](https://www.installaware.com/).

### <a name="installshield-deployment"></a>Distribuzione InstallShield

InstallShield compila i pacchetti dell'app Windows (MSIX, APPX), i pacchetti di Windows Installer (MSI) e i programmi di installazione di codice nativo (EXE). InstallShield fornisce anche l'integrazione con Visual Studio. Per ulteriori informazioni, vedere il sito Web [InstallShield](https://www.flexerasoftware.com/install/products/installshield.html) .

<a name="wix"></a>

### <a name="windows-installer-xml-wix-deployment"></a>Distribuzione di Windows Installer XML (WiX)

Il set di strumenti Windows Installer XML (WiX) compila i pacchetti di installazione di Windows dal codice sorgente XML. WiX supporta un ambiente della riga di comando che può essere integrato nei processi di compilazione per compilare pacchetti di installazione MSM e MSI. Con l'uso di WiX è possibile [specificare .NET Framework come prerequisito](https://wixtoolset.org/documentation/manual/v3/howtos/redistributables_and_install_checks/install_dotnet.html)o [creare un concatenatore](https://wixtoolset.org/documentation/manual/v3/xsd/wix/exepackage.html) per controllare completamente l'esperienza di distribuzione di .NET Framework. Per altre informazioni su WiX, vedere il sito Web del [set di strumenti Windows Installer XML (WiX)](https://wixtoolset.org/) .

<a name="installing_manually"></a>

## <a name="installing-the-net-framework-manually"></a>Installazione manuale di .NET Framework

In alcune situazioni l'installazione automatica di .NET Framework con l'applicazione potrebbe risultare poco pratica. In tali casi, è possibile l'installazione manuale di .NET Framework da parte degli utenti. Il pacchetto ridistribuibile è disponibile in [due pacchetti](#redistributable-packages). Quindi, nel processo di installazione è necessario fornire istruzioni sulle modalità con cui gli utenti dovranno individuare e installare .NET Framework.

<a name="chaining"></a>

## <a name="chaining-the-net-framework-installation-to-your-apps-setup"></a>Concatenare l'installazione di .NET Framework all'installazione dell'applicazione

Se si crea un programma di installazione personalizzato per l'applicazione, è possibile concatenare (includere) il processo di installazione di .NET Framework. nel processo di installazione dell'applicazione. Il concatenamento fornisce due opzioni dell'interfaccia utente per l'installazione di .NET Framework:

- usare l'interfaccia utente predefinita fornita dal programma di installazione di .NET Framework.

- Creare un'interfaccia utente personalizzata per l'installazione di .NET Framework per coerenza con il programma di installazione dell'applicazione.

Entrambi i metodi consentono di usare il programma di installazione Web o il programma di installazione offline. Ogni pacchetto comporta dei vantaggi:

- Se si usa il programma di installazione Web, il processo di installazione di .NET Framework deciderà quale pacchetto di installazione è necessario e scaricherà e installerà solo quel pacchetto dal Web.

- Se si usa il programma di installazione offline, è possibile includere il set completo dei pacchetti di installazione di .NET Framework con i supporti di ridistribuzione in modo che gli utenti non debbano scaricare dal Web eventuali file aggiuntivi durante l'installazione.

<a name="chaining_default"></a>

### <a name="chaining-by-using-the-default-net-framework-ui"></a>Concatenamento usando l'interfaccia utente predefinita di .NET Framework

Per concatenare automaticamente il processo di installazione di .NET Framework e fare in modo che il programma di installazione di .NET Framework fornisca l'interfaccia utente, aggiungere il comando seguente al programma di installazione:

`<.NET Framework redistributable> /q /norestart /ChainingPackage <PackageName>`

Ad esempio, se il programma eseguibile è Contoso.exe e si vuole installare automaticamente il pacchetto ridistribuibile offline di .NET Framework 4.5, usare il comando:

`dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage Contoso`

È possibile usare opzioni aggiuntive della riga di comando per personalizzare l'installazione. Ad esempio:

- Per offrire agli utenti un metodo per chiudere le applicazioni .NET Framework in esecuzione per ridurre al minimo i riavvii del sistema, impostare la modalità passiva e usare l'opzione `/showrmui` come segue:

    `dotNetFx45_Full_x86_x64.exe /norestart /passive /showrmui /ChainingPackage Contoso`

     Questo comando consente a Gestione riavvio di visualizzare una finestra di messaggio che offre agli utenti l'opportunità di chiudere le applicazioni .NET Framework prima di installare .NET Framework.

- Se si usa il programma di installazione Web, è possibile usare l'opzione `/LCID` per specificare un Language Pack. Per concatenare il programma di installazione Web di .NET Framework 4.5 al programma di installazione Contoso e installare il Language Pack giapponese, ad esempio, aggiungere il comando seguente al processo di installazione dell'app:

    `dotNetFx45_Full_setup.exe /q /norestart /ChainingPackage Contoso /LCID 1041`

     Se si omette l'opzione `/LCID` , il programma di installazione installerà il Language Pack corrispondente all'impostazione MUI dell'utente.

    > [!NOTE]
    > Language Pack diversi possono avere date di versione diverse. Se il Language Pack specificato non è disponibile nell'Area download, .NET Framework verrà installato senza il Language Pack. Se .NET Framework è già installato nel computer dell'utente, verrà installato solo il Language Pack.

Per un elenco completo di opzioni, vedere la sezione [Opzioni della riga di comando](#command-line-options) .

Per i codici restituiti comuni, vedere la sezione [Codici restituiti](#return-codes) .

<a name="chaining_custom"></a>

### <a name="chaining-by-using-a-custom-ui"></a>Concatenamento tramite un'interfaccia utente personalizzata

Se è disponibile un pacchetto di installazione personalizzato, è possibile avviare automaticamente l'installazione di .NET Framework e tenerne traccia mentre viene visualizzato lo stato di avanzamento dell'installazione. In questo caso, assicurarsi che il codice riguardi quanto segue:

- Verificare i [requisiti hardware e software di .NET Framework](../get-started/system-requirements.md).

- [Stabilire](#detect_net) se la versione corretta di .NET Framework è già installata nel computer dell'utente.

    > [!IMPORTANT]
    > Per determinare se è già installata la versione corretta di .NET Framework, è necessario controllare se è installata la versione di destinazione *o* una versione successiva, non se è installata la versione di destinazione. In altre parole, è necessario valutare se la combinazione di tasti di rilascio che si recupera dal Registro di sistema è maggiore o uguale alla combinazione di tasti di rilascio della versione di destinazione, *non* se è uguale alla combinazione di tasti di rilascio della versione di destinazione.

- [Stabilire](#detecting-the-language-packs) se i Language Pack sono già installati nel computer dell'utente.

- Se si vuole controllare la distribuzione, avviare automaticamente il processo di installazione di .NET Framework e tenerne traccia (vedere [How to: Get Progress from the .NET Framework 4.5 Installer](how-to-get-progress-from-the-dotnet-installer.md)).

- Se si distribuisce il programma di installazione offline, [concatenare separatamente i Language Pack](#chain_langpack).

- Personalizzare la distribuzione usando le [opzioni della riga di comando](#command-line-options). Se ad esempio si concatena il programma di installazione Web di .NET Framework, ma si vuole sostituire il Language Pack predefinito, usare l'opzione `/LCID` , come descritto nella sezione precedente.

- [Risolvere i problemi](#troubleshooting).

<a name="detect_net"></a>

### <a name="detecting-the-net-framework"></a>Rilevamento di .NET Framework

Il programma di installazione di .NET Framework scrive le chiavi del Registro di sistema quando l'installazione viene completata correttamente. È possibile verificare se .NET Framework 4.5 o versione successiva è installato controllando se nella cartella `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` del Registro di sistema è presente un valore `DWORD` denominato `Release`. Si noti che "NET Framework Setup" non inizia con un punto. L'esistenza di questa chiave indica che nel computer è installato .NET Framework 4,5 o una versione successiva. Il valore di `Release` indica la versione di .NET Framework installata.

> [!IMPORTANT]
> Verificare la presenza di un valore  **maggiore o uguale** al valore della parola chiave Release quando si prova a rilevare se è presente una versione specifica.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|Version|Valore DWORD di Release|
|-------------|--------------------------------|
|.NET Framework 4.8 installato nell'aggiornamento di Windows 10 di maggio 2019|528040|
|.NET Framework 4.8 installato in tutte le versioni del sistema operativo diverse dall'aggiornamento di Windows 10 di maggio 2019|528049|
|.NET Framework 4.7.2 installato nell'Aggiornamento di Windows 10 (aprile 2018) e in Windows Server, versione 1803|461808|
|.NET Framework 4.7.2 installato in tutte le versioni di sistemi operativi diversi dall'Aggiornamento di Windows 10 (aprile 2018) e da Windows Server, versione 1803. Include l'Aggiornamento di Windows 10 (ottobre 2018). |461814|
|.NET Framework 4.7.1 installato in Windows 10 Fall Creators Update e in Windows Server, versione 1709|461308|
|.NET Framework 4.7.1 installato in tutte le versioni di sistemi operativi diversi da Windows 10 Fall Creators Update e Windows Server, versione 1709|461310|
|.NET Framework 4.7 installato in Windows 10 Creators Update|460798|
|.NET Framework 4.7 installato in tutte le versioni del sistema operativo diverse da Windows 10 Creators Update|460805|
|.NET Framework 4.6.2 installato in Windows 10 Anniversary Edition e in Windows Server 2016|394802|
|.NET Framework 4.6.2 installato in tutte le versioni del sistema operativo diverse da Windows 10 Anniversary Edition e Windows Server 2016|394806|
|.NET Framework 4.6.1 installato in Windows 10 November Update|394254|
|.NET Framework 4.6.1 installato in tutte le versioni del sistema operativo diverse da Windows 10 November Update|394271|
|.NET Framework 4.6 installato in Windows 10|393295|
|.NET Framework 4.6 installato in tutte le versioni del sistema operativo diverse da Windows 10|393297|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.5.1 installato con Windows 8.1 o Windows Server 2012 R2|378675|
|.NET Framework 4.5.1 installato in Windows 8, Windows 7|378758|
|.NET Framework 4.5|378389|

### <a name="detecting-the-language-packs"></a>Rilevamento dei Language Pack

È possibile verificare se un Language Pack è installato controllando se nella cartella HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\\*LCID* del Registro di sistema è presente un valore DWORD denominato `Release`. Si noti che "NET Framework Setup" non inizia con un punto. *LCID* specifica un identificatore delle impostazioni locali; vedere [lingue supportate](#supported-languages) per un elenco di tali identificatori.

Ad esempio, per rilevare se è installato il Language Pack giapponese completo (LCID = 1041), recuperare il valore denominato seguente dal registro di sistema:

| | |
|-|-|
| Chiave | HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\1041 |
| Name | Versione |
| Type | DWORD |

Per determinare se per una versione particolare di .NET Framework dalla 4.5 alla 4.7.2 è installata la versione di rilascio finale di un Language Pack, verificare il valore della chiave RELEASE del valore DWORD descritto nella sezione precedente, [Rilevamento di .NET Framework](#detect_net).

<a name="chain_langpack"></a>

### <a name="chaining-the-language-packs-to-your-app-setup"></a>Concatenamento dei Language Pack nell'installazione dell'applicazione

.NET Framework fornisce un set di file eseguibili di Language pack autonomi contenenti le risorse localizzate per impostazioni cultura specifiche. I Language Pack sono disponibili nelle pagine di download .NET Framework:

- [.NET Framework 4,8](https://dotnet.microsoft.com/download/dotnet-framework/net48)
- [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework/net472)
- [.NET Framework 4.7.1](https://dotnet.microsoft.com/download/dotnet-framework/net471)
- [.NET Framework 4,7](https://dotnet.microsoft.com/download/dotnet-framework/net47)
- [.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)
- [.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)
- [.NET framework 4.6](https://dotnet.microsoft.com/download/dotnet-framework/net46)
- [.NET Framework 4.5.2](https://dotnet.microsoft.com/download/dotnet-framework/net452)
- [.NET Framework 4.5.1](https://dotnet.microsoft.com/download/dotnet-framework/net451)
- [.NET Framework 4.5](https://dotnet.microsoft.com/download/dotnet-framework/net45)

> [!IMPORTANT]
> I Language Pack non contengono i componenti di .NET Framework necessari per eseguire un'applicazione. È necessario installare .NET Framework usando il programma di installazione Web o offline prima di installare un Language Pack.

A partire da NET Framework 4.5.1, i nomi dei pacchetti sono in formato NDP<`version`>-KB<`number`>-x86-x64-AllOS-<`culture`>.exe, dove `version` è il numero di versione di .NET Framework, `number` è il numero di un articolo della Microsoft Knowledge Base e `culture` specifica un [paese o un'area geografica](#supported-languages). Un esempio di uno di questi pacchetti è `NDP452-KB2901907-x86-x64-AllOS-JPN.exe`. I nomi di pacchetto sono elencati nella sezione [Redistributable Packages](#redistributable-packages) precedente di questo articolo.

Per installare un Language Pack con il programma di installazione offline di .NET Framework, è necessario concatenarlo all'installazione dell'applicazione. Per distribuire il programma di installazione offline di NET Framework 4.5.1 con il Language Pack per la lingua giapponese, ad esempio, usare il comando seguente:

`NDP451-KB2858728-x86-x64-AllOS-JPN.exe /q /norestart /ChainingPackage <ProductName>`

Non è necessario concatenare i Language Pack se si usa il programma di installazione Web. Verrà installato il Language Pack corrispondente alle impostazioni MUI dell'utente. Se si vuole installare una lingua diversa, è possibile usare l'opzione `/LCID` per specificare un Language Pack.

Per un elenco completo di opzioni della riga di comando, vedere la sezione [Opzioni della riga di comando](#command-line-options) .

### <a name="troubleshooting"></a>Risoluzione dei problemi

#### <a name="return-codes"></a>Codici restituiti

Nella tabella seguente sono elencati i codici restituiti più comuni per il programma di installazione ridistribuibile di .NET Framework. I codici restituiti sono gli stessi per tutte le versioni del programma di installazione. Per collegamenti a informazioni dettagliate, vedere la sezione successiva.

|Codice restituito|Descrizione|
|-----------------|-----------------|
|0|Installazione completata.|
|1602|Installazione annullata dall'utente.|
|1603|Errore irreversibile durante l'installazione.|
|1641|Riavvio necessario per completare l'installazione. Questo messaggio indica l'esito positivo dell'operazione.|
|3010|Riavvio necessario per completare l'installazione. Questo messaggio indica l'esito positivo dell'operazione.|
|5100|Il computer dell'utente non soddisfa i requisiti di sistema.|

#### <a name="download-error-codes"></a>Scaricare i codici di errore

Fare riferimento al contenuto seguente:

- [Background Intelligent Transfer Service (BITS) error codes](https://go.microsoft.com/fwlink/?LinkId=180946) (Codici di errore del Servizio trasferimento intelligente in background (BITS))

- [Codici di errore del moniker URL](https://go.microsoft.com/fwlink/?LinkId=180947)

- [WinHttp error codes](https://go.microsoft.com/fwlink/?LinkId=180948) (Codici di errore WinHttp)

#### <a name="other-error-codes"></a>Altri codici di errore

Fare riferimento al contenuto seguente:

- [Windows Installer error codes](https://go.microsoft.com/fwlink/?LinkId=180949) (Codici di errore di Windows Installer)

- [Windows Update Agent result codes](https://go.microsoft.com/fwlink/?LinkId=180951) (Codici restituiti dall'Agente di Windows Update)

## <a name="uninstalling-the-net-framework"></a>Disinstallazione di .NET Framework

A partire da Windows 8, è possibile disinstallare .NET Framework 4,5 o versioni successive usando **attivazione e disattivazione delle funzionalità Windows** nel pannello di controllo. Nelle versioni precedenti di Windows è possibile disinstallare .NET Framework 4,5 o versioni successive utilizzando **Installazione applicazioni** nel pannello di controllo.

> [!IMPORTANT]
> Per Windows 7 e sistemi operativi precedenti, la disinstallazione di .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8 non ripristina i file di .NET Framework 4.5 e la disinstallazione di .NET Framework 4.5 non ripristina i file di .NET Framework 4. Se si vuole tornare alla versione precedente, è necessario reinstallarla con tutti gli aggiornamenti.

## <a name="appendix"></a>Appendice

### <a name="command-line-options"></a>Opzioni della riga di comando

Nella tabella seguente sono elencate le opzioni che è possibile includere quando si concatena il file ridistribuibile di NET Framework 4.5 all'installazione dell'applicazione.

|Opzione|Descrizione|
|------------|-----------------|
|**/CEIPConsent**|Sostituisce il comportamento predefinito e invia un commento anonimo a Microsoft al fine di migliorare le future esperienze di distribuzione. È possibile usare questa opzione solo se il programma di installazione richiede il consenso e se l'utente concede l'autorizzazione a inviare commenti anonimi a Microsoft.|
|**/chainingpackage** `packageName`|Specifica il nome dell'eseguibile che esegue il concatenamento. Queste informazioni vengono inviate a Microsoft come commento anonimo per contribuire a migliorare le future esperienze di distribuzione.<br /><br /> Se il nome del pacchetto include spazi, usare le virgolette doppie come delimitatori, ad esempio: **/chainingpackage "Lucerne Publishing"**. Per un esempio di un pacchetto di concatenamento, vedere [recupero di informazioni sullo stato di avanzamento da un pacchetto di installazione](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).|
|**/LCID**  `LCID`<br /><br /> dove `LCID` specifica un identificatore delle impostazioni locali (vedere [lingue supportate](#supported-languages)).|Installa il Language Pack specificato da `LCID` e forza la visualizzazione dell'interfaccia utente in tale lingua, a meno che non sia impostata la modalità non interattiva.<br /><br /> Per il programma di installazione Web, questa opzione concatena-installa il Language Pack dal Web. **Nota:** usare questa opzione solo con il programma di installazione Web.|
|**/log** `file` &#124; `folder`|Specifica il percorso del file di log. Il valore predefinito è la cartella temporanea per il processo e il nome del file predefinito è basato sul pacchetto. Se l'estensione del file è TXT, viene prodotto un log in formato testo. Se si specifica un'altra estensione o nessuna estensione, viene creato un log in formato HTML.|
|**/msioptions**|Specifica le opzioni da passare per gli elementi MSI e MSP, ad esempio: `/msioptions "PROPERTY1='Value'"`.|
|**/norestart**|Impedisce il riavvio automatico del programma di installazione. Se si usa questa opzione, l'applicazione di concatenamento deve acquisire il codice restituito e gestire il riavvio (vedere [recupero di informazioni sullo stato di avanzamento da un pacchetto di installazione](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100))).|
|**/passive**|Imposta la modalità passiva. Visualizza la barra di stato per indicare che l'installazione è in corso, ma non presenta prompt o messaggi di errore all'utente. In questa modalità, se concatenato da un programma di installazione, il pacchetto di concatenamento deve gestire [codici restituiti](#return-codes).|
|**/pipe**|Crea un canale di comunicazione per consentire a un pacchetto di concatenamento di ottenere lo stato di avanzamento.|
|**/promptrestart**|Solo modalità passiva, se il programma di installazione richiede un riavvio, viene visualizzato un prompt di richiesta. Questa opzione richiede l'interazione dell'utente se è richiesto un riavvio.|
|**/q**|Imposta la modalità non interattiva.|
|**/Repair**|Attiva la funzionalità di ripristino.|
|**/serialdownload**|Forza l'esecuzione dell'installazione solo al termine del download del pacchetto.|
|**/showfinalerror**|Imposta la modalità passiva. Visualizza errori solo se l'installazione non viene completata correttamente. Questa opzione richiede l'interazione dell'utente se l'installazione non viene completata.|
|**/showrmui**|Usata solo con l'opzione **/passive** . Visualizza una finestra di messaggio che richiede agli utenti di chiudere le applicazioni .NET Framework in esecuzione. Questa finestra di messaggio mantiene lo stesso comportamento a prescindere dalla modalità.|
|**/uninstall**|Disinstalla .NET Framework ridistribuibile.|

### <a name="supported-languages"></a>Lingue supportate

Nella tabella seguente sono elencati .NET Framework Language Pack disponibili per .NET Framework 4,5 e versioni successive.

|LCID|Lingua (paese/area)|Impostazioni cultura|
|----------|--------------------------------|-------------|
|1025|Arabo (Arabia Saudita)|ar|
|1028|Cinese (tradizionale)|zh-Hant|
|1029|Ceco|cs|
|1030|Danese|da|
|1031|Tedesco (Germania)|de|
|1032|Greco|el|
|1035|Finlandese|fi|
|1036|Francese (Francia)|fr|
|1037|Ebraico|he|
|1038|Ungherese|hu|
|1040|Italiano (Italia)|it|
|1041|Giapponese|ja|
|1042|Coreano|ko|
|1043|Olandese (Paesi Bassi)|nl|
|1044|Norvegese (Bokmål)|no|
|1045|Polacco|pl|
|1046|Portoghese (Brasile)|pt-BR|
|1049|Russo|ru|
|1053|Svedese|sv|
|1055|Turco|tr|
|2052|Cinese (semplificato)|zh-Hans|
|2070|Portoghese (Portogallo)|pt-PT|
|3082|Spagnolo (Spagna, ordinamento moderno)|es|

## <a name="see-also"></a>Vedere anche

- [Guida alla distribuzione per amministratori](guide-for-administrators.md)
- [Requisiti di sistema](../get-started/system-requirements.md)
- [Installare .NET Framework per sviluppatori](../install/guide-for-developers.md)
- [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
- [Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5](reducing-system-restarts.md)
- [Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)
