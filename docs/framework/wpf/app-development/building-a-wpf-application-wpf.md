---
title: Compilazione di un'applicazione WPF (WPF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], building
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
ms.openlocfilehash: 48536d8fba3f86c2883e48cd4e5cf9a3a8752fcd
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636315"
---
# <a name="building-a-wpf-application-wpf"></a>Compilazione di un'applicazione WPF (WPF)

Le applicazioni Windows Presentation Foundation (WPF) possono essere compilate come .NET Framework eseguibili (con estensione exe), librerie (. dll) o una combinazione di entrambi i tipi di assembly. In questo argomento viene illustrato come compilare applicazioni WPF e vengono descritti i passaggi principali del processo di compilazione.

<a name="Building_a_WPF_Application_using_Command_Line"></a>

## <a name="building-a-wpf-application"></a>Compilazione di un'applicazione WPF

Un'applicazione WPF può essere compilata nei modi seguenti:

- Dalla riga di comando. L'applicazione deve contenere solo codice (non XAML) e un file di definizione dell'applicazione (ADF). Per altre informazioni, vedere [Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oppure [Compilazione dalla riga di comando (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

- Microsoft Build Engine (MSBuild). Oltre ai file di codice e XAML, l'applicazione deve contenere un file di progetto MSBuild. Per altre informazioni, vedere "MSBuild".

- Visual Studio. Visual Studio è un ambiente di sviluppo integrato che consente di compilare applicazioni WPF con MSBuild e include una finestra di progettazione visiva per la creazione dell'interfaccia utente. Per altre informazioni, vedere [scrittura e gestione del codice con Visual Studio](/visualstudio/ide/index-writing-code) e [progettazione di XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>

## <a name="wpf-build-pipeline"></a>Pipeline di compilazione WPF

Quando viene compilato un progetto WPF, viene richiamata la combinazione di destinazioni specifiche del linguaggio e di WPF. Il processo di esecuzione di queste destinazioni è definito pipeline di compilazione e i passaggi principali sono illustrati nella figura seguente.

![Processo di compilazione WPF](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")

<a name="Pre_Build_Initializations"></a>

### <a name="pre-build-initializations"></a>Inizializzazioni pre-compilazione

Prima della compilazione, MSBuild determina la posizione di strumenti e librerie importanti, inclusi i seguenti:

- .NET Framework.

- Directory Windows SDK.

- Percorso degli assembly di riferimento WPF.

- La proprietà per i percorsi di ricerca degli assembly.

La prima posizione in cui MSBuild cerca gli assembly è la directory dell'assembly di riferimento (%programmi%\Reference%SYSTEMDRIVE%\Programmi\Reference Assemblies\Microsoft\Framework\v3.0.\\). Durante questo passaggio, il processo di compilazione inizializza anche le varie proprietà e i gruppi di elementi, quindi esegue le operazioni di pulizia necessarie.

<a name="Resolving_references"></a>

### <a name="resolving-references"></a>Risoluzione dei riferimenti

Il processo di compilazione individua e associa gli assembly necessari per compilare il progetto di applicazione. Questa logica è contenuta nell'attività `ResolveAssemblyReference`. Tutti gli assembly dichiarati come `Reference` nel file di progetto sono disponibili per l'attività insieme a informazioni sui percorsi di ricerca e metadati degli assembly già installati nel sistema. L'attività Cerca gli assembly e usa i metadati dell'assembly installato per filtrare gli assembly WPF di base che non devono essere visualizzati nei manifesti di output. Questa operazione viene eseguita per evitare informazioni ridondanti nei manifesti ClickOnce. Ad esempio, poiché il file PresentationFramework. dll può essere considerato rappresentativo di un'applicazione compilata in e per WPF e poiché tutti gli assembly WPF si trovano nello stesso percorso in ogni computer in cui è installato il .NET Framework, non è necessario includere tutti informazioni su tutti gli assembly di riferimento .NET Framework nei manifesti.

<a name="Markup_Compilation___Pass_1"></a>

### <a name="markup-compilationpass-1"></a>Compilazione del markup - Passaggio 1

In questo passaggio, i file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono analizzati e compilati in modo che il runtime non spenda tempo per l'analisi del codice XML e la convalida dei valori delle proprietà. Il file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compilato viene preliminarmente suddiviso in token in modo che, in fase di esecuzione, risulti molto più veloce da caricare rispetto a un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

Durante questo passaggio, le attività dell'elenco vengono eseguite per ogni file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che rappresenta un elemento Build `Page`:

1. Il file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene analizzato dal compilatore di markup.

2. Una rappresentazione compilata viene creata per tale file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e viene copiata nella cartella obj\Release.

3. Una rappresentazione CodeDOM di una nuova classe parziale viene creata e copiata nella cartella obj\Release.

Viene anche generato un file di codice specifico del linguaggio per ogni file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ad esempio, per una pagina Pagina1. XAML in un progetto Visual Basic, viene generato un file Pagina1. g. vb; per una pagina Pagina1. XAML in un C# progetto, viene generato un Page1.g.cs. Il componente ".g" nel nome del file indica che il file è costituito da codice generato con una dichiarazione di classe parziale per l'elemento di livello superiore del file di markup (ad esempio `Page` o `Window`). La classe viene dichiarata con il modificatore di `partial` in C# (`Extends` in Visual Basic) per indicare che è presente un'altra dichiarazione per la classe altrove, in genere nel file code-behind Page1.XAML.cs.

La classe parziale si estende dalla classe di base appropriata, ad esempio <xref:System.Windows.Controls.Page> per una pagina, e implementa l'interfaccia <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType>. L'interfaccia <xref:System.Windows.Markup.IComponentConnector> dispone di metodi per inizializzare un componente e connettere nomi ed eventi sugli elementi nel contenuto. Di conseguenza, il file di codice generato ha un'implementazione del metodo simile all'esempio seguente:

```csharp
public void InitializeComponent() {
    if (_contentLoaded) {
        return;
    }
    _contentLoaded = true;
    System.Uri resourceLocater =
        new System.Uri(
            "window1.xaml",
            System.UriKind.RelativeOrAbsolute);
    System.Windows.Application.LoadComponent(this, resourceLocater);
}
```

```vb
Public Sub InitializeComponent() _

    If _contentLoaded Then
        Return
    End If

    _contentLoaded = True
    Dim resourceLocater As System.Uri = _
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)

    System.Windows.Application.LoadComponent(Me, resourceLocater)

End Sub
```

Per impostazione predefinita, la compilazione del markup viene eseguita nello stesso <xref:System.AppDomain> del motore MSBuild. In questo modo si ottengono miglioramenti significativi delle prestazioni. Questo comportamento può essere attivato o disattivato tramite la proprietà `AlwaysCompileMarkupFilesInSeparateDomain`. Questa operazione ha il vantaggio di scaricare tutti gli assembly di riferimento scaricando il <xref:System.AppDomain>separato.

<a name="Pass_2_of_Markup_Compilation"></a>

### <a name="markup-compilationpass-2"></a>Compilazione del markup - Passaggio 2

Non tutte le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono compilate durante il passaggio 1 della compilazione del markup. I file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che dispongono di riferimenti a tipi definiti in locale (riferimenti a tipi definiti nel codice in un'altra parte dello stesso progetto) sono esclusi dalla compilazione in questa fase, poiché tali tipi definiti in locale esistono solo nel codice sorgente e non sono ancora stati compilati. Per determinare questo aspetto, il parser utilizza un'euristica che implica la ricerca di elementi, ad esempio `x:Name`, nel file di markup. Se si individua un'istanza di questo tipo, la compilazione di tale file di markup viene posticipata fino a quando non vengono compilati i file di codice. Dopodiché, nel secondo passaggio di compilazione del markup, si elaborano questi file.

<a name="File_Classification"></a>

### <a name="file-classification"></a>Classificazione dei file

Il processo di compilazione inserisce i file di output in diversi gruppi di risorse sulla base dell'assembly dell'applicazione in cui verranno inseriti. In una tipica applicazione non localizzata tutti i file di dati contrassegnati come `Resource` vengono inseriti nell'assembly principale (eseguibile o libreria). Quando `UICulture` è impostato nel progetto, tutti i file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compilati e le risorse espressamente contrassegnate come specifiche del linguaggio vengono inserite nell'assembly di risorse satellite. Anche le risorse indipendenti dal linguaggio vengono inserite nell'assembly principale. In questo passaggio del processo di compilazione viene determinato tale aspetto.

Le azioni di compilazione `ApplicationDefinition`, `Page` e `Resource` nel file di progetto possono essere estese con i metadati `Localizable` (i valori accettabili sono `true` e `false`), che determinano se il file è specifico del linguaggio o indipendente da esso.

<a name="Core_Compilation"></a>

### <a name="core-compilation"></a>Compilazione base

Il passaggio base della compilazione include la compilazione dei file di codice. Questa operazione viene gestita dalla logica nei file di destinazioni specifici del linguaggio Microsoft.CSharp.targets e Microsoft.VisualBasic.targets. Se l'euristica ha determinato che è sufficiente un unico passaggio del compilatore di markup, viene generato l'assembly principale. Tuttavia, se uno o più file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nel progetto hanno riferimenti a tipi definiti in locale, viene generato un file temporaneo con estensione dll e gli assembly dell'applicazione finale potranno essere creati dopo il completamento del secondo passaggio della compilazione di markup.

<a name="Manifest_generation"></a>

### <a name="manifest-generation"></a>Generazione di manifesti

Al termine del processo di compilazione, dopo che tutti gli assembly dell'applicazione e i file di contenuto sono pronti, vengono generati i manifesti ClickOnce per l'applicazione.

Il file manifesto della distribuzione descrive il modello di distribuzione: la versione corrente, il comportamento di aggiornamento e l'identità del server di pubblicazione insieme alla firma digitale. Questo manifesto deve essere creato dagli amministratori che gestiscono la distribuzione. L'estensione del file è XBAP (per le applicazioni browser XAML (XBAPs) e. Application per le applicazioni installate. La prima estensione è dovuta alla proprietà del progetto `HostInBrowser` e, di conseguenza, il manifesto identifica l'applicazione come ospitata dal browser.

Il manifesto dell'applicazione (un file con estensione exe.manifest) descrive l'assembly dell'applicazione e le librerie dipendenti, oltre a elencare le autorizzazioni richieste dall'applicazione. Questo file deve essere creato dallo sviluppatore dell'applicazione. Per avviare un'applicazione ClickOnce, un utente apre il file manifesto di distribuzione dell'applicazione.

Questi file manifesto vengono sempre creati per le applicazioni XBAP. Per le applicazioni installate, i file manifesto non vengono creati, a meno che la proprietà `GenerateManifests` venga specificata nel file di progetto con il valore `true`.

Le applicazioni XBAPs ottengono due autorizzazioni aggiuntive oltre a quelle assegnate alle tipiche applicazioni dell'area Internet: <xref:System.Security.Permissions.WebBrowserPermission> e <xref:System.Security.Permissions.MediaPermission>. Il sistema di compilazione WPF dichiara tali autorizzazioni nel manifesto dell'applicazione.

<a name="Incremental_Build_Support"></a>

## <a name="incremental-build-support"></a>Supporto della compilazione incrementale

Il sistema di compilazione WPF fornisce supporto per le compilazioni incrementali. in quanto è in grado di rilevare le modifiche apportate al codice o al markup e compila solo gli elementi interessati dalla modifica. Il meccanismo di compilazione incrementale utilizza i file seguenti:

- Un file $(*NomeAssembly*)_MarkupCompiler.Cache per gestire lo stato corrente del compilatore.

- Un file $(*NomeAssembly*)_MarkupCompiler. lref per memorizzare nella cache i file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con riferimenti a tipi definiti in locale.

Di seguito è riportato un set di regole che controlla la compilazione incrementale:

- Il file è la più piccola unità di rilevazione delle modifiche per il sistema di compilazione. Pertanto, per un file di codice, il sistema di compilazione non è in grado di stabilire se è stato modificato un tipo o se è stato aggiunto codice. Lo stesso vale per i file di progetto.

- Il meccanismo di compilazione incrementale deve tenere conto del fatto che una pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definisce una classe oppure utilizza altre classi.

- Se le voci `Reference` vengono modificate, è necessario ricompilare tutte le pagine.

- Se un file di codice viene modificato, ricompilare tutte le pagine contenenti riferimenti a tipi definiti in locale.

- Se un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene modificato:

  - Quando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è dichiarato come `Page` nel progetto: se il file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non dispone di riferimenti a tipi definiti in locale, ricompilare tale file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e tutte le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con riferimenti locali; se il file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dispone di riferimenti locali, ricompilare tutte le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con riferimenti locali.

  - Se [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene dichiarata come `ApplicationDefinition` nel progetto: ricompilare tutte le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (motivo: ogni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] presenta un riferimento a un tipo di <xref:System.Windows.Application> che potrebbe essere stato modificato).

- Quando il file di progetto dichiara un file di codice come definizione di applicazione anziché un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:

  - Controllare se il valore `ApplicationClassName` nel file di progetto è stato modificato (se è presente un nuovo tipo di applicazione). In questo caso, è necessario ricompilare l'intera applicazione.

  - In caso contrario, è sufficiente ricompilare tutte le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con riferimenti locali.

- Quando viene modificato un file di progetto: applicare tutte le regole precedenti e stabilire cosa deve essere ricompilato. Le modifiche alle seguenti proprietà determinano una ricompilazione completa: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace` e `HostInBrowser`.

Sono possibili gli scenari di ricompilazione seguenti:

- Viene ricompilata l'intera applicazione.

- Vengono ricompilati solo i file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con riferimenti a tipi definiti in locale.

- Non viene ricompilato nulla (se non è stato modificato nulla nel progetto).

## <a name="see-also"></a>Vedere anche

- [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)
- [Informazioni di riferimento su MSBuild WPF](/visualstudio/msbuild/wpf-msbuild-reference)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md)
