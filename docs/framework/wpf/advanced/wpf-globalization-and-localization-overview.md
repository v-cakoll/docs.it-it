---
title: Panoramica della globalizzazione e localizzazione WPF
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 957ba16886669acdfa5501ffe02501cbe6e57198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wpf-globalization-and-localization-overview"></a>Panoramica della globalizzazione e localizzazione WPF
Quando si limita la disponibilità del prodotto a una sola lingua, si riduce la potenziale base clienti a una frazione della popolazione mondiale di 6,5 miliardi di persone. Se si vuole che le applicazioni raggiungano un pubblico globale, la localizzazione economica del prodotto è uno dei modi migliori e più economici per raggiungere un ampio pubblico di clienti.  
  
 Questa panoramica vengono presentati globalizzazione e localizzazione in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. La globalizzazione si basa sulla progettazione e sviluppo di applicazioni eseguibili in più posizioni. Ad esempio, la globalizzazione supporta interfacce utente e dati internazionali localizzati per utenti in varie impostazioni cultura. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce funzionalità di progettazione globalizzate, inclusi il layout automatico, gli assembly satellite e attributi localizzati e commenti.
  
 La localizzazione consiste nella conversione delle risorse dell'applicazione in versioni localizzate per specifiche impostazioni cultura supportate dall'applicazione. La localizzazione in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], si usano le API nel <xref:System.Windows.Markup.Localizer> dello spazio dei nomi. Il risparmio API il [strumento LocBaml](http://go.microsoft.com/fwlink/?LinkID=160016) strumento da riga di comando. Per informazioni su come creare e usare LocBaml, vedere [localizzazione di un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).    
  
## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Procedure consigliate per la globalizzazione e la localizzazione in WPF  
 È possibile sfruttare al meglio le funzionalità di globalizzazione e localizzazione incorporato in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguendo la progettazione dell'interfaccia utente e i suggerimenti relativi alla localizzazione forniti in questa sezione.  
  
### <a name="best-practices-for-wpf-ui-design"></a>Procedure consigliate per la progettazione dell'interfaccia utente WPF  
 Quando si progetta un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basato su [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], si consiglia di implementare le procedure consigliate:  
  
-   Scrivere il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; evitare di creare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel codice. Quando si crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], esporlo tramite API di localizzazione predefinite.  
  
