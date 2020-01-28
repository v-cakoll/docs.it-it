---
title: Panoramica della sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- code access security [Windows Forms], Windows Forms
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms], about security
- access control [Windows Forms], Windows Forms
ms.assetid: 4810dc9f-ea23-4ce1-8ea1-657f0ff1d820
ms.openlocfilehash: 9010b45383f856079661359fdf82180526d96dde
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734846"
---
# <a name="security-in-windows-forms-overview"></a>Panoramica della sicurezza in Windows Form

Prima del rilascio del .NET Framework, tutto il codice in esecuzione sul computer di un utente aveva gli stessi diritti o le stesse autorizzazioni di accesso alle risorse di un utente del computer. Se ad esempio all'utente era consentito l'accesso al file system o a un database, anche il codice aveva accesso al file system o al database. Anche se ciò può essere accettabile per il codice contenuto negli eseguibili installati esplicitamente dall'utente nel computer locale, non è altrettanto accettabile per quanto riguarda il codice potenzialmente dannoso proveniente da Internet o da una Intranet locale. A questo tipo di codice, infatti, non deve essere consentito l'accesso alle risorse del computer dell'utente senza autorizzazione esplicita.

Il .NET Framework introduce un'infrastruttura denominata sicurezza dall'accesso di codice che consente di distinguere le autorizzazioni, o i diritti, del codice rispetto ai diritti dell'utente. Per impostazione predefinita, il codice proveniente da Internet e dalla Intranet può essere eseguito soltanto in un ambiente parzialmente attendibile. Le applicazioni parzialmente attendibili sono soggette a una serie di restrizioni, ad esempio non possono accedere al disco rigido locale né eseguire codice non gestito. Il .NET Framework controlla le risorse a cui il codice è autorizzato ad accedere in base all'identità del codice: da dove proviene, se dispone di [assembly con nome sicuro](../../standard/assembly/strong-named.md), se è firmato con un certificato e così via.

La tecnologia ClickOnce, che consente di distribuire applicazioni Windows Forms, semplifica lo sviluppo di applicazioni che vengono eseguite in attendibilità parziale, con attendibilità totale o in attendibilità parziale con autorizzazioni elevate. ClickOnce fornisce funzionalità quali l'elevazione delle autorizzazioni e la distribuzione di applicazioni attendibili, in modo che l'applicazione possa richiedere l'attendibilità totale o autorizzazioni elevate dall'utente locale in modo responsabile.

## <a name="understanding-security-in-the-net-framework"></a>Informazioni sulla sicurezza in .NET Framework

