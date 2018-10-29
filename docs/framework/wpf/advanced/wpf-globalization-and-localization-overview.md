---
title: Panoramica della globalizzazione e localizzazione WPF
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: e9a9e9295425efaadff4ac1f0b796b2c9a889543
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200953"
---
# <a name="wpf-globalization-and-localization-overview"></a>Panoramica della globalizzazione e localizzazione WPF

Quando si limita la disponibilità del prodotto a una sola lingua, si riduce la potenziale base clienti a una frazione della popolazione mondiale di 6,5 miliardi di persone. Se si vuole che le applicazioni raggiungano un pubblico globale, la localizzazione economica del prodotto è uno dei modi migliori e più economici per raggiungere un ampio pubblico di clienti.  
  
 Questa panoramica vengono presentati globalizzazione e localizzazione in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. La globalizzazione si basa sulla progettazione e sviluppo di applicazioni eseguibili in più posizioni. Ad esempio, la globalizzazione supporta interfacce utente e dati internazionali localizzati per utenti in varie impostazioni cultura. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce funzionalità di progettazione globalizzate, tra cui layout automatico e gli assembly satellite localizzato degli attributi e commenti.
  
 La localizzazione consiste nella conversione delle risorse dell'applicazione in versioni localizzate per specifiche impostazioni cultura supportate dall'applicazione. Se si localizza in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], si usano le API nel <xref:System.Windows.Markup.Localizer> dello spazio dei nomi. Il risparmio API il [esempio dello strumento LocBaml](https://go.microsoft.com/fwlink/?LinkID=160016) lo strumento da riga di comando. Per informazioni su come creare e usare LocBaml, vedere [localizzare un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).
  
## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Procedure consigliate per la globalizzazione e la localizzazione in WPF

 È possibile sfruttare al meglio le funzionalità di globalizzazione e localizzazione incorporato in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguendo le istruzioni di progettazione dell'interfaccia utente e suggerimenti relativi alla localizzazione forniti in questa sezione.  
  
### <a name="best-practices-for-wpf-ui-design"></a>Procedure consigliate per la progettazione dell'interfaccia utente WPF

 Quando si progetta una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basato [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], si consiglia di implementare le procedure consigliate:  
  
-   Scrivere le [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; evitare di creare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel codice. Quando si crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] tramite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], si espone tramite le API di localizzazione predefinite.  
  
