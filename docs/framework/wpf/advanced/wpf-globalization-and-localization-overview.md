---
title: Panoramica sulla globalizzazione e localizzazione
description: Informazioni sulla localizzazione e la globalizzazione per Windows Presentation Foundation, inclusi il layout automatico, gli assembly satellite e gli attributi localizzati.
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 9a54ce2c265b989f99383ff9cdec961c80dd655c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168287"
---
# <a name="wpf-globalization-and-localization-overview"></a>Panoramica della globalizzazione e localizzazione WPF

Quando si limita la disponibilità del prodotto a una sola lingua, si limitano le potenziali basi clienti a una frazione della popolazione 7,5 miliardi del mondo. Se si vuole che le applicazioni raggiungano un pubblico globale, la localizzazione economica del prodotto è uno dei modi migliori e più economici per raggiungere un ampio pubblico di clienti.

Questa panoramica introduce la globalizzazione e la localizzazione in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . La globalizzazione si basa sulla progettazione e sviluppo di applicazioni eseguibili in più posizioni. Ad esempio, la globalizzazione supporta interfacce utente e dati internazionali localizzati per utenti in varie impostazioni cultura. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce funzionalità di progettazione globalizzate, tra cui layout automatico, assembly satellite e attributi localizzati e commenti.

La localizzazione consiste nella conversione delle risorse dell'applicazione in versioni localizzate per specifiche impostazioni cultura supportate dall'applicazione. Quando si localizza in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , si usano le API nello <xref:System.Windows.Markup.Localizer> spazio dei nomi. Queste API potenziano lo strumento da riga di comando di [esempio per lo strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml) . Per informazioni su come compilare e usare LocBaml, vedere [localizzare un'applicazione](how-to-localize-an-application.md).

## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Procedure consigliate per la globalizzazione e la localizzazione in WPF

È possibile sfruttare al meglio le funzionalità di globalizzazione e localizzazione integrate in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguendo i suggerimenti relativi alla progettazione dell'interfaccia utente e alla localizzazione forniti da questa sezione.

### <a name="best-practices-for-wpf-ui-design"></a>Procedure consigliate per la progettazione dell'interfaccia utente WPF

Quando si progetta una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basata su [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , è consigliabile implementare le procedure consigliate seguenti:

- Scrivere il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . evitare di creare nel codice. Quando si crea [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , questo viene esposto tramite le API di localizzazione predefinite.

- Evitare di usare posizioni assolute e dimensioni fisse per il layout del contenuto; usare invece il ridimensionamento relativo o automatico.

  - Utilizzare <xref:System.Windows.Window.SizeToContent%2A> e gestire larghezze e altezze impostate su `Auto` .

  - Evitare <xref:System.Windows.Controls.Canvas> di utilizzare per il layout di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .

  - Usare <xref:System.Windows.Controls.Grid> e la relativa funzionalità di condivisione delle dimensioni.

- Lasciare uno spazio aggiuntivo ai margini perché il testo localizzato spesso richiede più spazio. Lo spazio aggiuntivo servirà per eventuali caratteri sporgenti.

- Abilitare <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> on <xref:System.Windows.Controls.TextBlock> per evitare il ritaglio.

- Impostare l'attributo `xml:lang` . Questo attributo descrive le impostazioni cultura di un elemento specifico e dei relativi elementi figlio. Il valore di questa proprietà modifica il comportamento di diverse funzionalità in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Ad esempio, cambia il comportamento della sillabazione, del controllo ortografico, della sostituzione dei numeri, della definizione di lingue con alfabeto non latino e del fallback dei tipi di carattere. Per ulteriori informazioni sull'impostazione della [gestione di XML: lang in XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md), vedere [globalizzazione per WPF](globalization-for-wpf.md) .

- Creare un tipo di carattere composito personalizzato per ottenere un controllo migliore sui tipi di carattere usati per lingue diverse. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Usa il tipo di carattere carattere GlobalUserInterface. composite nella directory Windows\Fonts..

- Quando si creano applicazioni di navigazione che possono essere localizzate in impostazioni cultura che presentano testo in un formato da destra a sinistra, impostare in modo esplicito l'oggetto <xref:System.Windows.FlowDirection> di ogni pagina per assicurarsi che la pagina non erediti <xref:System.Windows.FlowDirection> da <xref:System.Windows.Navigation.NavigationWindow> .

- Quando si creano applicazioni di navigazione autonome ospitate all'esterno di un browser, impostare l'oggetto <xref:System.Windows.Application.StartupUri%2A> per l'applicazione iniziale su un <xref:System.Windows.Navigation.NavigationWindow> anziché su una pagina (ad esempio, `<Application StartupUri="NavigationWindow.xaml">` ). Questa progettazione consente di modificare il <xref:System.Windows.FlowDirection> della finestra e la barra di spostamento. Per ulteriori informazioni e un esempio, vedere [esempio di globalizzazione della Home page](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

### <a name="best-practices-for-wpf-localization"></a>Procedure consigliate per la localizzazione di WPF

Quando si localizzano [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni basate su, è consigliabile implementare le procedure consigliate seguenti:

- Usare i commenti di localizzazione per fornire un contesto aggiuntivo per i localizzatori.

- Usare gli attributi di localizzazione per controllare la localizzazione anziché omettere selettivamente le <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà sugli elementi. Per ulteriori informazioni, vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md) .

- Usare `msbuild -t:updateuid` e `-t:checkuid` per aggiungere e controllare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà nell' [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Usare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà per tenere traccia delle modifiche tra sviluppo e localizzazione. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>le proprietà consentono di localizzare nuove modifiche di sviluppo. Se si aggiungono manualmente <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà a un oggetto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , l'attività è in genere noiosa e meno accurata.

  - Non modificare o modificare le <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà dopo l'avvio della localizzazione.

  - Non usare proprietà duplicate <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> . tenere presente questo suggerimento quando si usa il comando copia e incolla.

  - Impostare il `UltimateResourceFallback` percorso in AssemblyInfo. \* per specificare la lingua appropriata per il fallback (ad esempio, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]` ).

    Se si decide di includere la lingua di origine nell'assembly principale omettendo il `<UICulture>` tag nel file di progetto, impostare il `UltimateResourceFallback` percorso come assembly principale anziché come satellite (ad esempio, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]` ).

## <a name="localize-a-wpf-application"></a>Localizzare un'applicazione WPF

Quando si localizza un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione, sono disponibili diverse opzioni. Ad esempio, è possibile associare le risorse localizzabili nell'applicazione a un file XML, archiviare il testo localizzabile nelle tabelle RESX o fare in modo che il localizzatore usi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] i file. Questa sezione descrive un flusso di lavoro di localizzazione che usa il modulo BAML di XAML, che offre diversi vantaggi:

- È possibile localizzare dopo la compilazione.

- È possibile eseguire l'aggiornamento a una versione più recente del modulo BAML di XAML con le localizzazioni da una versione precedente del modulo BAML di XAML in modo che sia possibile localizzare nello stesso momento in cui si sviluppa.

- È possibile convalidare gli elementi di origine e la semantica in fase di compilazione perché il modulo BAML di XAML è la forma compilata di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

### <a name="localization-build-process"></a>Processo di compilazione per la localizzazione

Quando si sviluppa un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione, il processo di compilazione per la localizzazione è il seguente:

- Lo sviluppatore crea e globalizza l' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione. Nel file di progetto lo sviluppatore imposta in `<UICulture>en-US</UICulture>` modo che, quando l'applicazione viene compilata, venga generato un assembly principale indipendente dalla lingua. Questo assembly dispone di un file satellite con estensione resources.dll che contiene tutte le risorse localizzabili. Facoltativamente, è possibile mantenere la lingua di origine nell'assembly principale perché le API di localizzazione supportano l'estrazione dall'assembly principale.

- Quando il file viene compilato nella compilazione, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene convertito nel formato BAML di XAML. I file culturalmente indipendenti `MyDialog.exe` e dipendenti dalla lingua inglese `MyDialog.resources.dll` vengono rilasciati ai clienti di lingua inglese.

### <a name="localization-workflow"></a>Flusso di lavoro della localizzazione

Il processo di localizzazione inizia dopo la compilazione del file non localizzato `MyDialog.resources.dll` . Gli [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi e le proprietà nell'originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono estratti dal form BAML di XAML in coppie chiave-valore usando le API in <xref:System.Windows.Markup.Localizer> . I localizzatori usano le coppie chiave-valore per localizzare l'applicazione. È possibile generare un nuovo file con estensione resource.dll a partire dai nuovi valori dopo che la localizzazione è stata completata.

Le chiavi delle coppie chiave-valore sono `x:Uid` valori posizionati dallo sviluppatore nella versione originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Questi `x:Uid` valori consentono all'API di rilevare e unire le modifiche che si verificano tra lo sviluppatore e il localizzatore durante la localizzazione. Se, ad esempio, lo sviluppatore modifica l'oggetto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dopo che il localizzatore inizia a localizzare, è possibile unire la modifica allo sviluppo con il lavoro di localizzazione già completato in modo da perdere il lavoro di traduzione minima.

La figura seguente mostra un tipico flusso di lavoro di localizzazione basato sul modulo BAML di XAML. Questo diagramma presuppone che lo sviluppatore scriva l'applicazione in lingua inglese. Lo sviluppatore crea e globalizza l'applicazione WPF. Nel file di progetto lo sviluppatore imposta in `<UICulture>en-US</UICulture>` modo che, durante la compilazione, un assembly principale indipendente dalla lingua venga generato con un .resources.dll satellite contenente tutte le risorse localizzabili. In alternativa, è possibile mantenere la lingua di origine nell'assembly principale poiché le API di localizzazione WPF supportano l'estrazione dall'assembly principale. Dopo il processo di compilazione, il codice XAML viene compilato in BAML. Il file MyDialog.exe.resources.dll indipendente dalla lingua viene distribuito ai clienti di lingua inglese.

![Diagramma che illustra il flusso di lavoro di localizzazione.](./media/wpf-globalization-and-localization-overview/localization-workflow.png)

![Diagramma che illustra il flusso di lavoro non localizzato.](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)

## <a name="examples-of-wpf-localization"></a>Esempi di localizzazione WPF

Questa sezione contiene esempi di applicazioni localizzate che consentono di comprendere come compilare e localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni.

### <a name="run-dialog-box-example"></a>Esempio di finestra di dialogo Esegui

La grafica seguente mostra l'output dell'esempio di finestra di dialogo **Esegui** .

**Inglese:**

![Screenshot che mostra una finestra di dialogo di esecuzione in lingua inglese.](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)

**Tedesco:**

![Screenshot che mostra una finestra di dialogo esecuzione tedesca.](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)

**Progettazione di una finestra di dialogo Esegui globale**

Questo esempio genera una finestra di dialogo **Esegui** utilizzando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Questa finestra di dialogo è equivalente alla finestra di dialogo **Esegui** disponibile nel menu Start di Microsoft Windows.

Alcune delle caratteristiche principali delle finestre di dialogo globali sono:

**Layout automatico**

*In Window1.xaml:*

`<Window SizeToContent="WidthAndHeight">`

La proprietà Window precedente ridimensiona automaticamente la finestra in base alle dimensioni del contenuto. Questa proprietà impedisce alla finestra di troncare il contenuto che aumenta di dimensioni dopo la localizzazione. Rimuove anche lo spazio superfluo quando le dimensioni del contenuto si riducono dopo la localizzazione.

`<Grid x:Uid="Grid_1">`

<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>le proprietà sono necessarie per consentire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corretto funzionamento delle API di localizzazione.

Vengono utilizzate dalle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API di localizzazione per tenere traccia delle modifiche tra lo sviluppo e la localizzazione del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>le proprietà consentono di unire una versione più recente di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con una localizzazione precedente di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . È possibile aggiungere una <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà eseguendo `msbuild -t:updateuid RunDialog.csproj` in una shell dei comandi. Questo è il metodo consigliato per aggiungere <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà perché l'aggiunta manuale è in genere dispendiosa in termini di tempo e meno accurata. È possibile verificare che le <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà siano impostate correttamente eseguendo `msbuild -t:checkuid RunDialog.csproj` .

[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]È strutturato tramite il <xref:System.Windows.Controls.Grid> controllo, che è un controllo utile per sfruttare il layout automatico in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Si noti che la finestra di dialogo è suddivisa in tre righe e cinque colonne. Una delle definizioni di riga e colonna ha dimensioni fisse; gli [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi posizionati in ogni cella possono pertanto adattarsi a aumenti e riduzioni delle dimensioni durante la localizzazione.

[!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]

Le prime due colonne in cui l'etichetta **Open:** e <xref:System.Windows.Controls.ComboBox> vengono posizionate utilizzano il 10% della [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] larghezza totale.

[!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]

Si noti che nell'esempio viene utilizzata la funzionalità di dimensionamento condiviso di <xref:System.Windows.Controls.Grid> . Le ultime tre colonne sfruttano questa impostazione inserendo se stessi nello stesso <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> . Come si evince dal nome della proprietà, in questo modo le colonne possono condividere le stesse dimensioni. Quindi, quando "Sfoglia..." viene localizzato nella stringa più lunga "durchsuchen...", tutti i pulsanti crescono in larghezza anziché avere un piccolo pulsante "OK" e un "durchsuchen..." molto grande. pulsante.

**XML: lang**

`xml:lang="en-US"`

Si noti la [gestione di XML: lang in XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md) posizionata in corrispondenza dell'elemento radice dell'oggetto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Questa proprietà descrive le impostazioni cultura di un determinato elemento e dei relativi elementi figlio. Questo valore viene utilizzato da diverse funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e deve essere modificato in modo appropriato durante la localizzazione. Questo valore cambia il dizionario in lingua usato per la sillabazione e il controllo ortografico delle parole. Influisce anche sulla visualizzazione delle cifre e sulla selezione del tipo di carattere da usare da parte del sistema di fallback dei tipi di carattere. Infine, la proprietà influisce sulla visualizzazione dei numeri e sulla forma dei testi scritti in lingue con alfabeti non latini. Il valore predefinito è "en-US".

**Creazione di un assembly di risorse satellite**

*Nel file con estensione csproj:*

Modificare il `.csproj` file e aggiungere il tag seguente a un valore non condizionale `<PropertyGroup>` :

`<UICulture>en-US</UICulture>`

Si noti l'aggiunta di un `UICulture` valore. Quando questa impostazione è impostata su un <xref:System.Globalization.CultureInfo> valore valido, ad esempio en-US, la compilazione del progetto genererà un assembly satellite con tutte le risorse localizzabili al suo interno.

`<Resource Include="RunIcon.JPG">`

`<Localizable>False</Localizable>`

`</Resource>`

Non `RunIcon.JPG` è necessario localizzare l'oggetto perché dovrebbe apparire lo stesso per tutte le impostazioni cultura. `Localizable`è impostato su `false` in modo che rimanga nell'assembly principale indipendente dalla lingua anziché nell'assembly satellite. Il valore predefinito di tutte le risorse non compilabili è `Localizable` impostato su `true` .

**Localizzazione della finestra di dialogo Esegui**

**Parse**.

Dopo aver compilato l'applicazione, il primo passaggio della localizzazione consiste nell'analizzare le risorse localizzabili nell'assembly satellite. Ai fini di questo argomento, usare lo strumento LocBaml di esempio, disponibile nell'esempio di [strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml). Si noti che LocBaml è solo uno strumento di esempio che permette di iniziare a creare uno strumento di localizzazione adatto al processo di localizzazione. Utilizzando LocBaml, eseguire il comando seguente per analizzare: **LocBaml/parse RunDialog.resources.dll/out:** per generare un file "RunDialog.resources.dll.CSV".

**Localize**

Usare un editor CSV che supporta la codifica Unicode per modificare il file. Escludere tutte le voci con categoria di localizzazione "Nessuna". Dovrebbero essere visualizzate le voci seguenti:

|Chiave di risorsa|Categoria di localizzazione|Valore|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Pulsante|OK|
|Button_2:System.Windows.Controls.Button.$Content|Pulsante|Annulla|
|Button_3:System.Windows.Controls.Button.$Content|Pulsante|Sfoglia...|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|Digitare il nome del programma, della cartella, del documento o della risorsa Internet da aprire.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Testo|Aperto:|
|Window_1:System.Windows.Window.Title|Titolo|Esegui|

La localizzazione dell'applicazione in tedesco richiede le seguenti traduzioni:

|Chiave di risorsa|Categoria di localizzazione|Valore|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Pulsante|OK|
|Button_2:System.Windows.Controls.Button.$Content|Pulsante|Abbrechen|
|Button_3:System.Windows.Controls.Button.$Content|Pulsante|Durchsuchen…|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|Geben Sie den Namen eines programmes, Ordners, Dokuments oder einer Internetresource an.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Testo|Apri:|
|Window_1:System.Windows.Window.Title|Titolo|Esegui|

**Generate**

L'ultimo passaggio della localizzazione implica la creazione dell'assembly satellite appena localizzato. Per questa operazione usare il comando LocBaml seguente:

**LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**

Nelle finestre tedesche, se questa resources.dll viene posizionata in una cartella de-DE accanto all'assembly principale, questa risorsa viene caricata automaticamente anziché quella nella cartella en-US. Se non si dispone di una versione tedesca di Windows per testarla, impostare le impostazioni cultura per le impostazioni cultura di Windows in uso (ad esempio, `en-US` ) e sostituire la dll di risorse originali.

**Caricamento di risorse satellite**

|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|
|------------------|------------------------------------|------------------------------------|
|Codice|BAML inglese originale|BAML localizzato|
|Risorse indipendenti dalle impostazioni cultura|Altre risorse in inglese|Altre risorse localizzate in tedesco|

.NET sceglie automaticamente l'assembly di risorse satellite da caricare in base all'applicazione <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> . Per impostazione predefinita, vengono utilizzate le impostazioni cultura del sistema operativo Windows. Se si usano le finestre tedesche, il file *de-DE\MyDialog.resources.dll* viene caricato. Se si usa Windows per la lingua inglese, il file *en-US\MyDialog.resources.dll* viene caricato. È possibile impostare la risorsa di fallback finale per l'applicazione specificando l' `NeutralResourcesLanguage` attributo nel file *AssemblyInfo* del progetto. Ad esempio, se si specifica:

`[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`

il file di *en-US\MyDialog.resources.dll* viene quindi utilizzato con le finestre tedesche se non sono disponibili nessuno dei seguenti file: *de-DE\MyDialog.resources.dll* o *de\MyDialog.resources.dll*.

### <a name="microsoft-saudi-arabia-homepage"></a>Home page Microsoft per l'Arabia Saudita

Le immagini seguenti mostrano una home page in inglese e in arabo. Per l'esempio completo che produce questi elementi grafici, vedere [esempio di globalizzazione della Home page](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

**Inglese:**

![Screenshot che mostra un home page in lingua inglese.](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)

**Arabo:**

![Screenshot che mostra un home page arabo.](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)

### <a name="designing-a-global-microsoft-home-page"></a>Progettazione di un home page Microsoft globale

Questo modello di sito Web Microsoft per l'Arabia Saudita illustra le funzionalità di globalizzazione disponibili per le lingue da destra a sinistra. Lingue quali l'ebraico e l'arabo hanno un ordine di lettura da destra a sinistra in modo che il layout di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] debba spesso essere disposto in modo molto diverso rispetto a quello delle lingue da sinistra a destra, ad esempio l'inglese. La localizzazione da una lingua da sinistra a destra in una lingua da destra a sinistra o viceversa può risultare piuttosto complessa. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è stato progettato per semplificare tali processi di localizzazione.

**FlowDirection**

*Homepage.xaml:*

[!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]

Si noti la <xref:System.Windows.FrameworkElement.FlowDirection%2A> Proprietà in <xref:System.Windows.Controls.Page> . Se si modifica questa proprietà in, il valore <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FrameworkElement.FlowDirection%2A> di <xref:System.Windows.Controls.Page> e i relativi elementi figlio verranno modificati in modo che il layout di questo oggetto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] venga capovolto per diventare da destra a sinistra come previsto da un utente arabo. È possibile eseguire l'override del comportamento di ereditarietà specificando un oggetto esplicito <xref:System.Windows.FrameworkElement.FlowDirection%2A> su qualsiasi elemento. La <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà è disponibile in qualsiasi <xref:System.Windows.FrameworkElement> elemento correlato a o Document e ha un valore implicito pari a <xref:System.Windows.FlowDirection.LeftToRight> .

Osservare che anche i pennelli sfumatura di sfondo vengono capovolti correttamente quando <xref:System.Windows.FrameworkElement.FlowDirection%2A> viene modificata la radice:

**FlowDirection="LeftToRight"**

![Screenshot che mostra il flusso sfumato da sinistra a destra.](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)

**FlowDirection="RightToLeft"**

![Screenshot che mostra il flusso sfumato da destra a sinistra.](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)

**Evitare l'utilizzo di dimensioni fisse per riquadri e controlli**

Esaminare Homepage. XAML. si noti che, a parte la larghezza fissa e l'altezza specificate per l'intero [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nella parte superiore <xref:System.Windows.Controls.DockPanel> , non sono presenti altre dimensioni fisse. Se si usano dimensioni fisse, è possibile che il testo localizzato risulti più lungo rispetto al testo di origine e debba essere ritagliato. I pannelli e i controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verranno automaticamente ridimensionati in base al contenuto. La maggior parte dei controlli dispone anche di dimensioni minime e massime che è possibile impostare per un maggiore controllo (ad esempio, MinWidth = "20"). Con <xref:System.Windows.Controls.Grid> è anche possibile impostare larghezze e altezze relative usando ' \* ' (ad esempio, `Width="0.25*"` ) o usare la funzionalità di condivisione delle dimensioni della cella.

**Commenti di localizzazione**

In molti casi il contenuto può risultare ambiguo e difficile da tradurre. Lo sviluppatore o il progettista ha la possibilità di fornire ai localizzatori contesto aggiuntivo e commenti tramite i commenti di localizzazione. Ad esempio, la localizzazione. i commenti seguenti chiariscono l'uso del carattere ' &#124;'.

[!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]

Questo commento viene associato al contenuto di TextBlock_1 e, nel caso dello strumento LocBaml (vedere [localizzare un'applicazione](how-to-localize-an-application.md)), può essere visualizzato nella sesta colonna della TextBlock_1 riga nel file output. csv:

|Chiave di risorsa|Category|Leggibile|Modificabile|Comment|Valore|
|-|-|-|-|-|-|
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|TRUE|TRUE|Questo carattere viene usato come regola decorativa.|&#124;|

I commenti possono essere inseriti nel contenuto o nella proprietà di qualsiasi elemento usando la sintassi seguente:

[!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]

**Attributi di localizzazione**

Spesso lo sviluppatore o il responsabile della localizzazione deve avere il controllo su tutto ciò che i localizzatori possono leggere e modificare. Ad esempio, il localizzatore non deve tradurre il nome della società o modificare alcuni termini legali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce attributi che consentono di impostare la leggibilità, la modificabilità e la categoria del contenuto o della proprietà di un elemento che lo strumento di localizzazione può utilizzare per bloccare, nascondere o ordinare gli elementi. Per altre informazioni, vedere <xref:System.Windows.Localization.Attributes%2A>. Ai fini di questo esempio, lo strumento LocBaml restituisce solo i valori di questi attributi. I controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno tutti i valori predefiniti per questi attributi, ma è possibile eseguirne l'override. Nell'esempio seguente, ad esempio, viene eseguito l'override degli attributi di localizzazione predefiniti per `TextBlock_1` e il contenuto viene impostato come leggibile ma non modificabile per i localizzatori.

[!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]

Oltre agli attributi di leggibilità e modificabilità, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un'enumerazione delle categorie comuni dell'interfaccia utente ( <xref:System.Windows.LocalizationCategory> ) che possono essere usate per offrire ai localizzatori un contesto più contestuale. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]È anche possibile eseguire l'override delle categorie predefinite per i controlli della piattaforma [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] :

[!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]

Gli attributi di localizzazione predefiniti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] forniti da possono anche essere sottoposti a override tramite codice, pertanto è possibile impostare correttamente i valori predefiniti corretti per i controlli personalizzati. Ad esempio:

```csharp
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]
public class CorporateLogo : TextBlock
{
    // ...
}
```

Gli attributi per istanza impostati in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] avranno la precedenza sui valori impostati nel codice nei controlli personalizzati. Per altre informazioni sugli attributi e i commenti, vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).

**Fallback dei tipi di carattere e tipi di carattere compositi**

Se si specifica un tipo di carattere che non supporta un intervallo di punti di codebase specificato, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verrà automaticamente utilizzato il fallback a uno che esegue mediante l'interfaccia utente globale. compositefont che si trova nella directory Windows\Fonts. I tipi di carattere compositi funzionano esattamente come qualsiasi altro tipo di carattere e possono essere usati in modo esplicito impostando un elemento `FontFamily` (ad esempio, `FontFamily="Global User Interface"` ). Per specificare le preferenze di fallback del tipo di carattere, è possibile creare un tipo di carattere composito personalizzato e specificare il tipo di carattere da usare per gli specifici intervalli di punti di codice e le lingue.

Per ulteriori informazioni sui tipi di carattere compositi <xref:System.Windows.Media.FontFamily> , vedere.

**Localizzazione della home page Microsoft**

È possibile seguire la stessa procedura usata nell'esempio della finestra di dialogo Esegui per localizzare l'applicazione. Il file CSV localizzato per l'arabo è disponibile nell'esempio della [Home page di globalizzazione](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).
