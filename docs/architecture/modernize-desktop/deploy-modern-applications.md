---
title: Distribuzione di applicazioni desktop moderne
description: Tutto ciò che occorre sapere sulla distribuzione di moderne applicazioni desktop.
ms.date: 05/12/2020
ms.openlocfilehash: 4a4d93caf1c2f8f58d48ee3199bbe6983fa939f4
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83423257"
---
# <a name="deploying-modern-desktop-applications"></a>Distribuzione di applicazioni desktop moderne

Quando si sviluppano applicazioni desktop, una cosa da considerare è il modo in cui l'applicazione verrà assemblata e distribuita nei computer degli utenti. Il problema con la creazione di pacchetti, la distribuzione e l'installazione è che in genere rientra nell'ambito dei professionisti IT, che si occupano di cose diverse dagli sviluppatori.

In questi giorni, si ha familiarità con il concetto di DevOps, in cui gli sviluppatori e i professionisti IT lavorano strettamente per spostare le applicazioni negli ambienti di produzione. Tuttavia, se la battaglia sul desktop è stata completata da più di 10 anni, è possibile che si sia visto la storia seguente. Un team di sviluppatori collabora duramente per soddisfare le scadenze del progetto. Le persone aziendali sono nervose perché richiedono che il sistema lavori su più computer dell'utente per eseguire l'azienda. In "D-Day", il project manager controlla con tutti gli sviluppatori che il codice funziona correttamente e che tutto è corretto, quindi è possibile spedire. Il team del pacchetto genera quindi la configurazione per l'app, la distribuisce a ogni computer utente e un set di utenti di test eseguono l'applicazione. Ebbene, tentano, perché prima di visualizzare un'interfaccia utente, l'applicazione genera un'eccezione che indica che il metodo ~ dell'oggetto ~ non è riuscito. Panico inizia a scorrere in aria e una breve indagine punta a uno sviluppatore giovane e stanco che ha introdotto un controllo di terze parti, che certamente "ha funzionato nel computer di sviluppo".

L'installazione di applicazioni desktop è stata tradizionalmente un incubo per due motivi principali:

- Mancanza di una stretta cultura di collaborazione tra sviluppatori e team IT.
- Mancanza di una solida tecnologia di creazione di pacchetti e distribuzione su cui è possibile basarsi.

In realtà, abbiamo vissuto il fatto che a volte ci dispiace che l'installazione di un'app sia stata completata perché:

- Si verificano alcuni effetti collaterali indesiderati nel computer.
- Alcune applicazioni installate in precedenza smettono di funzionare.

Inoltre, non è possibile ripristinare solo lo stato originale del sistema disinstallando l'app. Siamo abituati a vivere questa situazione e abbiamo coniato termini come "DLL Hell" o "Winrot".

In questo capitolo parleremo di MSIX. MSIX è la tecnologia nuovissima di Microsoft che tenta di acquisire il meglio delle tecnologie precedenti per offrire una solida base per la tecnologia di creazione dei pacchetti del futuro.

Che cosa deve fare una tecnologia di creazione di pacchetti con la modernizzazione? Ebbene, risulta che la creazione di pacchetti è fondamentale per l'IT aziendale con molti investimenti. La modernizzazione non riguarda solo l'utilizzo delle tecnologie più recenti. È anche correlato alla riduzione del time-to-Market dal momento in cui viene definito un requisito aziendale fino a quando l'azienda non recapita la funzionalità al client.

## <a name="the-modern-application-lifecycle"></a>Il ciclo di vita dell'applicazione moderna

Oggi gli sviluppatori scrivono e compilano il codice per un'app e quindi passano le risorse generate ai professionisti IT. Quindi, i professionisti IT riconfigurano l'app e la riassemblano, in genere in un file MSI o più di recente in un formato di creazione di pacchetti di App-V. L'app viene quindi distribuita tramite canali e strumenti diversi. Uno dei principali problemi di questo approccio è comunemente noto come "paralisi del packaging". Il problema è che il ciclo si ripete ogni volta che è presente un aggiornamento dell'app o un aggiornamento del sistema operativo.