La sicurezza dall'accesso di codice consente di assegnare al codice gradi di attendibilità diversi, in base all'origine e ad altri aspetti dell'identità del codice. Per altre informazioni sulle evidenze impiegate da Common Language Runtime per determinare i criteri di sicurezza, vedere [Evidenza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd(v=vs.100)). Questo strumento consente di proteggere i computer dal codice dannoso e il codice attendibile dai tentativi, sia intenzionali che accidentali, di compromissione della sicurezza. La sicurezza dall'accesso di codice assicura inoltre un controllo maggiore sulle azioni che possono essere eseguite dall'applicazione, poiché consente di assegnare a quest'ultima soltanto le autorizzazioni effettivamente necessarie. Questo tipo di sicurezza ha effetto su tutto il codice gestito destinato a Common Language Runtime, anche se tale codice non effettua un'unica verifica delle autorizzazioni di sicurezza per l'accesso di codice. Per ulteriori informazioni sulla sicurezza nella .NET Framework, vedere [concetti principali sulla sicurezza](../../standard/security/key-security-concepts.md) e [nozioni fondamentali sulla sicurezza dall'accesso di codice](../misc/code-access-security-basics.md).

Se l'utente esegue un file eseguibile di Windows Form direttamente da un server Web o una condivisione file, il livello di attendibilità concesso all'applicazione dipende dalla posizione in cui si trova il codice e dal modo in cui è stata avviata. Quando viene eseguita, un'applicazione viene automaticamente valutata e riceve un set di autorizzazioni denominato da Common Language Runtime. Per impostazione predefinita, al codice proveniente dal computer locale viene concesso il set di autorizzazioni Completamente attendibile, al codice proveniente da una rete locale viene concesso il set di autorizzazioni Intranet locale e al codice proveniente da Internet viene concesso il set di autorizzazioni Internet.

> [!NOTE]
> In .NET Framework versione 1,0 Service Pack 1 e Service Pack 2, il gruppo di codice dell'area Internet riceve il set di autorizzazioni Nothing. In tutte le altre versioni del .NET Framework, il gruppo di codice dell'area Internet riceve il set di autorizzazioni Internet.
>
> Le autorizzazioni predefinite concesse in ciascuno di questi insiemi sono elencate nell'argomento [Criteri di sicurezza predefiniti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100)). A seconda delle autorizzazioni ricevute, l'applicazione viene eseguita correttamente o genera un'eccezione di sicurezza.
>
> Molte applicazioni Windows Forms verranno distribuite tramite ClickOnce. Gli strumenti utilizzati per la generazione di una distribuzione ClickOnce hanno impostazioni predefinite di sicurezza diverse da quelle illustrate in precedenza. Per altre informazioni, vedere più avanti.

Poiché i criteri di sicurezza possono essere modificati, è possibile che le autorizzazioni effettive concesse all'applicazione siano diverse dai valori predefiniti. È pertanto possibile che l'applicazione disponga di un'autorizzazione su un computer ma non su un altro.

## <a name="developing-a-more-secure-windows-forms-application"></a>Sviluppo di applicazioni Windows Form più sicure

La sicurezza è importante in tutte le fasi di sviluppo delle applicazioni. Iniziare consultando e seguendo le [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md).

Quindi, decidere se l'applicazione deve essere eseguita in un ambiente completamente attendibile o parzialmente attendibile. L'esecuzione dell'applicazione in un ambiente completamente attendibile rende più semplice l'accesso alle risorse nel computer locale, ma espone l'applicazione e i relativi utenti a rischi di sicurezza maggiori nel caso in cui l'applicazione non sia stata progettata e sviluppata rispettando rigorosamente le linee guida per la generazione di codice sicuro. L'esecuzione dell'applicazione in un ambiente parzialmente attendibile semplifica lo sviluppo di applicazioni sicure e riduce la maggior parte dei rischi, ma richiede una pianificazione più accurata sulle modalità di implementazione di determinate funzionalità.

Se si sceglie di creare un'applicazione parzialmente attendibile, ovvero con set di autorizzazioni Internet o Intranet locale, occorre decidere come l'applicazione deve comportarsi in tale ambiente. In Windows Form sono disponibili modi alternativi più sicuri per implementare le funzionalità in un ambiente parzialmente attendibile. Alcune parti dell'applicazione, ad esempio l'accesso ai dati, possono essere progettate e scritte in modo differente per i due ambienti (parzialmente attendibile e completamente attendibile). Alcune funzionalità di Windows Form, ad esempio Impostazioni applicazione, sono progettate per funzionare in un ambiente parzialmente attendibile. Per altre informazioni, vedere [Panoramica delle impostazioni delle applicazioni](./advanced/application-settings-overview.md).

Se l'applicazione richiede più autorizzazioni rispetto a quelle consentite in un ambiente parzialmente attendibile, ma non la si vuole eseguire in un ambiente completamente attendibile, è possibile eseguire l'applicazione in un ambiente parzialmente attendibile effettuando al tempo stesso l'asserzione soltanto delle autorizzazioni aggiuntive necessarie. Se ad esempio si vuole eseguire l'applicazione in un ambiente parzialmente attendibile ma concedere l'accesso in sola lettura a una directory nel file system dell'utente, è possibile richiedere l'autorizzazione <xref:System.Security.Permissions.FileIOPermission> soltanto per tale directory. Se usato correttamente, questo approccio consente di aumentare le capacità dell'applicazione riducendo al minimo i rischi di sicurezza per gli utenti.

Quando si sviluppa un'applicazione che verrà eseguita in un ambiente parzialmente attendibile, occorre tenere traccia delle autorizzazioni indispensabili all'applicazione e di quelle che potrebbe usare facoltativamente. Quando si conoscono tutte le autorizzazioni, è necessario effettuare una richiesta dichiarativa per le autorizzazioni a livello di applicazione. La richiesta di autorizzazioni informa il .NET Framework tempo di esecuzione sulle autorizzazioni necessarie per l'applicazione e sulle autorizzazioni specifiche. Per altre informazioni sulla richiesta di autorizzazioni, vedere [Richiesta di autorizzazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100)).

Quando si richiedono autorizzazioni facoltative, è necessario gestire le eccezioni di sicurezza che verranno generate nel caso in cui l'applicazione esegua un'azione che richiede autorizzazioni non concesse. La corretta gestione dell'eccezione <xref:System.Security.SecurityException> assicurerà che l'esecuzione dell'applicazione non venga interrotta. L'eccezione può essere usata dall'applicazione per determinare se è necessario disabilitare una funzionalità per l'utente. Un'applicazione, ad esempio, può disabilitare l'opzione di menu **Salva** se l'autorizzazione necessaria non viene concessa.

In alcuni casi, è difficile sapere se è stata effettuata l'asserzione di tutte le autorizzazioni appropriate. È possibile, ad esempio, che una chiamata a metodo che a prima vista potrebbe sembrare innocua, a un certo punto dell'esecuzione richieda l'accesso al file system. Se l'applicazione non viene distribuita con tutte le autorizzazioni necessarie, è possibile che l'esecuzione risulti corretta nel proprio computer ma non dopo la distribuzione. Sia l'SDK .NET Framework 2,0 che Visual Studio 2005 contengono gli strumenti per il calcolo delle autorizzazioni necessarie per un'applicazione, ovvero lo strumento da riga di comando MT. exe e la funzionalità calcola autorizzazioni di Visual Studio, rispettivamente.

Negli argomenti riportati di seguito vengono illustrate le funzionalità di sicurezza aggiuntive di Windows Form.

|Argomento|Descrizione|
|-----------|-----------------|
|- [File e accesso ai dati più sicuri in Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)|Viene descritto come accedere ai file e ai dati in un ambiente parzialmente attendibile.|
|- [Stampa più sicura in Windows Forms](more-secure-printing-in-windows-forms.md)|Viene descritto come accedere alle funzionalità di stampa in un ambiente parzialmente attendibile.|
|- [Considerazioni aggiuntive sulla sicurezza in Windows Forms](additional-security-considerations-in-windows-forms.md)|Viene descritto come modificare le finestre, mediante gli Appunti, ed eseguire chiamate al codice non gestito in un ambiente parzialmente attendibile.|

### <a name="deploying-an-application-with-the-appropriate-permissions"></a>Distribuzione di un'applicazione con le autorizzazioni appropriate

Il modo più comune per distribuire un Windows Forms Application a un computer client è con ClickOnce, una tecnologia di distribuzione che descrive tutti i componenti che devono essere eseguiti dall'applicazione. ClickOnce usa file XML denominati manifesti per descrivere gli assembly e i file che costituiscono l'applicazione, nonché le autorizzazioni richieste dall'applicazione.

ClickOnce dispone di due tecnologie per la richiesta di autorizzazioni elevate in un computer client. entrambe basate sull'uso di certificati Authenticode. L'uso dei certificati fornisce una discreta garanzia agli utenti che l'applicazione proviene da una fonte attendibile.

Queste tecnologie sono descritte nella tabella seguente.

|Tecnologia per autorizzazioni elevate|Descrizione|
|------------------------------------|-----------------|
|Elevazione delle autorizzazioni|La prima volta che si esegue l'applicazione, viene visualizzata all'utente una finestra di dialogo di sicurezza di **elevazione delle autorizzazioni** in cui vengono fornite alcune informazioni sull'editore dell'applicazione, in modo che l'utente possa prendere una decisione consapevole sull'assegnazione di altre autorizzazioni all'applicazione.|
|Distribuzione di applicazioni attendibili|Questa tecnologia richiede che un amministratore di sistema esegua, una sola volta, l'installazione del certificato Authenticode di un'entità di pubblicazione in un computer client. Da quel momento in poi, le eventuali applicazioni firmate con il certificato verranno considerate attendibili e potranno essere eseguite con attendibilità totale nel computer locale senza che venga visualizzata alcuna richiesta all'utente.|

La tecnologia più adatta dipenderà dallo specifico ambiente di distribuzione. Per altre informazioni, vedere [Scelta di una strategia di distribuzione ClickOnce](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy).

Per impostazione predefinita, le applicazioni ClickOnce distribuite tramite Visual Studio o gli strumenti SDK .NET Framework (Mage. exe e MageUI. exe) sono configurate per l'esecuzione in un computer client con attendibilità totale. Se si vuole distribuire l'applicazione in un ambiente parzialmente attendibile o assegnando soltanto alcune autorizzazioni aggiuntive, sarà necessario modificare le impostazioni predefinite. Questa operazione può essere eseguita con Visual Studio o lo strumento SDK .NET Framework MageUI. exe quando si configura la distribuzione. Per ulteriori informazioni su come utilizzare MageUI. exe, vedere [procedura dettagliata: distribuzione manuale di un'applicazione ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  Per altre informazioni su come impostare le autorizzazioni per una zona personalizzata, vedere [Procedura: impostare le autorizzazioni personalizzate per un'applicazione ClickOnce](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hafybdaa(v=vs.110)) o [Procedura: impostare le autorizzazioni personalizzate per un'applicazione ClickOnce](/visualstudio/deployment/how-to-set-custom-permissions-for-a-clickonce-application).

Per ulteriori informazioni sugli aspetti di sicurezza di ClickOnce e sull'elevazione delle autorizzazioni, vedere [protezione di applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications). Per altre informazioni sulla distribuzione di applicazioni attendibili, vedere [Panoramica della distribuzione di applicazioni attendibili](/visualstudio/deployment/trusted-application-deployment-overview).

### <a name="testing-the-application"></a>Verifica dell'applicazione

Se la Windows Forms Application è stata distribuita usando Visual Studio, è possibile abilitare il debug in attendibilità parziale o un set di autorizzazioni limitato dall'ambiente di sviluppo.  Vedere anche [procedura: eseguire il debug di un'applicazione ClickOnce con autorizzazioni limitate](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions).

## <a name="see-also"></a>Vedere anche

- [Sicurezza di Windows Form](windows-forms-security.md)
- [Nozioni fondamentali sulla sicurezza per l’accesso al codice](../misc/code-access-security-basics.md)
- [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Panoramica della distribuzione di applicazioni attendibili](/visualstudio/deployment/trusted-application-deployment-overview)
- [Mage.exe (Strumento per la generazione e la modifica di manifesti)](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [MageUI.exe (Strumento per la generazione e la modifica di manifesti, client grafico)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