-   Evitare di usare posizioni assolute e dimensioni fisse per preparare il contenuto. Usare invece il ridimensionamento automatico o relativo.
  
    -   Uso <xref:System.Windows.Window.SizeToContent%2A> e mantenere le larghezze e altezze impostate su `Auto`.  
  
    -   Evitare di usare <xref:System.Windows.Controls.Canvas> per definire il layout [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s.  
  
    -   Usare <xref:System.Windows.Controls.Grid> e la funzionalità di condivisione delle dimensioni.  
  
-   Lasciare uno spazio aggiuntivo ai margini perché il testo localizzato spesso richiede più spazio. Lo spazio aggiuntivo servirà per eventuali caratteri sporgenti.  
  
-   Abilitare <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> su <xref:System.Windows.Controls.TextBlock> per evitare di ritaglio.
  
-   Impostare l'attributo `xml:lang` . Questo attributo descrive le impostazioni cultura di un elemento specifico e i relativi elementi figlio. Il valore di questa proprietà viene modificato il comportamento di diverse funzionalità in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ad esempio, cambia il comportamento della sillabazione, del controllo ortografico, della sostituzione dei numeri, della definizione di lingue con alfabeto non latino e del fallback dei tipi di carattere. Vedere [globalizzazione per WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md) per altre informazioni sull'impostazione il [XML: lang in XAML gestisce](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md).  
  
-   Creare un tipo di carattere composito personalizzato per ottenere maggiore controllo dei tipi di carattere utilizzati per le diverse lingue. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza il tipo di carattere GlobalUserInterface. composite nella directory Windows\Fonts.  
  
-   Quando si creano applicazioni di navigazione che possono essere localizzate in una lingua che presenta il testo in un formato di destra a sinistra, impostare in modo esplicito il <xref:System.Windows.FlowDirection> di ogni pagina per verificare che la pagina non erediti <xref:System.Windows.FlowDirection> dal <xref:System.Windows.Navigation.NavigationWindow>.  
  
-   Quando si creano applicazioni di navigazione autonome ospitate all'esterno di un browser, impostare il <xref:System.Windows.Application.StartupUri%2A> per l'applicazione iniziale su una <xref:System.Windows.Navigation.NavigationWindow> anziché a una pagina (ad esempio, `<Application StartupUri="NavigationWindow.xaml">`). Questa progettazione consente di modificare il <xref:System.Windows.FlowDirection> della finestra e la barra di spostamento. Per altre informazioni e un esempio, vedere [esempio della home page di globalizzazione](https://go.microsoft.com/fwlink/?LinkID=159990).  
  
### <a name="best-practices-for-wpf-localization"></a>Procedure consigliate per la localizzazione di WPF

 Quando si localizzano [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: le applicazioni basate su, è consigliabile implementare le procedure consigliate:  
  
-   Usare i commenti di localizzazione per offrire maggior contesto ai localizzatori.  
  
-   Usare gli attributi di localizzazione per controllare la localizzazione anziché omettere in maniera selettiva <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> sulle proprietà degli elementi. Visualizzare [commenti e gli attributi di localizzazione](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md) per altre informazioni.  
  
-   Uso `msbuild -t:updateuid` e `-t:checkuid` per aggiungere e verificare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> delle proprietà nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Usare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà per rilevare le modifiche tra sviluppo e la localizzazione. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà consentono di localizzare nuove modifiche di sviluppo. Se si aggiunge manualmente <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> delle proprietà per un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], l'attività è in genere lunga e meno accurata.  
  
    -   Non modificare o cambiare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà dopo aver iniziato la localizzazione.  
  
    -   Non usare duplicato <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà (Ricordarsi questo suggerimento quando si usa il comando copia e Incolla).  
  
    -   Impostare il `UltimateResourceFallback` posizione nel file AssemblyInfo. * per specificare la lingua appropriata per il fallback (ad esempio, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`).  
  
         Se si decide di includere la lingua di origine nell'assembly principale omettendo il `<UICulture>` tag nel file di progetto, impostare il `UltimateResourceFallback` percorso dell'assembly principale anziché satellite (ad esempio, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`).  
  
## <a name="localize-a-wpf-application"></a>Localizzare un'applicazione WPF

Se si localizza una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'applicazione, sono disponibili diverse opzioni. Ad esempio, è possibile associare le risorse localizzabili nell'applicazione per un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] file, archiviare il testo localizzabile in tabelle resx o che il localizzatore usi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file. Questa sezione descrive un flusso di lavoro di localizzazione che usa il modulo BAML di XAML, che offre diversi vantaggi:  
  
-   È possibile localizzare dopo la compilazione.  
  
-   È possibile eseguire l'aggiornamento a una versione più recente del modulo BAML di XAML con localizzazioni da una versione precedente del modulo BAML di XAML in modo da poter localizzare contemporaneamente allo sviluppo.  
  
-   È possibile convalidare originale gli elementi di origine e la semantica in fase di compilazione, perché il modulo BAML di XAML corrisponde al modulo compilato di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
### <a name="localization-build-process"></a>Processo di compilazione per la localizzazione  

Quando si sviluppa un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione, il processo di compilazione per la localizzazione è il seguente:  
  
-   Lo sviluppatore crea e globalizza il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. Nel file di progetto lo sviluppatore imposta `<UICulture>en-US</UICulture>` in modo che quando viene compilata l'applicazione, viene generato un assembly principale indipendente dalla lingua. Questo assembly dispone di un file satellite con estensione resources.dll che contiene tutte le risorse localizzabili. Facoltativamente, è possibile mantenere la lingua di origine nell'assembly principale poiché la localizzazione [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] supportano l'estrazione dall'assembly principale.  
  
-   Quando il file viene compilato nella build, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene convertito nel modulo BAML di XAML. Indipendente dalla lingua `MyDialog.exe` e il dipendente dalla lingua (in inglese) `MyDialog.resources.dll` i file vengono distribuiti ai clienti di lingua inglese.  
  
### <a name="localization-workflow"></a>Flusso di lavoro della localizzazione

Il processo di localizzazione inizia dopo la non localizzato `MyDialog.resources.dll` generazione del file. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi e proprietà in originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono estratti dal modulo BAML di XAML in coppie chiave-valore tramite il [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] sotto <xref:System.Windows.Markup.Localizer>. I localizzatori usano le coppie chiave-valore per localizzare l'applicazione. È possibile generare un nuovo file con estensione resource.dll a partire dai nuovi valori dopo che la localizzazione è stata completata.
  
 Le chiavi delle coppie chiave-valore sono `x:Uid` i valori che vengono inseriti dallo sviluppatore nell'originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Questi `x:Uid` abilitare i valori di [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] di rilevare e unire le modifiche apportate dallo sviluppatore e dal localizzatore durante la localizzazione. Ad esempio, se lo sviluppatore modifica il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dopo che il localizzatore ha iniziato la localizzazione, è possibile unire le modifiche di sviluppo con il lavoro di localizzazione già completato in modo che lavoro minimo traduzione viene perso.  
  
 La figura seguente mostra un tipico flusso di lavoro di localizzazione basato sul modulo BAML di XAML. Questo diagramma si presuppone che lo sviluppatore scriva l'applicazione in lingua inglese. Lo sviluppatore crea e globalizza l'applicazione WPF. Nel file di progetto lo sviluppatore imposta `<UICulture>en-US</UICulture>` in modo che in fase di compilazione, venga generato un assembly principale indipendente dalla lingua con un satellite. Resources contenente tutte le risorse localizzabili. In alternativa, è possibile mantenere la lingua di origine nell'assembly principale poiché le API di localizzazione WPF supportano l'estrazione dall'assembly principale. Dopo il processo di compilazione, il codice XAML viene compilato in BAML. Il file MyDialog.exe.resources.dll indipendente dalla lingua viene distribuito ai clienti di lingua inglese.  
  
 ![Flusso di lavoro di localizzazione](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![Flusso di lavoro non localizzato](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
## <a name="examples-of-wpf-localization"></a>Esempi di localizzazione WPF

 Questa sezione contiene esempi di applicazioni localizzate che illustrano come compilare e localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni.  
  
#### <a name="run-dialog-box-example"></a>Esempio di finestra di dialogo Esegui

 L'immagine seguente mostra l'output del **eseguire** esempio di finestra di dialogo.  
  
 **Inglese:**  
  
 ![Finestra di dialogo Esegui in inglese](../../../../docs/framework/wpf/advanced/media/rundialogenglish.PNG "RunDialogEnglish")  
  
 **Tedesco:**  
  
 ![Finestra di dialogo Esegui in tedesco](../../../../docs/framework/wpf/advanced/media/rundialoggerman.PNG "RunDialogGerman")  
  
 **Progettazione di una finestra di dialogo Esegui globale**  
  
 Questo esempio produce un **eseguiti** finestra di dialogo utilizzando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È equivalente a questa finestra di dialogo il **eseguiti** finestra di dialogo che è disponibile il [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] menu Start.  
  
 Alcune delle caratteristiche principali delle finestre di dialogo globali sono:  
  
 **Layout automatico**  
  
 *In Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 La proprietà Window precedente ridimensiona automaticamente la finestra in base alle dimensioni del contenuto. Questa proprietà impedisce alla finestra di troncare il contenuto che aumenta di dimensioni dopo la localizzazione. Rimuove anche lo spazio superfluo quando le dimensioni del contenuto si riducono dopo la localizzazione.  
  
 `<Grid x:Uid="Grid_1">`  
  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà sono necessarie affinché [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzazione [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] a funzionare correttamente.  
  
 Vengono usati da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzazione [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] tenere traccia delle modifiche tra lo sviluppo e la localizzazione del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà consentono di unire una versione più recente di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con una precedente localizzazione del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Si aggiunge un <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà eseguendo `msbuild -t:updateuid RunDialog.csproj` in una shell dei comandi. Questo è il metodo consigliato per aggiungere <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà perché aggiunta manuale risulta in genere molto dispendiosa e meno accurata. È possibile controllare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà siano impostate correttamente eseguendo `msbuild -t:checkuid RunDialog.csproj`.
  
 Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è strutturata mediante il <xref:System.Windows.Controls.Grid> controllo, che rappresenta un controllo utile per sfruttare il layout automatico in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Si noti che la finestra di dialogo è suddivisa in tre righe e cinque colonne. Non è una delle definizioni di riga e colonna ha una dimensione fissa; di conseguenza, il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] gli elementi che si trovano in ogni cella possono adattarsi ad aumenti e riduzioni delle dimensioni durante la localizzazione.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Le prime due colonne in cui il **aperto:** etichetta e <xref:System.Windows.Controls.ComboBox> vengono inserite usano il 10% del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] larghezza totale.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Si noti che l'esempio Usa la funzionalità di ridimensionamento condiviso di <xref:System.Windows.Controls.Grid>. Le ultime tre colonne sfruttano questo inserendo stessi nello stesso <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>. Come si evince dal nome della proprietà, in questo modo le colonne possono condividere le stesse dimensioni. Pertanto, quando la "Sfoglia..." viene localizzato nella stringa più lunga "Durchsuchen...", tutti i pulsanti aumenta in larghezza invece di avere un piccolo pulsante "OK" e un pulsante "Durchsuchen..." estremamente grande.  
  
 **Xml:lang**
  
 `Xml:lang="en-US"`  
  
 Si noti che il [XML: lang gestisce in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) posizionato in corrispondenza dell'elemento radice del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Questa proprietà descrive le impostazioni cultura di un determinato elemento e dei relativi elementi figlio. Questo valore viene usato da diverse funzionalità in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e deve essere modificata in modo appropriato durante la localizzazione. Questo valore cambia il dizionario in lingua usato per la sillabazione e il controllo ortografico delle parole. Influisce anche sulla visualizzazione delle cifre e sulla selezione del tipo di carattere da usare da parte del sistema di fallback dei tipi di carattere. Infine, la proprietà influisce sulla visualizzazione dei numeri e sulla forma dei testi scritti in lingue con alfabeti non latini. Il valore predefinito è "en-US".  
  
 **Creazione di un assembly di risorse satellite**  
  
 *Nel file con estensione csproj:*  

 Modificare il `.csproj` file e aggiungere il seguente tag a un incondizionale `<PropertyGroup>`:
 
 `<UICulture>en-US</UICulture>`  
  
 Si noti l'aggiunta di un `UICulture` valore. Quando è impostato su un valore valido <xref:System.Globalization.CultureInfo> valore, ad esempio en-US, compilare il progetto verrà generato un assembly satellite contenente tutte le risorse localizzabili in esso.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 Il `RunIcon.JPG` non dovrà essere localizzato poiché viene visualizzato lo stesso per tutte le impostazioni cultura. `Localizable` è impostato su `false` in modo che rimanga nell'assembly principale indipendente dalla lingua anziché nell'assembly satellite. È il valore predefinito di tutte le risorse non compilabili `Localizable` impostato su `true`.  
  
 **Localizzazione della finestra di dialogo Esegui**  
  
 **Analisi**  
  
 Dopo aver compilato l'applicazione, il primo passaggio della localizzazione consiste nell'analizzare le risorse localizzabili nell'assembly satellite. Ai fini di questo argomento, usare lo strumento LocBaml esempio reperibili [esempio dello strumento LocBaml](https://go.microsoft.com/fwlink/?LinkID=160016). Si noti che LocBaml è solo uno strumento di esempio che permette di iniziare a creare uno strumento di localizzazione adatto al processo di localizzazione. Utilizzo dello strumento LocBaml, eseguire il comando seguente per analizzare: **LocBaml/analizzare /Parse /out:** per generare un file "RunDialog".  
  
 **Localizzazione**  
  
 Usare un editor CSV che supporta la codifica Unicode per modificare il file. Escludere tutte le voci con categoria di localizzazione "Nessuna". Dovrebbero essere visualizzate le voci seguenti:  
  
|Chiave di risorsa|Categoria di localizzazione|Valore|  
|-|-|-| 
|Button_1:System.Windows.Controls.Button.$Content|Button|OK|  
|Button_2:System.Windows.Controls.Button.$Content|Button|Annulla|  
|Button_3:System.Windows.Controls.Button.$Content|Button|Sfoglia...|  
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|Digitare il nome del programma, della cartella, del documento o della risorsa Internet da aprire.|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Testo|Apri:|  
|Window_1:System.Windows.Window.Title|Titolo|Esegui|  
  
 La localizzazione dell'applicazione in tedesco richiede le seguenti traduzioni:  
  
|Chiave di risorsa|Categoria di localizzazione|Valore|  
|-|-|-| 
|Button_1:System.Windows.Controls.Button.$Content|Button|OK|  
|Button_2:System.Windows.Controls.Button.$Content|Pulsante|Abbrechen|  
|Button_3:System.Windows.Controls.Button.$Content|Button|Durchsuchen…|  
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|Geben Sie den Namen eines Programms, Ordners, dell'ordine Dokuments einer Internetresource una.|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Testo|Öffnen:|  
|Window_1:System.Windows.Window.Title|Titolo|Esegui|  
  
 **Generazione**  
  
 L'ultimo passaggio della localizzazione implica la creazione dell'assembly satellite appena localizzato. Per questa operazione usare il comando LocBaml seguente:  
  
 **LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**  
  
 Nella versione tedesca [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], se questo file resources. dll viene posizionato in una cartella de-DE accanto all'assembly principale, questa risorsa verrà caricata automaticamente anziché quella nella cartella en-US. Se non è una versione tedesca di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] per verificare questo comportamento, configurare le impostazioni cultura e utilizzare le impostazioni di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] in uso (ad esempio, `en-US`) e sostituire le DLL di risorse originale.  
  
 **Caricamento di risorse satellite**  
  
|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Codice|BAML inglese originale|BAML localizzato|  
|Risorse indipendenti dalle impostazioni cultura|Altre risorse in inglese|Altre risorse localizzate in tedesco|  
  
 .NET framework sceglie automaticamente l'assembly di risorse satellite da caricare in base all'applicazione `Thread.CurrentThread.CurrentUICulture`. Il valore predefinito è la lingua del [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] sistema operativo. Pertanto, se si usa tedesco [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], viene caricata la de-DE\MyDialog.resources.dll, se si usa inglese [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], en-US\MyDialog.resources.dll carica. Per impostare la risorsa di fallback finale per l'applicazione, specificare NeutralResourcesLanguage nel file AssemblyInfo.* del progetto. Ad esempio se si specifica:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 verrà utilizzato en-US\MyDialog.resources.dll con la versione tedesca di Windows se non sono disponibili de-DE\MyDialog.resources.dll o de\MyDialog.resources.dll.  
  
### <a name="microsoft-saudi-arabia-homepage"></a>Home page Microsoft per l'Arabia Saudita  
 Le immagini seguenti mostrano una home page in inglese e in arabo. Per l'esempio completo che produce queste immagini, vedere [esempio della home page di globalizzazione](https://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Inglese:**  
  
 ![Pagina inglese](../../../../docs/framework/wpf/advanced/media/englishhomepage.jpg "EnglishHomepage")  
  
 **Arabo:**  
  
 ![Pagina in arabo](../../../../docs/framework/wpf/advanced/media/arabichomepage.jpg "ArabicHomepage")  
  
### <a name="designing-a-global-microsoft-homepage"></a>Progettazione di una home page Microsoft globale  
 Questo modello di sito Web Microsoft per l'Arabia Saudita illustra le funzionalità di globalizzazione disponibili per le lingue da destra a sinistra. Lingue quali l'ebraico e arabo hanno un ordine di lettura da destra a sinistra, pertanto il layout di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] spesso deve essere disposto in modo molto diverso rispetto a come sarebbe nelle lingue da sinistra a destra, ad esempio inglese. La localizzazione da una lingua da sinistra a destra in una lingua da destra a sinistra o viceversa può risultare piuttosto complessa. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è stato progettato per semplificare tali processi di localizzazione.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xaml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Si noti che il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà <xref:System.Windows.Controls.Page>. La modifica di questa proprietà su <xref:System.Windows.FlowDirection.RightToLeft> cambierà il <xref:System.Windows.FrameworkElement.FlowDirection%2A> del <xref:System.Windows.Controls.Page> e i relativi elementi figlio in modo che il layout di questo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] venga capovolto per diventare da destra a sinistra, come si aspetterebbe un utente arabo. Per eseguire l'override del comportamento di ereditarietà specificando esplicita <xref:System.Windows.FrameworkElement.FlowDirection%2A> su qualsiasi elemento. Il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà è disponibile in qualsiasi <xref:System.Windows.FrameworkElement> o elemento correlato al documento e ha un valore implicito di <xref:System.Windows.FlowDirection.LeftToRight>.  
  
 Osservare che anche i pennelli sfumatura dello sfondo vengono invertiti correttamente al quando radice <xref:System.Windows.FrameworkElement.FlowDirection%2A> viene modificato:  
  
 **FlowDirection="LeftToRight"**  
  
 ![Flusso da sinistra a destra](../../../../docs/framework/wpf/advanced/media/lefttoright.PNG "LeftToRight")  
  
 **FlowDirection="RightToLeft"**  
  
 ![Flusso da destra a sinistra](../../../../docs/framework/wpf/advanced/media/righttoleft.PNG "RightToLeft")  
  
 **Evitare l'utilizzo di dimensioni fisse per riquadri e controlli**  
  
 Dare un'occhiata a HomePage. XAML, si noti che, a parte fissi di larghezza e altezza specificati per l'intera [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in alto <xref:System.Windows.Controls.DockPanel>, non sono presenti altre dimensioni fisse. Se si usano dimensioni fisse, è possibile che il testo localizzato risulti più lungo rispetto al testo di origine e debba essere ritagliato. I pannelli e i controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verranno automaticamente ridimensionati in base al contenuto. La maggior parte dei controlli dispone anche di dimensioni minime e massime che è possibile impostare per un maggiore controllo (ad esempio MinWidth = "20"). Con <xref:System.Windows.Controls.Grid>, è anche possibile impostare larghezze e altezze relative tramite '\*' (ad esempio, `Width="0.25*"`) o usare le dimensioni della cella funzionalità di condivisione.  
  
 **Commenti di localizzazione**  
  
 In molti casi il contenuto può risultare ambiguo e difficile da tradurre. Lo sviluppatore o il progettista ha la possibilità di fornire ai localizzatori contesto aggiuntivo e commenti tramite i commenti di localizzazione. Ad esempio l'oggetto Localization.Comments seguente chiarisce l'utilizzo del carattere '&#124;'.  
  
 [!code-xaml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Questo commento viene associato al contenuto di TextBlock_1 e, nel caso dello strumento LocBaml (vedere [localizzare un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)), può essere visualizzato nella colonna 6 della riga TextBlock_1 nel file con estensione csv di output:  
  
|Chiave di risorsa|Category|Leggibile|Modificabile|Commento|Valore|  
|-|-|-|-|-|-|  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|true|true|Questo carattere viene usato come regola decorativa.|&#124;|  
  
 I commenti possono essere inseriti nel contenuto o nella proprietà di qualsiasi elemento usando la sintassi seguente:  
  
 [!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Attributi di localizzazione**  
  
 Spesso lo sviluppatore o il responsabile della localizzazione deve avere il controllo su tutto ciò che i localizzatori possono leggere e modificare. Ad esempio, il localizzatore non deve tradurre il nome della società o modificare alcuni termini legali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone di attributi che consentono di impostare la leggibilità, modificabilità e la categoria del contenuto o delle proprietà di un elemento e che possono essere usati dallo strumento di localizzazione per bloccare, nascondere o ordinare gli elementi. Per altre informazioni, vedere <xref:System.Windows.Localization.Attributes%2A>. Ai fini di questo esempio, lo strumento LocBaml restituisce solo i valori di questi attributi. I controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno tutti i valori predefiniti per questi attributi, ma è possibile eseguirne l'override. Ad esempio, nell'esempio seguente esegue l'override gli attributi di localizzazione predefiniti per `TextBlock_1` e imposta il contenuto sia leggibile ma non modificabile per i localizzatori.  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 Oltre a attributi di leggibilità e modificabilità, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un'enumerazione di categorie comuni dell'interfaccia utente (<xref:System.Windows.LocalizationCategory>) che può essere utilizzato per fornire ai localizzatori maggiore contesto. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] categorie predefinite per i controlli della piattaforma possono essere sostituite in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anche:  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Gli attributi di localizzazione predefiniti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce può anche essere sottoposto a override tramite codice, pertanto è possibile impostare correttamente i valori predefiniti appropriati per i controlli personalizzati. Ad esempio:  

```csharp 
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)] 
public class CorporateLogo : TextBlock
{
    // ...
}
``` 
 
 Di attributi per istanza impostati [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] avrà la precedenza sui valori impostati nel codice sui controlli personalizzati. Per altre informazioni sugli attributi e commenti, vedere [commenti e gli attributi di localizzazione](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
 **Fallback dei tipi di carattere e tipi di carattere compositi**  
  
 Se si specifica un tipo di carattere che non supporta un intervallo di punti di codice specificato, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eseguirà automaticamente il fallback a uno che esegue utilizzando il Global User Interface. compositefont che si trova nella directory Windows\Fonts. Tipi di carattere compositi lavorare come qualsiasi altro tipo di carattere e può essere usati in modo esplicito tramite l'impostazione di un elemento `FontFamily` (ad esempio, `FontFamily="Global User Interface"`). Per specificare le preferenze di fallback del tipo di carattere, è possibile creare un tipo di carattere composito personalizzato e specificare il tipo di carattere da usare per gli specifici intervalli di punti di codice e le lingue.  
  
 Per altre informazioni su tipi di carattere compositi vedere <xref:System.Windows.Media.FontFamily>.  
  
 **Localizzazione della home page Microsoft**  
  
 È possibile seguire la stessa procedura usata nell'esempio della finestra di dialogo Esegui per localizzare l'applicazione. Il file con estensione CSV localizzato per l'arabo è disponibile nel [esempio della home page di globalizzazione](https://go.microsoft.com/fwlink/?LinkID=159990).