È possibile vedere il processo riflesso nell'immagine seguente:

![Diagramma che mostra il ciclo di vita IT moderno](./media/deploy-modern-applications/modern-it-application-lifecycle.png)

Le aziende hanno bisogno di un modo per suddividere il ciclo di pacchetti in tre cicli indipendenti:

- Aggiornamenti del sistema operativo
- Aggiornamenti dell'applicazione
- Personalizzazione

![Diagramma che mostra il ciclo virtuoso IT moderno](./media/deploy-modern-applications/modern-it-virtuous-cycle.png)

Il diagramma precedente mostra che è possibile:

- Aggiornare il sistema operativo sottostante senza dover riassemblare le app.
- Abilitare le personalizzazioni senza dover riassemblare il pacchetto per sviluppatori originale.

Questa modifica radicale ci porta al ciclo di vita IT nuovo e moderno, come illustrato nell'immagine seguente:

![Diagramma che mostra il ciclo di vita dell'applicazione tramite strumenti Microsoft](./media/deploy-modern-applications/microsoft-it-tools.png)

Gli sviluppatori creano l'app e generano un pacchetto MSIX che i professionisti IT possono utilizzare e configurare senza la necessità di ricreare la confezione. Insieme alla tecnologia MSIX, Microsoft ha creato strumenti che consentono di personalizzare e configurare i pacchetti senza riassemblarli.

## <a name="msix-the-next-generation-of-deployment"></a>MSIX: la prossima generazione della distribuzione

Prima di MSIX, erano disponibili diverse tecnologie di creazione dei pacchetti, ad esempio installazione guidata, MSI, ClickOnce, App-V e scripting. Ognuna di queste tecnologie ha i propri punti di forza e Microsoft ha deciso di scegliere il meglio per creare MSIX. MSIX è basato sulle fondamenta di queste tecnologie esistenti, selezionando il meglio di ognuno:

- App-V = \> contenitori
- ClickOnce = \> aggiornamento automatico
- MSI = \> facile da distribuire

Con MSIX è possibile ottenere una tecnologia di installazione con tutte queste funzionalità.

![Diagramma che mostra le diverse tecnologie che hanno influito sulla compilazione di MSIX](./media/deploy-modern-applications/msix.png)

### <a name="benefits-of-msix"></a>Vantaggi di MSIX

#### <a name="never-regret-installing-an-app"></a>Non rimpiangere mai l'installazione di un'app

MSIX fornisce una distribuzione prevedibile, affidabile e sicura. Il metodo dichiarativo contenuto nel manifesto del pacchetto consente al sistema operativo di tenere traccia di tutte le risorse necessarie per l'applicazione. Fornisce inoltre una vera disinstallazione pulita senza effetti collaterali.

#### <a name="disk-space-optimization"></a>Ottimizzazione dello spazio su disco

MSIX è ottimizzato per ridurre il footprint di un'applicazione sullo spazio su disco del computer dell'utente. Crea una singola istanza di archiviazione dei file. Ovvero, se si dispone di due pacchetti diversi con la stessa DLL, la DLL non viene installata due volte. La piattaforma si occupa di questo problema perché conosce tutti i file installati da una determinata app grazie alla sua natura dichiarativa. Consente inoltre di avere diverse versioni di una DLL che funzionano side-by-side.

Con l'uso di pacchetti di risorse, è possibile creare facilmente app multilingue e il sistema operativo si occupa dell'installazione di quelli usati.

#### <a name="network-optimization"></a>Ottimizzazione della rete

MSIX rileva le differenze nei file a livello di blocco di byte abilitando una funzionalità denominata aggiornamenti differenziali. Ciò significa che solo i blocchi di byte aggiornati vengono scaricati negli aggiornamenti dell'applicazione.

![Diagramma che illustra come MSIX gestisce gli aggiornamenti differenziali](./media/deploy-modern-applications/msix-managing-updates.png)

Con l'installazione del flusso, l'utente può iniziare rapidamente a lavorare sull'applicazione mentre altre parti dell'app vengono scaricate in background. Questa funzionalità contribuisce a un'esperienza accattivante per gli utenti.

Con la funzionalità pacchetti facoltativi, si ottiene la componentizzazione della distribuzione dell'app, in modo che sia possibile scaricarli quando necessario.

#### <a name="simple-packaging-and-deployment"></a>Creazione di pacchetti e distribuzione semplici

Il AppManifest dichiara il controllo delle versioni, la destinazione del dispositivo e l'identificazione in modo standard per ogni applicazione. Fornisce inoltre un modo per firmare gli asset offrendo una solida base di sicurezza.

#### <a name="os-managed"></a>Gestito dal sistema operativo

Il sistema operativo gestisce tutti i processi per l'installazione, l'aggiornamento e la rimozione di un'applicazione. Le applicazioni vengono installate per utente ma scaricate solo una volta, riducendo al minimo il footprint del disco. Microsoft sta lavorando per fornire l'esperienza MSIX anche in Windows 7.

#### <a name="windows-provides-integrity-for-the-app"></a>Windows garantisce l'integrità per l'app

Con l'uso di firme digitali, è possibile garantire che non si installi un'applicazione da origini non attendibili. MSIX impedisce inoltre la manomissione perché:

- Mantiene un record degli hash dei file.
- Rileva se un file è stato modificato dopo l'installazione.

#### <a name="works-for-the-entire-app-catalog"></a>Funziona per l'intero catalogo di app

Uno degli aspetti più interessanti di MSIX è che funziona per l'intero Catalogo applicazioni, Windows Forms, WPF, MFC/ATL, Delphi, anche se si vuole eseguire la distribuzione xCopy, ClickOnce o passare allo Store, è possibile usare lo stesso pacchetto MSIX.

### <a name="tools"></a>Strumenti

#### <a name="windows-application-packaging-project"></a>Progetto di creazione pacchetti di applicazione Windows

Per generare un pacchetto per l'applicazione desktop, è possibile usare il progetto di progetto di creazione di **pacchetti di applicazioni Windows**   in Visual Studio. Quindi, è possibile pubblicare il pacchetto nel Microsoft Store o sideload in uno o più PC.

#### <a name="msix-packaging-tool"></a>MSIX Packaging Tool

MSIX Packaging Tool ti consente di ricreare il pacchetto delle applicazioni Win32 esistenti in formato MSIX. Offre un'interfaccia utente interattiva e una riga di comando per le conversioni e consente di convertire un'applicazione senza il codice sorgente.

![MSIX Packaging Tool](./media/deploy-modern-applications/msix-packaging-tool.png)

#### <a name="package-support-framework"></a>PSF (Package Support Framework)

Il Framework di supporto pacchetti è un kit open source che consente di applicare correzioni all'applicazione Win32 esistente quando non si ha accesso al codice sorgente, in modo che possa essere eseguito in un contenitore MSIX. PSF consente di seguire le procedure consigliate degli ambienti di runtime moderni per le app.

#### <a name="app-installer"></a>Programma di installazione app

Il programma di installazione delle app consente di installare le app di Windows 10 facendo doppio clic sul pacchetto dell'app. Ciò significa che non è necessario che gli utenti usino PowerShell o altri strumenti di sviluppo per distribuire le app di Windows 10. Il programma di installazione dell'app può anche installare un'app dal Web, dai pacchetti facoltativi e dai set correlati.

## <a name="how-to-create-an-msix-package-from-an-existing-win32-desktop-application"></a>Come creare un pacchetto MSIX da un'applicazione desktop Win32 esistente

Esaminiamo la procedura per creare un pacchetto MSIX da un'applicazione Win32 esistente. In questo esempio si userà un'app Windows Forms.

Per iniziare, aggiungere un nuovo progetto alla soluzione, selezionare il progetto di creazione pacchetti di applicazioni Windows e assegnargli un nome.

![Aggiunta di un nuovo progetto di creazione pacchetti di applicazioni Windows](./media/deploy-modern-applications/add-packaging-project.png)

Si noterà la struttura del progetto di creazione del pacchetto e si nota una cartella speciale denominata *Applications*. All'interno di questa cartella è possibile specificare le applicazioni che si desidera includere nel pacchetto. Può essere più di uno.

![Struttura del progetto di creazione pacchetto](./media/deploy-modern-applications/packaging-project.png)

Fare clic con il pulsante destro del mouse sulla cartella *applicazioni* e selezionare il progetto Windows Forms che si vuole creare il pacchetto dalla soluzione Visual Studio.

![Aggiunta del progetto Windows Forms al progetto di creazione pacchetto](./media/deploy-modern-applications/add-winforms-project.png)

A questo punto, è possibile compilare e generare il pacchetto, ma esaminiamo un paio di cose. Per migliorare l'esperienza utente, Visual Studio è in grado di generare automaticamente tutte le risorse visive necessarie per un'applicazione moderna per gestire le icone e le risorse dei riquadri per la barra dei riquadri e il menu Start. Aprire il file *Package. appxmanifest* per accedere alla finestra di progettazione del manifesto. È quindi possibile generare tutti gli asset visivi da una determinata immagine presente nel progetto semplicemente facendo clic su **Crea**.

![Screenshot della finestra di progettazione del manifesto in Visual Studio](./media/deploy-modern-applications/manifest-designer.png)

Se si apre il codice per il file *Package. appxmanifest* , è possibile vedere un paio di aspetti interessanti.

A destra `<Package>` , c'è un `<Identity>` nodo. Questo è il punto in cui l'applicazione in pacchetto otterrà la propria identità, che verrà gestita dal sistema operativo.

![Nodo Identity](./media/deploy-modern-applications/identity-node.png)

Nel `<Capabilities>` nodo è possibile trovare tutti i requisiti necessari per l'applicazione, prestare particolare attenzione a `<rescap:Capability Name="runFullTrust" \>` , che indica al sistema operativo di eseguire l'app in modalità di attendibilità totale poiché si tratta di un'applicazione Win32.

![Nodo funzionalità](./media/deploy-modern-applications/capabilities-node.png)

Impostare il progetto di creazione pacchetto come progetto di avvio per la soluzione e selezionare *Esegui*. Questa operazione sarà:

- Compilare il Windows Forms Application.
- Creare un pacchetto MSIX dai risultati della compilazione.
- Distribuire i pacchetti.
- Installarlo localmente nel computer di sviluppo.
- Avviare l'app.

![Applicazione installata](./media/deploy-modern-applications/our-installed-application.png)

In questo modo si dispone dell'esperienza di installazione e disinstallazione pulita che MSIX fornisce completamente integrato in Windows 10.

La fase finale riguarda il modo in cui si distribuisce il pacchetto MSIX in un altro computer.

Fare clic con il pulsante destro del mouse sul progetto di creazione pacchetto, scegliere il menu **Store** , quindi selezionare l'opzione **Crea pacchetti dell'applicazione** .

Quindi, è possibile scegliere tra la creazione di un pacchetto da caricare nell'archivio o la creazione di pacchetti per sideload. Nella maggior parte degli scenari di modernizzazione, si sceglierà **di voler creare pacchetti per sideload**.

![Configurazione dei pacchetti](./media/deploy-modern-applications/configuring-packages.png)

Qui è possibile selezionare le diverse architetture di destinazione, in quanto è possibile includere il numero desiderato nello stesso pacchetto di MSIX.

Il passaggio finale consiste nel dichiarare la posizione in cui si desidera distribuire gli asset di installazione finali.

![Configurare le impostazioni di aggiornamento](./media/deploy-modern-applications/configure-update-settings.png)

È possibile scegliere di usare un server Web di un percorso UNC condiviso nei file server aziendali. Prestare attenzione alle impostazioni per specificare come si vuole aggiornare l'applicazione. Verranno illustrati gli aggiornamenti dell'applicazione nella sezione successiva.

Per una guida dettagliata, vedere creare [un pacchetto di un'app desktop dal codice sorgente con Visual Studio](/windows/msix/desktop/desktop-to-uwp-packaging-dot-net).

## <a name="auto-updates-in-msix"></a>Aggiornamenti automatici in MSIX

Windows Store offre un meccanismo di aggiornamento straordinario con Windows Update. Nella maggior parte degli scenari aziendali, non si usa lo Store per distribuire le app desktop. Quindi, è necessario un modo simile per configurare gli aggiornamenti per l'applicazione ed eseguirne il pull agli utenti.

Grazie a una combinazione di funzionalità di Windows 10 e di pacchetti MSIX, è possibile offrire agli utenti un'esperienza di aggiornamento ottimale. In realtà, l'utente non deve necessariamente essere tecnico, ma è comunque vantaggioso da un'esperienza di aggiornamento di applicazioni senza problemi.

È possibile configurare gli aggiornamenti per interagire con l'utente in due modi diversi:

- Aggiornamenti richiesti dall'utente: il sistema operativo Mostra un'interfaccia utente di Nizza generata automaticamente per notificare all'utente che l'applicazione sta per essere installata. Questa interfaccia utente viene compilata in base alle proprietà specificate nei file di installazione.

- Aggiornamenti invisibile all'utente in background. Con questa opzione, gli utenti non devono essere a conoscenza degli aggiornamenti.

È inoltre possibile configurare quando si desidera eseguire gli aggiornamenti quando l'applicazione viene avviata o a intervalli regolari. Grazie alle funzionalità di caricamento laterale, è anche possibile ottenere questi aggiornamenti mentre l'applicazione è in esecuzione.

Quando si usa questo tipo di distribuzione, viene creato un file speciale denominato *. AppInstaller*. Il file semplice contiene le sezioni seguenti:

- Percorso del file con *estensione AppInstaller*
- Proprietà principali del pacchetto MSIX dell'applicazione
- Comportamento dell'aggiornamento

![file con estensione AppInstaller](./media/deploy-modern-applications/appinstaller-file.png)

In combinazione con questo file, Microsoft ha progettato un protocollo URL speciale per avviare il processo di installazione da un collegamento:

```xml
<a href="ms-appinstaller:?source=http://mywebservice.azureedge.net/MyApp.msix">Install app package </a>
```

Questo protocollo funziona su tutti i browser e avvia il processo di installazione con una grande esperienza utente in Windows 10. Poiché il sistema operativo gestisce il processo di installazione, è a conoscenza del percorso da cui è stata installata l'applicazione e tiene traccia di tutti i file interessati dal processo.

MSIX crea un'interfaccia utente per l'installazione che mostra automaticamente alcune proprietà del pacchetto. Ciò consente un'esperienza di installazione comune per ogni app.

Dopo aver generato il nuovo pacchetto MSIX e averlo spostato sul server di distribuzione, è sufficiente modificare il file con *estensione AppInstaller* per riflettere queste modifiche, soprattutto la versione e il percorso del nuovo file MSIX. Al successivo avvio dell'applicazione da parte dell'utente, il sistema rileverà la modifica e scaricherà i file per la nuova versione in background. Al termine, l'installazione verrà eseguita all'avvio di una nuova applicazione in modo trasparente per l'utente.

>[!div class="step-by-step"]
>[Indietro](example-migration-core.md)
