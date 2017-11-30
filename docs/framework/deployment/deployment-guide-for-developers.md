---
title: Guida alla distribuzione di .NET Framework per sviluppatori
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- developer's guide, deploying .NET Framework
- deployment [.NET Framework], developer's guide
ms.assetid: 094d043e-33c4-40ba-a503-e0b20b55f4cf
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 287005af09f3f022c368d3c8fab12ad02b30e944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="net-framework-deployment-guide-for-developers"></a>Guida alla distribuzione di .NET Framework per sviluppatori
In questo argomento vengono fornite informazioni per gli sviluppatori che desiderano installare il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, il [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, o il 4.7 di .NET Framework o 4.7.1 con le proprie app.

Per i collegamenti ai download, vedere la sezione [Pacchetti ridistribuibili](#redistributable-packages). È anche possibile scaricare i pacchetti ridistribuibili e i Language Pack dalle pagine dell'Area download Microsoft seguenti:

- .NET framework, 4.7.1 per tutti i sistemi operativi ([programma di installazione web](http://go.microsoft.com/fwlink/?LinkId=852095) o [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=852107))

- .NET Framework 4.7 per tutti i sistemi operativi ([programma di installazione Web](http://go.microsoft.com/fwlink/?LinkId=825299) o [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=825303))

- [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] per tutti i sistemi operativi ([programma di installazione Web](http://go.microsoft.com/fwlink/?LinkId=780597) oppure [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=780601))

- [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] per tutti i sistemi operativi ([programma di installazione Web](http://go.microsoft.com/fwlink/?LinkId=671729) oppure [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=671744))

- [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] per tutti i sistemi operativi ([programma di installazione Web](http://go.microsoft.com/fwlink/?LinkId=528222) oppure [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=528232))

- .NET Framework 4.5.2 per tutti i sistemi operativi ([programma di installazione Web](http://go.microsoft.com/fwlink/p/?LinkId=397703) o [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=397706))

- .NET Framework 4.5.1 per tutti i sistemi operativi ([programma di installazione Web](http://go.microsoft.com/fwlink/p/?LinkId=310158) o [programma di installazione offline](http://go.microsoft.com/fwlink/p/?LinkId=310159))

- [.NET Framework 4.5](http://go.microsoft.com/fwlink/p/?LinkId=245484)

 Note importanti:

> [!NOTE]
> La frase "il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e le versioni intermedie" si intende il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e tutte le versioni successive.

- Il [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.7.1, 4.7, 4.6.2, 4.6.1, 4.6 e 4.5.2 sono aggiornamenti sul posto di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], ovvero usano la stessa versione di runtime, ma le versioni degli assembly sono aggiornate e includono nuovi tipi e membri.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e le relative versioni vengono compilati in modo incrementale in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Quando si installa il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 o 4.7.1 in un sistema con il [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] , gli assembly della versione 4 vengono sostituiti con versioni più recenti.

- Se si fa riferimento a un [pacchetto fuori programma](http://msdn.microsoft.com/library/dn151288\(v=vs.110\).aspx) di Microsoft nell'app, l'assembly verrà incluso nel pacchetto dell'app.

- È necessario avere privilegi di amministratore per installare [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e le relative versioni intermedie.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] è incluso in [!INCLUDE[win8](../../../includes/win8-md.md)] e [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], quindi non è necessario distribuirlo con l'applicazione in questi sistemi operativi. Analogamente, [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] è incluso in [!INCLUDE[win81](../../../includes/win81-md.md)] e Windows Server 2012 R2. .NET Framework 4.5.2 non è incluso in nessun sistema operativo. [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] è incluso in Windows 10, [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] è incluso nell'aggiornamento di novembre di Windows 10 e [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] è incluso nell'aggiornamento dell'anniversario di Windows 10.  Il 4.7 di .NET Framework è incluso in Windows 10 creatori di aggiornamento e .NET Framework 4.7.1 è incluso in Windows 10 rientrano creatori di aggiornamento. Per un elenco completo dei requisiti hardware e software, vedere [Requisiti di sistema](../../../docs/framework/get-started/system-requirements.md).

- A partire da [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], gli utenti possono visualizzare un elenco di applicazioni .NET Framework in esecuzione durante l'installazione e chiuderle con facilità. In questo modo, è possibile evitare i riavvii del sistema dovuti alle installazioni di .NET Framework. Vedere [Riduzione dei riavvii del sistema](../../../docs/framework/deployment/reducing-system-restarts.md).

- Se si disinstalla [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una delle versioni intermedie, si rimuovono anche i file [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] preesistenti. Se si vuole tornare a [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], è necessario reinstallarlo insieme a tutti i relativi aggiornamenti. Vedere [Installazione di .NET Framework 4](http://msdn.microsoft.com/library/5a4x27ek\(v=vs.100\).aspx).

- Il file ridistribuibile di .NET Framework 4.5 è stato aggiornato il 9 ottobre 2012 per risolvere un problema correlato a un timestamp errato in un certificato digitale, che ha causato la scadenza anticipata della firma digitale su file creati e firmati da Microsoft. Se in precedenza è stato installato .NET Framework 4.5 Redistributable Package del 16 agosto 2012, è consigliabile aggiornare la copia con l'ultimo file ridistribuibile dall' [Area download Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=245484). Per altre informazioni su questo problema, vedere l' [avviso di sicurezza Microsoft 2749655](http://technet.microsoft.com/security/advisory/2749655).

 Per informazioni su come un amministratore di sistema può distribuire .NET Framework e le relative dipendenze di sistema in una rete, vedere [Guida alla distribuzione per amministratori](../../../docs/framework/deployment/guide-for-administrators.md).

## <a name="deployment-options-for-your-app"></a>Opzioni di distribuzione per le app
 Quando si ritiene di poter procedere alla pubblicazione dell'applicazione in un server Web o in un'altra posizione centralizzata per consentirne l'installazione da parte degli utenti, è possibile scegliere tra diversi metodi di distribuzione. Alcuni di questi vengono forniti con Visual Studio. Nella tabella seguente sono elencate le opzioni di distribuzione per l'app e specifica il pacchetto ridistribuibile di .NET Framework che supporta ciascuna opzione. È anche possibile scrivere un programma di installazione personalizzato per l'applicazione. Per altre informazioni, vedere la sezione [Concatenare l'installazione di .NET Framework all'installazione dell'applicazione](#chaining).

|Strategia di distribuzione per l'applicazione|Metodi di distribuzione disponibili|Pacchetto ridistribuibile di .NET Framework da usare|
|--------------------------------------|----------------------------------|-------------------------------------------|
|Installazione dal Web|- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Set di strumenti WiX](#wix)<br />- [Installazione manuale](#installing_manually)|[Web installer](#redistributable-packages)|
|Installazione da disco|- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Set di strumenti WiX](#wix)<br />- [Installazione manuale](#installing_manually)|[Offline installer](#redistributable-packages)|
|Installazione da una rete locale (per applicazioni aziendali)|- [ClickOnce](#clickonce-deployment)|[Programma di installazione Web](#redistributable-packages) (vedere [ClickOnce](#clickonce-deployment) per le restrizioni) o [programma di installazione offline](#redistributable-packages)|

## <a name="redistributable-packages"></a>Pacchetti ridistribuibili
 .NET Framework è disponibile in due pacchetti ridistribuibili: programma di installazione Web (programma di avvio automatico) e programma di installazione offline (ridistribuibile autonomo). Nella tabella seguente vengono confrontati i due pacchetti.

||programma di installazione Web|programma di installazione offline|
|-|-------------------|-----------------------|
|File per il download|.NET framework 4.7.1: <br/>[NDP471-KB4033344-Web.exe](http://go.microsoft.com/fwlin/?LinkId=852092)<br/><br/>.NET Framework 4.7: <br />[NDP47-KB3186500-Web.exe](http://go.microsoft.com/fwlink/?LinkId=825298) <br /><br />[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]: <br />[NDP462-KB3151802-Web.exe](http://go.microsoft.com/fwlink/?LinkId=780596)<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]:<br />[NDP461-KB3102438-Web.exe](http://go.microsoft.com/fwlink/?LinkId=671728)<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]:<br />[NDP46-KB3045560-Web.exe](http://go.microsoft.com/fwlink/?LinkId=528222)<br /><br /> .NET Framework 4.5.2: <br />[NDP452-KB2901954-Web.exe](http://go.microsoft.com/fwlink/?LinkId=397707)<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]: <br />[NDP451-KB2859818-Web.exe](http://go.microsoft.com/fwlink/?LinkId=322115)<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]: <br />[dotNetFx45_Full_setup.exe](http://go.microsoft.com/fwlink/?LinkId=225704)|.NET framework 4.7.1: <br />[NDP471-KB4033342-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=852104) <br /><br />.NET Framework 4.7: <br />[NDP47-KB3186497-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=825302) <br /><br />[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]: <br />[NDP462-KB3151800-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=780600)<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]: <br />[NDP461-KB3102436-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=671743)<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]: <br />[NDP46-KB3045557-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=528232)<br /><br /> .NET Framework 4.5.2: <br />[NDP452-KB2901907-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=397708)<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]: <br />[NDP451-KB2858728-x86-x64-AllOS-ENU.exe](http://go.microsoft.com/fwlink/?LinkId=322116)<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]: <br />[dotNetFx45_Full_x86_x64.exe](http://go.microsoft.com/fwlink/?LinkId=225702)|
|Connessione Internet necessaria?|Sì|No|
|Dimensioni del download|Minime (include il programma di installazione per la sola piattaforma di destinazione)*|Massime*|
|Language Pack|Incluso**|Deve essere [installato separatamente](#chain_langpack), a meno che non si usi il pacchetto destinato a tutti i sistemi operativi|
|Metodo di distribuzione|Supporta tutti i metodi:<br /><br />- [ClickOnce](#clickonce-deployment)<br />- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Windows Installer XML (WiX)](#wix)<br />- [Installazione manuale](#installing_manually)<br />- [Impostazione personalizzata (concatenamento)](#chaining)|Supporta tutti i metodi:<br /><br /> - [ClickOnce](#clickonce-deployment)<br />- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Windows Installer XML (WiX)](#wix)<br />- [Installazione manuale](#installing_manually)<br />- [Impostazione personalizzata (concatenamento)](#chaining)|
|Percorso di download per la distribuzione ClickOnce|Area download Microsoft:<br /><br /> - [.NET framework 4.7.1](http://go.microsoft.com/fwlink/?LinkId=852092) <br/> - [.NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825298) <br/> - [.NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=780596)<br />- [.NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=671728)<br />- [.NET Framework 4.6](http://go.microsoft.com/fwlink/?LinkId=528222)<br />- [.NET Framework 4.5.2](http://go.microsoft.com/fwlink/?LinkId=397703)<br />- [.NET Framework 4.5.1](http://go.microsoft.com/fwlink/p/?LinkId=310158)<br />- [.NET Framework 4.5](http://go.microsoft.com/fwlink/p/?LinkId=245484)|Proprio server o Area download Microsoft:<br /><br /> - [.NET framework 4.7.1](http://go.microsoft.com/fwlink/?LinkId=852104)<br /> - [.NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825302)<br /> - [.NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=780600)<br />- [.NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=671743)<br />- [.NET Framework 4.6](http://go.microsoft.com/fwlink/?LinkId=528232)<br />- [.NET Framework 4.5.2](http://go.microsoft.com/fwlink/p/?LinkId=397706)<br />- [.NET Framework 4.5.1](http://go.microsoft.com/fwlink/p/?LinkId=310159)<br />- [.NET Framework 4.5](http://go.microsoft.com/fwlink/p/?LinkId=245484)|

 \* Il programma di installazione offline è di dimensioni maggiori perché contiene i componenti per tutte le piattaforme di destinazione. Al termine dell'installazione, il sistema operativo Windows memorizza nella cache solo il programma di installazione usato. Se il programma di installazione offline viene eliminato dopo l'installazione, lo spazio su disco usato equivale a quello usato dal programma di installazione Web. Se lo strumento utilizzato (ad esempio, [InstallAware](#installaware-deployment) o [InstallShield](#installshield-deployment)) per creare il programma di installazione dell'applicazione fornisce una cartella di file di installazione che viene rimossa dopo l'installazione, il programma di installazione offline può essere viene eliminato automaticamente inserendolo nella cartella di installazione.

 ** Se si usa il programma di installazione Web con l'installazione personalizzata, è possibile usare le impostazioni predefinite della lingua basate sull'impostazione dell'interfaccia utente multilingue (MUI) oppure specificare un diverso Language Pack usando l'opzione `/LCID` sulla riga di comando. Per alcuni esempi, vedere la sezione [Concatenamento usando l'interfaccia utente predefinita di .NET Framework](#chaining_default) .

## <a name="deployment-methods"></a>Metodi di distribuzione
 Sono disponibili quattro metodi di distribuzione:

- È possibile impostare una dipendenza da .NET Framework. È possibile specificare .NET Framework come prerequisito nell'installazione dell'applicazione, tramite uno di questi metodi:

    - usare la [distribuzione ClickOnce](#clickonce-deployment) (disponibile in Visual Studio)

    - Creare un [InstallAware progetto](#installaware-deployment) (edizione gratuita disponibile per gli utenti di Visual Studio)

    - Creare un [progetto InstallShield](#installshield-deployment) (disponibile in Visual Studio)

    - usare il [set di strumenti WiX (Windows Installer XML)](#wix)

- È possibile chiedere agli utenti di [installare manualmente .NET Framework](#installing_manually).

- È possibile concatenare (includere) il processo di installazione di .NET Framework nell'installazione dell'applicazione e decidere come gestire l'installazione di .NET Framework:

    - [usare l'interfaccia utente predefinita](#chaining_default). Fare in modo che l'installazione venga gestita dal programma di installazione di .NET Framework.

    - [Personalizzare l'interfaccia utente](#chaining_custom) per offrire un'installazione unificata e per monitorare lo stato di avanzamento dell'installazione di .NET Framework.

 Questi metodi di distribuzione vengono descritti in dettaglio nelle sezioni seguenti.

## <a name="setting-a-dependency-on-the-net-framework"></a>Impostazione di una dipendenza da .NET Framework
Se si usa ClickOnce, InstallAware, InstallShield o WiX per distribuire l'applicazione, è possibile aggiungere una dipendenza su .NET Framework, pertanto può essere installato come parte dell'applicazione.

### <a name="clickonce-deployment"></a>distribuzione ClickOnce
 È possibile usare una distribuzione ClickOnce per progetti creati con Visual Basic, Visual C#, ma non per progetti creati con Visual C++.

 In Visual Studio scegliere la distribuzione ClickOnce e aggiungere una dipendenza da .NET Framework:

1.  Aprire il progetto dell'applicazione che si vuole pubblicare.

2.  In Esplora soluzioni aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.

3.  Scegliere il riquadro **Pubblica** .

4.  Scegliere il pulsante **Prerequisiti** .

5.  Nella finestra di dialogo **Prerequisiti** verificare che la casella di controllo **Crea programma di installazione per installare componenti dei prerequisiti** sia selezionata.

6.  Nell'elenco dei prerequisiti, individuare e selezionare la versione di .NET Framework usata per compilare il progetto.

7.  Scegliere un'opzione per specificare il percorso di origine per i prerequisiti e scegliere **OK**.

     Se si fornisce un URL per il percorso di download di .NET Framework, è possibile specificare il sito Web dell'Area download Microsoft oppure un sito Web di propria scelta. Se si inserisce il pacchetto ridistribuibile nel proprio server, deve essere il programma di installazione offline e non il programma di installazione Web. È possibile creare un collegamento al programma di installazione Web nell'Area download Microsoft. L'URL può anche specificare un disco in cui viene distribuita l'applicazione.

8.  Nella finestra di dialogo **Pagine delle proprietà** scegliere **OK**.

<a name="installaware"></a> 
### <a name="installaware-deployment"></a>Distribuzione InstallAware
InstallAware Compila (APPX) app di Windows, Windows Installer (MSI), codice nativo (EXE) e pacchetti App-V (Application Virtualization) da un'unica origine. Facilmente [includono qualsiasi versione di .NET Framework](https://www.installaware.com/one-click-pre-requisite-installer.htm) nella configurazione, personalizzazione, facoltativamente, l'installazione da [la modifica di script predefinito](https://www.installaware.com/msicode.htm). Ad esempio possibile InstallAware pre-installare certificati in Windows 7, senza che il programma di installazione di .NET Framework 4.7 ha esito negativo. Per ulteriori informazioni su InstallAware, vedere il [InstallAware per Windows Installer](https://www.installaware.com/) sito Web.

### <a name="installshield-deployment"></a>Distribuzione InstallShield
 In Visual Studio scegliere la distribuzione InstallShield e aggiungere una dipendenza da .NET Framework:

1.  Nella barra dei menu di Visual Studio scegliere **File**, **Nuovo**, **Progetto**.

2.  Nel riquadro sinistro della finestra di dialogo **Nuovo progetto** scegliere **Altri tipi di progetto**, **Installazione e distribuzione**, **InstallShield LE**.

3.  Nella casella **Nome** digitare un nome per il progetto e scegliere **OK**.

4.  Se si sta creando un progetto di installazione e distribuzione per la prima volta, scegliere **Accedi a InstallShield** o **Abilita InstallShield Limited Edition** per scaricare InstallShield Limited Edition per la versione di Microsoft Visual Studio. Riavviare Visual Studio.

5.  Passare alla procedura guidata **Project Assistant** e scegliere **File applicazione** per aggiungere l'output del progetto. È possibile configurare altri attributi del progetto tramite la procedura guidata.

6.  Passare a **Requisiti per l'installazione** e selezionare i sistemi operativi e la versione di .NET Framework che si vuole installare.

7.  Aprire il menu di scelta rapida per il progetto di installazione e scegliere **Compila**.
 
<a name="wix"></a> 
### <a name="windows-installer-xml-wix-deployment"></a>Distribuzione di Windows Installer XML (WiX)
 Il set di strumenti Windows Installer XML (WiX) compila i pacchetti di installazione di Windows dal codice sorgente XML. WiX supporta un ambiente della riga di comando che può essere integrato nei processi di compilazione per compilare pacchetti di installazione MSM e MSI. Con l'uso di WiX è possibile [specificare .NET Framework come prerequisito](http://wixtoolset.org/documentation/manual/v3/howtos/redistributables_and_install_checks/install_dotnet.html)o [creare un concatenatore](http://wixtoolset.org/documentation/manual/v3/xsd/wix/exepackage.html) per controllare completamente l'esperienza di distribuzione di .NET Framework. Per altre informazioni su WiX, vedere il sito Web del [set di strumenti Windows Installer XML (WiX)](http://wixtoolset.org/) .

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

```
<.NET Framework redistributable> /q /norestart /ChainingPackage <PackageName>
```

 Se, ad esempio, il programma eseguibile è Contoso.exe e si vuole installare automaticamente il pacchetto ridistribuibile offline di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] , usare il comando:

```
dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage Contoso
```

 È possibile usare opzioni aggiuntive della riga di comando per personalizzare l'installazione. Ad esempio:

- Per offrire agli utenti un metodo per chiudere le applicazioni .NET Framework in esecuzione per ridurre al minimo i riavvii del sistema, impostare la modalità passiva e usare l'opzione `/showrmui` come segue:

    ```
    dotNetFx45_Full_x86_x64.exe /norestart /passive /showrmui /ChainingPackage Contoso
    ```

     Questo comando consente a Gestione riavvio di visualizzare una finestra di messaggio che offre agli utenti l'opportunità di chiudere le applicazioni .NET Framework prima di installare .NET Framework.

- Se si usa il programma di installazione Web, è possibile usare l'opzione `/LCID` per specificare un Language Pack. Per concatenare il programma di installazione Web di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] al programma di installazione Contoso e installare il Language Pack giapponese, ad esempio, aggiungere il comando seguente al processo di installazione dell'applicazione:

    ```
    dotNetFx45_Full_setup.exe /q /norestart /ChainingPackage Contoso /LCID 1041
    ```

     Se si omette l'opzione `/LCID` , il programma di installazione installerà il Language Pack corrispondente all'impostazione MUI dell'utente.

    > [!NOTE]
    > Language Pack diversi possono avere date di versione diverse. Se il Language Pack specificato non è disponibile nell'Area download, .NET Framework verrà installato senza il Language Pack. Se .NET Framework è già installato nel computer dell'utente, verrà installato solo il Language Pack.

 Per un elenco completo di opzioni, vedere la sezione [Opzioni della riga di comando](#command-line-options) .

 Per i codici restituiti comuni, vedere la sezione [Codici restituiti](#return-codes) .

<a name="chaining_custom"></a>
### <a name="chaining-by-using-a-custom-ui"></a>Concatenamento tramite un'interfaccia utente personalizzata
 Se è disponibile un pacchetto di installazione personalizzato, è possibile avviare automaticamente l'installazione di .NET Framework e tenerne traccia mentre viene visualizzato lo stato di avanzamento dell'installazione. In questo caso, assicurarsi che il codice riguardi quanto segue:

- Verificare i [requisiti hardware e software di .NET Framework](../../../docs/framework/get-started/system-requirements.md).

- [Stabilire](#detect_net) se la versione corretta di .NET Framework è già installata nel computer dell'utente.

    > [!IMPORTANT]
    > Per determinare se è già installata la versione corretta di .NET Framework, è necessario controllare se è installata la versione di destinazione *o* una versione successiva, non se è installata la versione di destinazione. In altre parole, è necessario valutare se la combinazione di tasti di rilascio che si recupera dal Registro di sistema è maggiore o uguale alla combinazione di tasti di rilascio della versione di destinazione, *non* se è uguale alla combinazione di tasti di rilascio della versione di destinazione.

- [Stabilire](#detecting-the-language-packs) se i Language Pack sono già installati nel computer dell'utente.

- Se si vuole controllare la distribuzione, avviare automaticamente il processo di installazione di .NET Framework e tenerne traccia (vedere [How to: Get Progress from the .NET Framework 4.5 Installer](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)).

- Se si distribuisce il programma di installazione offline, [concatenare separatamente i Language Pack](#chain_langpack).

- Personalizzare la distribuzione usando le [opzioni della riga di comando](#command-line-options). Se ad esempio si concatena il programma di installazione Web di .NET Framework, ma si vuole sostituire il Language Pack predefinito, usare l'opzione `/LCID` , come descritto nella sezione precedente.

- [Risolvere i problemi](#troubleshooting).

<a name="detect_net"></a>
### <a name="detecting-the-net-framework"></a>Rilevamento di .NET Framework
 Il programma di installazione di .NET Framework scrive le chiavi del Registro di sistema quando l'installazione viene completata correttamente. È possibile verificare se [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versione successiva è installato controllando se nella cartella `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` del Registro di sistema è presente un valore `DWORD` denominato `Release`. Si noti che "NET Framework Setup" non inizia con un punto. La presenza di questa chiave indica che [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versione successiva è installato nel computer. Il valore di `Release` indica la versione di .NET Framework installata.

> [!IMPORTANT]
> Verificare la presenza di un valore  **maggiore o uguale** al valore della parola chiave Release quando si prova a rilevare se è presente una versione specifica.

|Versione|Valore DWORD di Release|
|-------------|--------------------------------|
|.NET framework installato in Windows 10 rientrano creatori Update 4.7.1|461308|
|.NET framework installato in tutte le versioni del sistema operativo diverse dall'aggiornamento di Windows 10 rientrano creatori 4.7.1|461310|
|.NET Framework 4.7 installato in Windows 10 Creators Update|460798|
|.NET Framework 4.7 installato in tutte le versioni del sistema operativo diverse da Windows 10 Creators Update|460805|
|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] installato nell'aggiornamento dell'anniversario di Windows 10|394802|
|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] installato in tutte le versioni di sistemi operativi diversi dall'aggiornamento dell'anniversario di Windows 10|394806|
|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] installato nell'aggiornamento di novembre di Windows 10|394254|
|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] installato in tutte le versioni del sistema operativo diverse dall'aggiornamento di novembre di Windows 10|394271|
|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] installato in Windows 10|393295|
|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] installato in tutte le versioni di sistemi operativi diversi da Windows 10|393297|
|.NET Framework 4.5.2|379893|
|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] installato con [!INCLUDE[win81](../../../includes/win81-md.md)] o Windows Server 2012 R2|378675|
|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] installato in [!INCLUDE[win8](../../../includes/win8-md.md)], Windows 7|378758|
|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]|378389|

### <a name="detecting-the-language-packs"></a>Rilevamento dei Language Pack
 È possibile verificare se un Language Pack è installato controllando se nella cartella HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\\*LCID* del Registro di sistema è presente un valore DWORD denominato `Release`. Si noti che "NET Framework Setup" non inizia con un punto. *LCID* specifica un identificatore delle impostazioni locali; vedere le [lingue supportate](#supported-languages) per un elenco di tali identificatori.

 Per rilevare se il Language Pack completo della lingua giapponese (LCID=1041) è installato, ad esempio, controllare i valori seguenti nel Registro di sistema:

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\1041
Name: Release
Type: DWORD
```

 Per determinare se la versione di rilascio finale di un language pack è installata per il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 o 4.7.1, verificare il valore della versione chiave valore DWORD descritto nella sezione precedente, [rilevamento .NET Framework](#detect_net).

<a name="chain_langpack"></a> 
### <a name="chaining-the-language-packs-to-your-app-setup"></a>Concatenamento dei Language Pack nell'installazione dell'applicazione
 .NET Framework fornisce un set di file eseguibili di Language pack autonomi contenenti le risorse localizzate per impostazioni cultura specifiche. I Language Pack sono disponibili nell'Area download Microsoft:

- [Language pack di.NET framework 4.7.1](http://go.microsoft.com/fwlink/p/?LinkId=852090)

- [Language Pack di.NET Framework 4.7](http://go.microsoft.com/fwlink/p/?LinkId=825306)

- [Language Pack di.NET Framework 4.6.2](http://go.microsoft.com/fwlink/p/?LinkId=780604)

- [Language Pack di.NET Framework 4.6.1](http://go.microsoft.com/fwlink/p/?LinkId=671747)

- [Language Pack di.NET Framework 4.6](http://go.microsoft.com/fwlink/p/?LinkId=528314)

- [Language Pack di.NET Framework 4.5.2](http://go.microsoft.com/fwlink/p/?LinkId=397701)

- [Language Pack di.NET Framework 4.5.1](http://go.microsoft.com/fwlink/p/?LinkId=322101)

- [Language Pack di.NET Framework 4.5](http://go.microsoft.com/fwlink/p/?LinkId=245451)

> [!IMPORTANT]
> I Language Pack non contengono i componenti di .NET Framework necessari per eseguire un'applicazione. È necessario installare .NET Framework usando il programma di installazione Web o offline prima di installare un Language Pack.

 A partire da [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], i nomi dei pacchetti sono in formato NDP<`version`>-KB<`number`>-x86-x64-AllOS-<`culture`>.exe, dove `version` è il numero di versione di .NET Framework, `number` è il numero di un articolo della Microsoft Knowledge Base e `culture` specifica [un paese o un'area geografica](#supported-languages). Un esempio di uno di questi pacchetti è `NDP452-KB2901907-x86-x64-AllOS-JPN.exe`. I nomi di pacchetto sono elencati nella sezione [Redistributable Packages](#redistributable-packages) precedente di questo articolo.

 Per installare un Language Pack con il programma di installazione offline di .NET Framework, è necessario concatenarlo all'installazione dell'applicazione. Per distribuire il programma di installazione offline di [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] con il Language Pack per la lingua giapponese, ad esempio, usare il comando seguente:

```
NDP451-KB2858728-x86-x64-AllOS-JPN.exe/q /norestart /ChainingPackage <ProductName>
```

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
 Vedere il contenuto seguente:

- [Background Intelligent Transfer Service (BITS) error codes](http://go.microsoft.com/fwlink/?LinkId=180946) (Codici di errore del Servizio trasferimento intelligente in background (BITS))

- [Codici di errore del moniker URL](http://go.microsoft.com/fwlink/?LinkId=180947)

- [Codici di errore WinHttp](http://go.microsoft.com/fwlink/?LinkId=180948)

#### <a name="other-error-codes"></a>Altri codici di errore
 Vedere il contenuto seguente:

- [Windows Installer error codes](http://go.microsoft.com/fwlink/?LinkId=180949) (Codici di errore di Windows Installer)

- [Codici di risultato dell'Agente di Windows Update](http://go.microsoft.com/fwlink/?LinkId=180951)

## <a name="uninstalling-the-net-framework"></a>Disinstallazione di .NET Framework
 A partire da [!INCLUDE[win8](../../../includes/win8-md.md)], è possibile disinstallare il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 o 4.7.1 utilizzando **funzionalità di Windows di attivare e disattivare** nel Pannello di controllo. Nelle versioni precedenti di Windows, è possibile disinstallare il [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 o 4.7.1 utilizzando **Aggiungi / Rimuovi programmi** nel Pannello di controllo.

> [!IMPORTANT]
> Per Windows 7 e sistemi operativi precedenti, la disinstallazione di [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.7.1, 4.7, 4.6.2, 4.6.1, 4.6 o 4.5.2 non comporta il ripristino [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] file e la disinstallazione di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] non comporta il ripristino [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] file. Se si vuole tornare alla versione precedente, è necessario reinstallarla con tutti gli aggiornamenti.

## <a name="appendix"></a>Appendice

### <a name="command-line-options"></a>Opzioni della riga di comando
 Nella tabella seguente sono elencate le opzioni che è possibile includere quando si concatena il file ridistribuibile di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] all'installazione dell'applicazione.

|Opzione|Descrizione|
|------------|-----------------|
|**/CEIPConsent**|Sostituisce il comportamento predefinito e invia un commento anonimo a Microsoft al fine di migliorare le future esperienze di distribuzione. È possibile usare questa opzione solo se il programma di installazione richiede il consenso e se l'utente concede l'autorizzazione a inviare commenti anonimi a Microsoft.|
|**/chainingpackage** `packageName`|Specifica il nome dell'eseguibile che esegue il concatenamento. Queste informazioni vengono inviate a Microsoft come commento anonimo per contribuire a migliorare le future esperienze di distribuzione.<br /><br /> Se il nome del pacchetto include spazi, usare le virgolette doppie come delimitatori, ad esempio: **/chainingpackage "Lucerne Publishing"**. Per un esempio di un pacchetto di concatenamento, vedere [Ottenere informazioni sullo stato di avanzamento da un pacchetto di installazione](http://go.microsoft.com/fwlink/?LinkId=181926) in MSDN Library.|
|**/LCID**  `LCID`<br /><br /> dove `LCID` specifica un identificatore delle impostazioni locali (vedere [lingue supportate](#supported-languages)).|Installa il Language Pack specificato da `LCID` e forza la visualizzazione dell'interfaccia utente in tale lingua, a meno che non sia impostata la modalità non interattiva.<br /><br /> Per il programma di installazione Web, questa opzione concatena-installa il Language Pack dal Web. **Nota:** usare questa opzione solo con il programma di installazione Web.|
|**/log** `file` &#124; `folder`|Specifica il percorso del file di log. Il valore predefinito è la cartella temporanea per il processo e il nome del file predefinito è basato sul pacchetto. Se l'estensione del file è TXT, viene prodotto un log in formato testo. Se si specifica un'altra estensione o nessuna estensione, viene creato un log in formato HTML.|
|**/msioptions**|Specifica le opzioni da passare per gli elementi MSI e MSP, ad esempio: `/msioptions "PROPERTY1='Value'"`.|
|**/norestart**|Impedisce il riavvio automatico del programma di installazione. Se si usa questa opzione, l'applicazione di concatenamento deve acquisire il codice restituito e gestire il riavvio (vedere [Recupero di informazioni sullo stato di avanzamento da un pacchetto di installazione](http://go.microsoft.com/fwlink/?LinkId=179606) in MSDN Library).|
|**/passive**|Imposta la modalità passiva. Visualizza la barra di stato per indicare che l'installazione è in corso, ma non presenta prompt o messaggi di errore all'utente. In questa modalità, se concatenato da un programma di installazione, il pacchetto di concatenamento deve gestire [codici restituiti](#return-codes).|
|**/pipe**|Crea un canale di comunicazione per consentire a un pacchetto di concatenamento di ottenere lo stato di avanzamento.|
|**/promptrestart**|Solo modalità passiva, se il programma di installazione richiede un riavvio, viene visualizzato un prompt di richiesta. Questa opzione richiede l'interazione dell'utente se è richiesto un riavvio.|
|**/q**|Imposta la modalità non interattiva.|
|**/repair**|Attiva la funzionalità di ripristino.|
|**/serialdownload**|Forza l'esecuzione dell'installazione solo al termine del download del pacchetto.|
|**/showfinalerror**|Imposta la modalità passiva. Visualizza errori solo se l'installazione non viene completata correttamente. Questa opzione richiede l'interazione dell'utente se l'installazione non viene completata.|
|**/showrmui**|Usata solo con l'opzione **/passive** . Visualizza una finestra di messaggio che richiede agli utenti di chiudere le applicazioni .NET Framework in esecuzione. Questa finestra di messaggio mantiene lo stesso comportamento a prescindere dalla modalità.|
|**/uninstall**|Disinstalla .NET Framework ridistribuibile.|

### <a name="supported-languages"></a>Lingue supportate
Nella tabella seguente sono elencati i Language Pack di .NET Framework disponibili per [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e per le relative versioni intermedie.

|LCID|Lingua (paese/regione)|culture|
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
|1044|Norvegese (Bokmål)|No|
|1045|Polacco|pl|
|1046|Portoghese (Brasile)|pt-BR|
|1049|Russo|ru|
|1053|Svedese|sv|
|1055|Turco|tr|
|2052|Cinese (semplificato)|zh-Hans|
|2070|Portoghese (Portogallo)|pt-PT|
|3082|Spagnolo (Spagna, ordinamento moderno)|es|

## <a name="see-also"></a>Vedere anche
 [Guida alla distribuzione per amministratori](../../../docs/framework/deployment/guide-for-administrators.md)  
 [Requisiti di sistema](../../../docs/framework/get-started/system-requirements.md)  
 [Installare .NET Framework per sviluppatori](../../../docs/framework/install/guide-for-developers.md)  
 [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)  
 [Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5](../../../docs/framework/deployment/reducing-system-restarts.md)  
 [Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)