-   Evitare di utilizzare posizioni assolute e dimensioni fisse per preparare il contenuto. Utilizzare invece il ridimensionamento automatico o relativo.
  
    -   Utilizzare <xref:System.Windows.Window.SizeToContent%2A>; e mantenere larghezze e altezze impostate su `Auto`.  
  
    -   Evitare di utilizzare <xref:System.Windows.Controls.Canvas> disposti [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s.  
  
    -   Utilizzare <xref:System.Windows.Controls.Grid> e la funzionalità di condivisione delle dimensioni.  
  
-   Lasciare uno spazio aggiuntivo ai margini perché il testo localizzato spesso richiede più spazio. Lo spazio aggiuntivo servirà per eventuali caratteri sporgenti.  
  
-   Abilitare <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> su <xref:System.Windows.Controls.TextBlock> per evitare il ritaglio.
  
-   Impostare il **XML: lang** attributo. Questo attributo descrive le impostazioni cultura di un elemento specifico e i relativi elementi figlio. Il valore di questa proprietà viene modificato il comportamento di diverse funzionalità in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ad esempio, cambia il comportamento della sillabazione, del controllo ortografico, della sostituzione dei numeri, della definizione di lingue con alfabeto non latino e del fallback dei tipi di carattere. Vedere [globalizzazione per WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md) per ulteriori informazioni sull'impostazione di [XML: lang Handling in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md).  
  
-   Creare un tipo di carattere composito personalizzato per ottenere maggiore controllo dei tipi di carattere utilizzati per le diverse lingue. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza il tipo di carattere GlobalUserInterface. composite nella directory Windows\Fonts.  
  
-   Quando si creano applicazioni di navigazione che potrebbero essere localizzate in una lingua con testo in un formato da destra a sinistra, impostare in modo esplicito il <xref:System.Windows.FlowDirection> di ogni pagina per verificare la pagina non eredita <xref:System.Windows.FlowDirection> dal <xref:System.Windows.Navigation.NavigationWindow>.  
  
-   Quando si creano applicazioni di esplorazione autonome che sono ospitate all'esterno di un browser, impostare il <xref:System.Windows.Application.StartupUri%2A> per l'applicazione iniziale di un <xref:System.Windows.Navigation.NavigationWindow> anziché a una pagina (ad esempio, `<Application StartupUri="NavigationWindow.xaml">`). Questa progettazione consente di modificare il <xref:System.Windows.FlowDirection> della finestra e barra di spostamento. Per ulteriori informazioni e un esempio, vedere [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
### <a name="best-practices-for-wpf-localization"></a>Procedure consigliate per la localizzazione di WPF  
 Quando si localizza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: applicazioni basate su, è consigliabile implementare queste procedure consigliate:  
  
-   Utilizzare i commenti di localizzazione per fornire un contesto aggiuntivo per i localizzatori.  
  
-   Utilizzare gli attributi di localizzazione per controllare la localizzazione anziché in modo selettivo l'omissione <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà degli elementi. Vedere [commenti e gli attributi di localizzazione](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md) per ulteriori informazioni.  
  
-   Utilizzare **msbuild /t: updateuid** e **checkuid** per aggiungere e verificare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Utilizzare <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà per rilevare le modifiche tra lo sviluppo e la localizzazione. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà semplificano la localizzazione delle nuove modifiche di sviluppo. Se si aggiunge manualmente <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà per un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], l'attività è in genere monotona e meno accurata.  
  
    -   Non modificare o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> dopo aver iniziato a localizzazione di proprietà.  
  
    -   Non utilizzare duplicato <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà (occorre ricordare che questo suggerimento quando si utilizza il comando di copia e Incolla).  
  
    -   Impostare il `UltimateResourceFallback` posizione nel file AssemblyInfo. * per specificare la lingua di fallback appropriata (ad esempio, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`).  
  
         Se si decide di includere la lingua di origine nell'assembly principale omettendo il `<UICulture>` tag nel file di progetto, impostare il `UltimateResourceFallback` percorso dell'assembly principale anziché il satellite (ad esempio, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`).  
  
<a name="workflow_to_localize"></a>   
## <a name="localize-a-wpf-application"></a>Localizzare un'applicazione WPF  
 Quando si localizza un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'applicazione, sono disponibili diverse opzioni. Ad esempio, è possibile associare le risorse localizzabili nell'applicazione per un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] file, archiviare il testo localizzabile in tabelle resx o impostare il localizzatore [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file. In questa sezione viene descritto un flusso di lavoro di localizzazione che usa il modulo BAML di XAML, che offre diversi vantaggi:  
  
-   È possibile localizzare dopo la compilazione.  
  
-   È possibile eseguire l'aggiornamento a una versione più recente del modulo BAML di XAML con localizzazioni da una versione precedente del modulo BAML di XAML in modo da poter localizzare contemporaneamente allo sviluppo.  
  
-   È possibile convalidare gli elementi di origine e semantica originali in fase di compilazione perché il modulo BAML di XAML è il form compilato dei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
### <a name="localization-build-process"></a>Processo di compilazione per la localizzazione  
 Quando si sviluppa un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione, il processo di compilazione per la localizzazione è il seguente:  
  
-   Lo sviluppatore crea e globalizza il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. Nel file di progetto lo sviluppatore imposta `<UICulture>en-US</UICulture>` in modo che quando viene compilata l'applicazione, viene generato un assembly principale indipendente dalla lingua. Questo assembly dispone di un file satellite con estensione resources.dll che contiene tutte le risorse localizzabili. Facoltativamente, è possibile mantenere la lingua di origine nell'assembly principale perché la localizzazione [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] supportano l'estrazione dall'assembly principale.  
  
-   Quando il file viene compilato nella build, la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene convertito nel modulo BAML di XAML. Indipendenti dalle impostazioni cultura `MyDialog.exe` e il dipendente (inglese) `MyDialog.resources.dll` i file vengono distribuiti ai clienti di lingua inglese.  
  
### <a name="localization-workflow"></a>Flusso di lavoro della localizzazione  
 Il processo di localizzazione inizia dopo il non localizzato `MyDialog.resources.dll` file viene compilato. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi e le proprietà in originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono estratte dal modulo BAML di XAML in coppie chiave-valore tramite il [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] in <xref:System.Windows.Markup.Localizer>. I localizzatori usano le coppie chiave-valore per localizzare l'applicazione. È possibile generare un nuovo file con estensione resource.dll a partire dai nuovi valori dopo che la localizzazione è stata completata.  
  
 Le chiavi delle coppie chiave-valore sono `x:Uid` i valori vengono posizionati dallo sviluppatore nell'originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Questi `x:Uid` valori abilitare il [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] per tenere traccia e unire le modifiche eseguite dallo sviluppatore e il localizzatore durante la localizzazione. Ad esempio, se lo sviluppatore modifica il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dopo il localizzatore inizia la localizzazione, è possibile unire le modifiche di sviluppo con la localizzazione già completata in modo che la conversione minima si perdita di dati.  
  
 La figura seguente mostra un tipico flusso di lavoro di localizzazione basato sul modulo BAML di XAML. Questo diagramma si presuppone che lo sviluppatore scrive l'applicazione in inglese. Lo sviluppatore crea e globalizza l'applicazione WPF. Nel file di progetto lo sviluppatore imposta `<UICulture>en-US</UICulture>` in modo che in fase di compilazione, venga generato un assembly principale indipendente dalla lingua con un satellite. Resources contenente tutte le risorse localizzabili. In alternativa, è possibile mantenere la lingua di origine nell'assembly principale poiché le API di localizzazione WPF supportano l'estrazione dall'assembly principale. Dopo il processo di compilazione, il codice XAML viene compilato in BAML. Il file MyDialog.exe.resources.dll indipendente dalla lingua viene distribuito ai clienti di lingua inglese.  
  
 ![Flusso di lavoro di localizzazione](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![Flusso di lavoro non localizzato](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
<a name="examples_of_localization"></a>   
## <a name="examples-of-wpf-localization"></a>Esempi di localizzazione WPF  
 Questa sezione contiene esempi di applicazioni localizzate che aiutano a comprendere come compilare e localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni.  
  
#### <a name="run-dialog-box-example"></a>Esempio di finestra di dialogo Esegui  
 Il grafico seguente mostra l'output del **eseguire** esempio finestra di dialogo.  
  
 **Inglese:**  
  
 ![Finestra di dialogo Esegui in inglese](../../../../docs/framework/wpf/advanced/media/rundialogenglish.PNG "RunDialogEnglish")  
  
 **Tedesco:**  
  
 ![Finestra di dialogo Esegui in tedesco](../../../../docs/framework/wpf/advanced/media/rundialoggerman.PNG "RunDialogGerman")  
  
 **Progettazione di una finestra di dialogo Esegui globale**  
  
 Questo esempio produce un **eseguire** la finestra di dialogo utilizzando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È equivalente a questa finestra di dialogo di **eseguire** la finestra di dialogo che è disponibile il [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] menu Start.  
  
 Alcune delle caratteristiche principali delle finestre di dialogo globali sono:  
  
 **Layout automatico**  
  
 *In Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 La proprietà Window precedente ridimensiona automaticamente la finestra in base alle dimensioni del contenuto. Questa proprietà impedisce alla finestra di troncare il contenuto che aumenta di dimensioni dopo la localizzazione. Rimuove anche lo spazio superfluo quando le dimensioni del contenuto si riducono dopo la localizzazione.  
  
 `<Grid x:Uid="Grid_1">`  
  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà sono necessarie affinché [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzazione [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] per funzionare correttamente.  
  
 Vengono usati da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzazione [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] per tenere traccia delle modifiche tra lo sviluppo e la localizzazione del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le proprietà consentono di unire una versione più recente del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con una precedente localizzazione il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Si aggiunge un <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà eseguendo **msbuild /t: updateuid RunDialog.csproj** in una shell dei comandi. Questo è il metodo consigliato per aggiungere <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà perché aggiungerli manualmente è in genere richiede molto tempo e meno accurata. È possibile verificare che <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> proprietà sono state impostate correttamente eseguendo **msbuild checkuid RunDialog.csproj**.  
  
 Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è strutturata mediante il <xref:System.Windows.Controls.Grid> controllo, che è un controllo utile per sfruttare i vantaggi del layout automatico in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Si noti che la finestra di dialogo è suddivisa in tre righe e cinque colonne. Non è una delle definizioni di riga e colonna ha dimensioni fisse. di conseguenza, il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] gli elementi che verranno posizionati in ogni cella possono adattarsi a aumenta e si riducono le dimensioni durante la localizzazione.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Le prime due colonne in cui il **aprire:** etichetta e <xref:System.Windows.Controls.ComboBox> vengono posizionate utilizzano il 10% del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] larghezza totale.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Si noti che l'esempio Usa la funzionalità di ridimensionamento condiviso di <xref:System.Windows.Controls.Grid>. Le ultime tre colonne sfruttano tale inserendo stessi nello stesso <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>. Come si evince dal nome della proprietà, in questo modo le colonne possono condividere le stesse dimensioni. Di conseguenza, quando "Sfoglia..." viene localizzato nella stringa più lunga "Durchsuchen...", la larghezza di tutti i pulsanti aumenta anziché avere una sproporzione tra un piccolo pulsante "OK" e un pulsante "Durchsuchen..." estremamente grande. immagini (...).  
  
 **Xml:lang**  
  
 `Xml:lang="en-US"`  
  
 Si noti il [XML: lang Handling in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) posizionato in corrispondenza dell'elemento radice del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Questa proprietà descrive le impostazioni cultura di un determinato elemento e dei relativi elementi figlio. Questo valore viene utilizzato da diverse funzionalità in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e deve essere modificata in modo appropriato durante la localizzazione. Questo valore cambia il dizionario in lingua usato per la sillabazione e il controllo ortografico delle parole. Influisce anche sulla visualizzazione delle cifre e sulla selezione del tipo di carattere da usare da parte del sistema di fallback dei tipi di carattere. Infine, la proprietà influisce sulla visualizzazione dei numeri e sulla forma dei testi scritti in lingue con alfabeti non latini. Il valore predefinito è "en-US".  
  
 **Creazione di un assembly di risorse satellite**  
  
 *Nel file con estensione csproj:*  
  
 `<UICulture>en-US</UICulture>`  
  
 Si noti l'aggiunta di un `UICulture` valore. Quando è impostato su un valore valido <xref:System.Globalization.CultureInfo> valore, ad esempio en-US, compilare il progetto verrà generato un assembly satellite con tutte le risorse localizzabili in essa contenuti.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 Il `RunIcon.JPG` non deve essere localizzato poiché deve essere visualizzato lo stesso per tutte le impostazioni cultura. `Localizable` è impostato su `false` in modo che rimanga nell'assembly principale indipendente dalla lingua anziché l'assembly satellite. Il valore predefinito di tutte le risorse non compilabili è `Localizable` impostato su `true`.  
  
 **Localizzazione della finestra di dialogo Esegui**  
  
 **Analisi**  
  
 Dopo aver compilato l'applicazione, il primo passaggio della localizzazione consiste nell'analizzare le risorse localizzabili nell'assembly satellite. Ai fini di questo argomento, utilizzare lo strumento LocBaml esempio è reperibile in [strumento LocBaml](http://go.microsoft.com/fwlink/?LinkID=160016). Si noti che LocBaml è solo uno strumento di esempio che permette di iniziare a creare uno strumento di localizzazione adatto al processo di localizzazione. Tramite LocBaml, eseguire il comando seguente per analizzare: **LocBaml/analizzare RunDialog.resources.dll /out:** per generare un file "RunDialog".  
  
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
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|Geben Sie den Namen eines Programms Ordners, Dokuments o einer Internetresource un.|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Testo|Öffnen:|  
|Window_1:System.Windows.Window.Title|Titolo|Esegui|  
  
 **Generazione**  
  
 L'ultimo passaggio della localizzazione implica la creazione dell'assembly satellite appena localizzato. Per questa operazione usare il comando LocBaml seguente:  
  
 **LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**  
  
 Nella versione tedesca [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], se questo Resources viene inserito in una cartella de-DE accanto all'assembly principale, questa risorsa verrà caricata automaticamente anziché quello nella cartella en-US. Se non si dispone di una versione tedesca di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] per testarla, è necessario configurare le impostazioni cultura e utilizzare le impostazioni di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] uso (ad esempio en-US) e sostituire il Resources originale.  
  
 **Caricamento di risorse satellite**  
  
|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Codice|BAML inglese originale|BAML localizzato|  
|Risorse indipendenti dalle impostazioni cultura|Altre risorse in inglese|Altre risorse localizzate in tedesco|  
  
 .NET framework sceglie automaticamente l'assembly di risorse satellite da caricare in base all'applicazione `Thread.CurrentThread.CurrentUICulture`. L'impostazione predefinita per le impostazioni cultura del [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] sistema operativo. Pertanto, se si utilizza tedesco [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], carica il de-DE\MyDialog.resources.dll, se si utilizza l'inglese [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], en-US\MyDialog.resources.dll carica. Per impostare la risorsa di fallback finale per l'applicazione, specificare NeutralResourcesLanguage nel file AssemblyInfo.* del progetto. Ad esempio se si specifica:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 verrà utilizzato en-US\MyDialog.resources.dll con la versione tedesca di Windows se non sono disponibili de-DE\MyDialog.resources.dll o de\MyDialog.resources.dll.  
  
### <a name="microsoft-saudi-arabia-homepage"></a>Home page Microsoft per l'Arabia Saudita  
 Le immagini seguenti mostrano una home page in inglese e in arabo. Per l'esempio completo che produce questa grafica vedere [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Inglese:**  
  
 ![Pagina inglese](../../../../docs/framework/wpf/advanced/media/englishhomepage.jpg "EnglishHomepage")  
  
 **Arabo:**  
  
 ![Pagina in arabo](../../../../docs/framework/wpf/advanced/media/arabichomepage.jpg "ArabicHomepage")  
  
### <a name="designing-a-global-microsoft-homepage"></a>Progettazione di una home page Microsoft globale  
 Questo modello di sito Web Microsoft per l'Arabia Saudita illustra le funzionalità di globalizzazione disponibili per le lingue da destra a sinistra. Linguaggi, ad esempio lingua ebraica e araba dispongono di un ordine di lettura da destra a sinistra così il layout di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] spesso devono essere disposte in modo molto diverso rispetto a quanto sarebbe in lingue da sinistra a destra, ad esempio inglese. La localizzazione da una lingua da sinistra a destra in una lingua da destra a sinistra o viceversa può risultare piuttosto complessa. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è stato progettato per semplificare tali processi di localizzazione.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xaml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Si noti il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà <xref:System.Windows.Controls.Page>. Modifica questa proprietà su <xref:System.Windows.FlowDirection.RightToLeft> verrà modificato il <xref:System.Windows.FrameworkElement.FlowDirection%2A> del <xref:System.Windows.Controls.Page> e dei relativi elementi figlio in modo che il layout di questa [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] capovolgere per diventare da destra a sinistra, come un utente arabo. Per eseguire l'override del comportamento di ereditarietà specificando esplicita <xref:System.Windows.FrameworkElement.FlowDirection%2A> su qualsiasi elemento. Il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà è disponibile in qualsiasi <xref:System.Windows.FrameworkElement> o elemento correlato al documento e ha un valore implicito <xref:System.Windows.FlowDirection.LeftToRight>.  
  
 Osservare che anche il background sfumatura invertita correttamente quando la radice <xref:System.Windows.FrameworkElement.FlowDirection%2A> viene modificato:  
  
 **FlowDirection="LeftToRight"**  
  
 ![Flusso da sinistra a destra](../../../../docs/framework/wpf/advanced/media/lefttoright.PNG "LeftToRight")  
  
 **FlowDirection="RightToLeft"**  
  
 ![Flusso da destra a sinistra](../../../../docs/framework/wpf/advanced/media/righttoleft.PNG "RightToLeft")  
  
 **Evitare l'utilizzo di dimensioni fisse per riquadri e controlli**  
  
 Esaminare homepage, si noti che oltre la larghezza fissa e l'altezza specificate per l'intera [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in alto <xref:System.Windows.Controls.DockPanel>, vi sono altre dimensioni fisse. Se si usano dimensioni fisse, è possibile che il testo localizzato risulti più lungo rispetto al testo di origine e debba essere ritagliato. I pannelli e i controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verranno automaticamente ridimensionati in base al contenuto. La maggior parte dei controlli dispone anche di dimensioni minime e massime che è possibile impostare per un maggiore controllo (ad esempio MinWidth = "20"). Con <xref:System.Windows.Controls.Grid>, è anche possibile impostare larghezze e altezze utilizzando ' *' (ad esempio Width = "0,25\*") o utilizzare le dimensioni della cella funzionalità per la condivisione.  
  
 **Commenti di localizzazione**  
  
 In molti casi il contenuto può risultare ambiguo e difficile da tradurre. Lo sviluppatore o il progettista ha la possibilità di fornire ai localizzatori contesto aggiuntivo e commenti tramite i commenti di localizzazione. Ad esempio l'oggetto Localization.Comments seguente chiarisce l'utilizzo del carattere '&#124;'.  
  
 [!code-xaml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Questo commento viene associato al contenuto di TextBlock_1 e nel caso dello strumento LocBaml (vedere [localizzazione di un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)), può essere visualizzato nella colonna 6 della riga TextBlock_1 nel file CSV di output:  
  
|Chiave di risorsa|Category|Leggibile|Modificabile|Commento|Valore|  
|-|-|-|-|-|-|  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Testo|true|true|Questo carattere viene usato come regola decorativa.|&#124;|  
  
 I commenti possono essere inseriti nel contenuto o nella proprietà di qualsiasi elemento usando la sintassi seguente:  
  
 [!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Attributi di localizzazione**  
  
 Spesso lo sviluppatore o il responsabile della localizzazione deve avere il controllo su tutto ciò che i localizzatori possono leggere e modificare. Ad esempio, il localizzatore non deve tradurre il nome della società o modificare alcuni termini legali. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone di attributi che consentono di impostare la leggibilità, modificabilità e la categoria del contenuto o delle proprietà di un elemento e che possono essere usati dallo strumento di localizzazione per bloccare, nascondere o ordinare gli elementi. Per altre informazioni, vedere <xref:System.Windows.Localization.Attributes%2A>. Ai fini di questo esempio, lo strumento LocBaml restituisce solo i valori di questi attributi. I controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno tutti i valori predefiniti per questi attributi, ma è possibile eseguirne l'override. Ad esempio, nell'esempio seguente esegue l'override gli attributi di localizzazione predefiniti per `TextBlock_1` e imposta il contenuto sia leggibile ma non modificabile per i localizzatori.  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 Oltre agli attributi di leggibilità e modificabilità, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un'enumerazione di categorie comuni di interfaccia utente (<xref:System.Windows.LocalizationCategory>) che può essere utilizzato per fornire ai localizzatori più contesto. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] categorie predefinite per i controlli della piattaforma possono essere sottoposto a override in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anche:  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Gli attributi di localizzazione predefiniti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce può inoltre essere sottoposto a override tramite codice, pertanto è possibile impostare correttamente i valori predefiniti appropriati per i controlli personalizzati. Ad esempio:  
  
 `[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]`  
  
 `public class CorporateLogo: TextBlock`  
  
 `{`  
  
 `…`  
  
 `..`  
  
 `.`  
  
 `}`  
  
 Di attributi per istanza impostati [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] avrà la precedenza sui valori impostati nel codice per i controlli personalizzati. Per ulteriori informazioni sugli attributi e i commenti, vedere [commenti e gli attributi di localizzazione](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
 **Fallback dei tipi di carattere e tipi di carattere compositi**  
  
 Se si specifica un tipo di carattere che non supporta un intervallo di punti di codice specificato, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eseguirà automaticamente il fallback a un mediante compositefont di utente globale si trova nella directory Windows\Fonts. I tipi di carattere compositi funzionano come qualsiasi altro tipo di carattere e possono essere usati in modo esplicito impostando FontFamily di un elemento (ad esempio, FontFamily = "Interfaccia utente globale"). Per specificare le preferenze di fallback del tipo di carattere, è possibile creare un tipo di carattere composito personalizzato e specificare il tipo di carattere da usare per gli specifici intervalli di punti di codice e le lingue.  
  
 Per ulteriori informazioni sui tipi di carattere compositi vedere <xref:System.Windows.Media.FontFamily>.  
  
 **Localizzazione della home page Microsoft**  
  
 È possibile seguire la stessa procedura usata nell'esempio della finestra di dialogo Esegui per localizzare l'applicazione. Il file CSV localizzato per la lingua araba è disponibile nel [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).
