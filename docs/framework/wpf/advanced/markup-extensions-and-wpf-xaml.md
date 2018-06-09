---
title: Estensioni di markup e XAML WPF
ms.date: 03/30/2017
helpviewer_keywords:
- brace character [WPF]
- Binding markup extensions [WPF]
- RelativeSource markup extensions [WPF]
- XAML [WPF], markup extensions
- markup extensions [WPF]
- nesting extension syntax [WPF]
- curly brace characters ({})
- TemplateBinding markup extensions [WPF]
- StaticResource markup extensions [WPF]
- literal curly brace characters ({})
- characters [WPF], curly brace
- DynamicResource markup extensions [WPF]
ms.assetid: 618dc745-8b14-4886-833f-486d2254bb78
ms.openlocfilehash: 907d5dcaae8f6e09902c2b3548d5ba8ac9a2b077
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251168"
---
# <a name="markup-extensions-and-wpf-xaml"></a>Estensioni di markup e XAML WPF
Questo argomento introduce le estensioni di markup per XAML, con informazioni sulle regole della sintassi, le finalità e il modello a oggetti di classe sottostante. Le estensioni di markup sono una funzionalità generale del linguaggio XAML e dell'implementazione .NET di servizi XAML. Questo argomento descrive in particolare le estensioni di markup per l'uso in XAML WPF.  
  
  
<a name="XAML_Processors_and_Markup_Extensions"></a>   
## <a name="xaml-processors-and-markup-extensions"></a>Processori XAML ed estensioni di markup  
 In generale, un parser XAML può interpretare un valore di attributo come stringa letterale che può essere convertita in tipo primitivo oppure può convertirlo in oggetto in qualche modo. Uno di questi modi consiste nel fare riferimento a un convertitore di tipi e viene descritto nell'argomento [Convertitori di tipi e XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md). In alcuni scenari, tuttavia, è necessario un comportamento diverso. Ad esempio, è possibile indicare a un processore XAML che un valore di un attributo non deve essere restituito come nuovo oggetto nell'oggetto grafico. L'attributo deve invece essere restituito come oggetto grafico che crea un riferimento a un oggetto già costruito in un'altra parte dell'oggetto grafico o a un oggetto statico. In base a un altro scenario è possibile richiedere a un processore XAML di usare una sintassi che fornisca argomenti non predefiniti al costruttore di un oggetto. In scenari di questi tipi un'estensione di markup può essere la soluzione.  
  
<a name="Basic_Markup_Extension_Syntax"></a>   
## <a name="basic-markup-extension-syntax"></a>Sintassi delle estensioni di markup di base  
 Un'estensione di markup può essere implementata per fornire valori per le proprietà in una sintassi di attributi, le proprietà in una sintassi di elementi proprietà o entrambe.  
  
 Se usata per fornire un valore di attributo, la sintassi che distingue una sequenza di estensioni di markup per un processore XAML è la presenza delle parentesi graffe di apertura e chiusura ({ e }). Il tipo di estensione di markup viene quindi identificato dal token di stringa immediatamente successivo alla parentesi graffa di apertura.  
  
 Se usata nella sintassi di elementi proprietà, un'estensione di markup è visivamente identica a qualsiasi altro elemento usato per fornire il valore di un elemento proprietà: un elemento dichiarato XAML che fa riferimento alla classe dell'estensione di markup come elemento, racchiuso tra parentesi angolari (<>).  
  
<a name="XAML_Defined_Markup_Extensions"></a>   
## <a name="xaml-defined-markup-extensions"></a>Estensioni di markup definite da XAML  
 Esistono diverse estensioni di markup non specifiche dell'implementazione WPF di XAML, ma che sono invece implementazioni di intrinseci o funzionalità di XAML come linguaggio. Queste estensioni di markup vengono implementate nell'assembly System.Xaml come parte dei servizi XAML generali di .NET Framework e sono incluse nello spazio dei nomi XAML del linguaggio XAML. In termini di utilizzo comune del markup, queste estensioni di markup sono in genere identificabili dal prefisso `x:` nella sintassi. La <xref:System.Windows.Markup.MarkupExtension> classe di base (anche definito in System. XAML) fornisce il modello che tutte le estensioni di markup devono usare per ricevere il supporto di reader XAML e writer XAML, incluso in XAML di WPF.  
  
-   `x:Type` fornisce l'oggetto <xref:System.Type> per il tipo denominato. Questa funzionalità viene usata più comunemente in stili e modelli. Per informazioni dettagliate, vedere [Estensione di markup x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md).  
  
-   `x:Static` produce valori statici. I valori provengono da entità di codice di tipo di valore che non sono direttamente il tipo del valore di una proprietà di destinazione, ma possono restituire tale tipo. Per informazioni dettagliate, vedere [Estensione di markup x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md).  
  
-   `x:Null` specifica `null` come valore per una proprietà e può essere usata per attributi o valori di elementi proprietà. Per informazioni dettagliate, vedere [Estensione di markup x:Null](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
-   `x:Array` supporta la creazione di matrici generali nella sintassi XAML nei casi in cui si sceglie intenzionalmente di non usare il supporto delle raccolte fornito dagli elementi di base e dai modelli di controllo di WPF. Per informazioni dettagliate, vedere [Estensione di markup x:Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md).  
  
> [!NOTE]
>  Il prefisso `x:` viene usato per il mapping dello spazio dei nomi XAML tipico degli intrinseci del linguaggio XAML, nell'elemento radice di un file o una produzione XAML. Ad esempio, i modelli di Visual Studio per le applicazioni WPF avviano un file XAML usando il `x:` mapping. Nel mapping dello spazio dei nomi XAML personalizzato è possibile scegliere un token di prefisso diverso. Tuttavia, per identificare le entità che rappresentano una parte definita dello spazio dei nomi XAML per il linguaggio XAML, questa documentazione usa il mapping `x:` predefinito anziché lo spazio dei nomi WPF predefinito o altri spazi dei nomi XAML non correlati a un framework specifico.  
  
<a name="WPF_Specific_Markup_Extensions"></a>   
## <a name="wpf-specific-markup-extensions"></a>Estensioni di markup specifiche di WPF  
 Le estensioni di markup più comuni usate nella programmazione WPF sono quelle che supportano i riferimenti a risorse (`StaticResource` e `DynamicResource`) e quelli che supportano il data binding (`Binding`).  
  
-   `StaticResource` fornisce un valore per una proprietà sostituendo il valore di una risorsa già definita. Una valutazione di `StaticResource` viene infine eseguita in fase di caricamento XAML e non ha accesso all'oggetto grafico in fase di esecuzione. Per informazioni dettagliate, vedere [Estensione di markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   `DynamicResource` fornisce un valore per una proprietà rinviando il valore come riferimento in fase di esecuzione a una risorsa. Il riferimento a una risorsa dinamica forza una nuova ricerca ogni volta che si accede a tale risorsa e che la risorsa ha accesso all'oggetto grafico in fase di esecuzione. Per ottenere questo accesso, il concetto di `DynamicResource` è supportato da proprietà di dipendenza nel sistema di proprietà WPF e da espressioni valutate. Di conseguenza, è possibile usare `DynamicResource` solo per la destinazione di una proprietà di dipendenza. Per informazioni dettagliate, vedere [Estensione di markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
-   `Binding` fornisce un valore di data binding per una proprietà, usando il contesto dei dati valido per l'oggetto padre in fase di esecuzione. Questa estensione di markup è relativamente complessa, perché permette una sintassi inline sostanziale per specificare un data binding. Per informazioni dettagliate, vedere [Estensione di markup Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md).  
  
-   `RelativeSource` fornisce informazioni di origine per un <xref:System.Windows.Data.Binding> che può passare più relazioni possibili nell'albero degli oggetti in fase di esecuzione. In questo modo, si ottengono origini specializzate per i binding creati in modelli multiuso o creati nel codice senza una completa conoscenza dell'albero di oggetti circostante. Per informazioni dettagliate, vedere [Estensione di markup RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md).  
  
-   `TemplateBinding` permette a un modello di controllo di usare valori per proprietà basate su modelli provenienti da proprietà definite da modelli a oggetti della classe che userà il modello. In altri termini, la proprietà all'interno della definizione del modello può accedere a un contesto che esiste solo dopo l'applicazione del modello. Per informazioni dettagliate, vedere [Estensione di markup TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md). Per altre informazioni sull'uso pratico di `TemplateBinding`, vedere [Applicazione di stili con l'esempio di ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
-   `ColorConvertedBitmap` supporta uno scenario di creazione di immagini relativamente avanzato. Per informazioni dettagliate, vedere [Estensione di markup ColorConvertedBitmap](../../../../docs/framework/wpf/advanced/colorconvertedbitmap-markup-extension.md).  
  
-   `ComponentResourceKey` e `ThemeDictionary` supportano alcuni aspetti della ricerca di risorse, in particolare per risorse e temi che contengono controlli personalizzati. Per altre informazioni, vedere [Estensione di markup ComponentResourceKey](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md), [Estensione di markup ThemeDictionary](../../../../docs/framework/wpf/advanced/themedictionary-markup-extension.md) o [Panoramica della creazione di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="StarExtension"></a>   
## <a name="extension-classes"></a>*Classi di estensione  
 Per il linguaggio XAML generale e le estensioni di markup WPF specifiche, il comportamento di ogni estensione di markup viene identificato in un processore XAML tramite un `*Extension` classe che deriva da <xref:System.Windows.Markup.MarkupExtension>e fornisce un'implementazione del <xref:System.Windows.Markup.StaticExtension.ProvideValue%2A> metodo. Questo metodo in ogni estensione fornisce l'oggetto restituito quando viene valutata l'estensione di markup. L'oggetto restituito viene in genere valutato in base ai diversi token di stringa passati all'estensione di markup.  
  
 Ad esempio, il <xref:System.Windows.StaticResourceExtension> classe fornisce l'implementazione della superficie di ricerca effettiva di risorse in modo che il relativo <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> implementazione restituisce l'oggetto richiesto, con l'input di tale implementazione costituito da una stringa che viene utilizzata per cercare la risorsa dal relativo `x:Key`. Molti dei dettagli di questa implementazione sono irrilevanti se si usa un'estensione di markup esistente.  
  
 Alcune estensioni di markup non usano argomenti dei token di stringa. Il motivo è che restituiscono un valore statico o coerente oppure perché il contesto per il valore da restituire è disponibile tramite uno dei servizi passati tramite il parametro `serviceProvider`.  
  
 Il criterio di denominazione `*Extension` ha scopi di praticità e coerenza. Non è necessario perché un processore XAML identifichi la classe come supporto per un'estensione di markup. Purché la codebase include System. XAML e utilizza le implementazioni di servizi XAML di .NET Framework, sono necessario per essere riconosciute come un'estensione di markup XAML consiste nel derivare da <xref:System.Windows.Markup.MarkupExtension> e supporta una sintassi di costruzione. WPF definisce classi abilitazione estensione di markup non seguono il `*Extension` denominazione modello, ad esempio <xref:System.Windows.Data.Binding>. In genere il motivo è che la classe supporta scenari che vanno oltre il puro supporto delle estensioni di markup. In caso di <xref:System.Windows.Data.Binding>, che classe supporta l'accesso ai metodi e proprietà dell'oggetto in fase di esecuzione per gli scenari che avere nulla a che fare con XAML.  
  
### <a name="extension-class-interpretation-of-initialization-text"></a>Interpretazione del testo di inizializzazione da parte delle classi delle estensioni  
 I token di stringa che seguono il nome dell'estensione di markup e ancora racchiuse tra parentesi graffe vengono interpretati da un processore XAML in uno dei modi seguenti:  
  
-   Una virgola rappresenta sempre il separatore o il delimitatore di singoli token.  
  
-   Se i singoli token separati non contengono segni di uguale, ogni token viene considerato un argomento del costruttore. Ogni parametro del costruttore deve essere specificato come tipo previsto dalla firma e nell'ordine corretto previsto dalla firma.  
  
    > [!NOTE]
    >  Un processore XAML deve chiamare il costruttore corrispondente al conteggio di argomenti del numero di coppie. Per questo motivo, se si implementa un'estensione di markup personalizzata, non forniscono più costruttori con il numero di argomenti stesso. Il comportamento di un processore XAML se sono presenti più percorsi del costruttore dell'espressione di markup con lo stesso parametro è indefinito, ma è bene aspettarsi che a un processore XAML è consentito generare un'eccezione sull'utilizzo in presenza di questa situazione nelle definizioni dei tipi di estensione di markup.  
  
-   Se i singoli token separati contengono segni di uguale, un processore XAML chiama prima di tutto il costruttore predefinito per l'estensione di markup. Quindi, ogni coppia nome=valore viene interpretata come nome di una proprietà presente nell'estensione di markup e come valore da assegnare alla proprietà.  
  
-   In presenza di un risultato parallelo tra il comportamento del costruttore e il comportamento di impostazione delle proprietà in un'estensione di markup, il comportamento usato non è importante. È prassi più comune usare le coppie *proprietà*`=`*valore* per le estensioni di markup che includono più di una proprietà impostabile, anche solo perché questo comportamento rende il markup più intenzionale e riduce la probabilità di trasporre accidentalmente i parametri del costruttore. Quando si specificano coppie proprietà=valore, queste proprietà possono essere in qualsiasi ordine. Inoltre, non vi è alcuna garanzia che un'estensione di markup fornisca un parametro del costruttore che imposta ognuna delle proprietà impostabili. Ad esempio, <xref:System.Windows.Data.Binding> è un'estensione di markup, con molte proprietà che possono essere impostate tramite l'estensione in *proprietà*`=`*valore* modulo, ma <xref:System.Windows.Data.Binding> supporta solo due costruttori: un costruttore predefinito e uno che imposta un percorso iniziale.  
  
-   Una virgola letterale non può essere passata a un'estensione di markup senza sequenza di escape.  
  
<a name="EscapeSequences"></a>   
## <a name="escape-sequences-and-markup-extensions"></a>Sequenze di escape ed estensioni di markup  
 La gestione degli attributi in un processore XAML usa le parentesi graffe come indicatori di una sequenza di estensioni di markup. È anche possibile produrre un valore di attributo di un carattere di parentesi graffa letterale se necessario, ma immettendo una sequenza di escape tramite una coppia di parentesi graffe vuote seguita dalla parentesi graffa letterale. Vedere [ {} sequenza - estensione di Markup di Escape](../../xaml-services/escape-sequence-markup-extension.md).  
  
<a name="Nesting"></a>   
## <a name="nesting-markup-extensions-in-xaml-usage"></a>Annidamento di estensioni di markup nella sintassi XAML  
 L'annidamento di più estensioni di markup è supportato e viene valutata per prima l'estensione di markup a livello più profondo. Ad esempio, si consideri la sintassi seguente:  
  
```  
<Setter Property="Background"  
  Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}" />  
```  
  
 In questa sintassi l'istruzione `x:Static` viene valutata per prima e restituisce una stringa. Questa stringa viene quindi usata come argomento per `DynamicResource`.  
  
## <a name="markup-extensions-and-property-element-syntax"></a>Estensioni di markup e sintassi di elementi proprietà  
 Se usata come elemento oggetto che immette un valore di elemento proprietà, la classe di un'estensione di markup è visivamente indistinguibile da un tipico elemento oggetto supportato da tipi che può essere usato in XAML. La differenza pratica tra un elemento oggetto tipico e un'estensione di markup è che l'estensione di markup restituisce un valore tipizzato o viene rinviata come espressione. Di conseguenza, i meccanismi per tutti i possibili errori di tipo dei valori di proprietà per l'estensione di markup differiranno, analogamente a come viene gestita una proprietà di data binding in altri modelli di programmazione. Un elemento oggetto comune viene valutato per la corrispondenza dei tipi rispetto alla proprietà di destinazione impostata durante l'analisi del codice XAML.  
  
 La maggior parte delle estensioni di markup, se usate nella sintassi di elementi oggetto per immettere un elemento proprietà, non avrà contenuto né ulteriore sintassi di elementi proprietà al suo interno. In questo modo, è necessario chiudere il tag dell'elemento oggetto, senza fornire elementi figlio. Ogni volta che un elemento oggetto viene rilevato da un processore XAML, viene chiamato il costruttore per la classe, che crea un'istanza dell'oggetto creato dall'elemento analizzato. La classe di un'estensione di markup non è diversa: se si vuole che l'estensione di markup possa essere usata nella sintassi di elementi oggetto, è necessario fornire un costruttore predefinito. Alcune estensioni di markup esistenti hanno almeno un valore di proprietà obbligatorio che deve essere specificato ai fini dell'inizializzazione corretta. In questo caso, il valore di proprietà viene in genere specificato come attributo della proprietà nell'elemento oggetto. Nelle pagine di riferimento [Funzionalità del linguaggio dello spazio dei nomi XAML (x:)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md) e [Estensioni XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md) verranno indicate le estensioni di markup che includono proprietà obbligatorie, insieme ai nomi delle proprietà obbligatorie. Le pagine di riferimento indicano anche se la sintassi degli elementi oggetto o degli attributi non è consentita per una determinata estensione di markup. Un caso interessante riguarda l'[estensione di markup x:Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md), che non può supportare la sintassi di attributi perché il contenuto della matrice deve essere specificata all'interno dei tag come contenuto. Poiché i contenuti della matrice vengono gestiti come oggetti generali, non è possibile usare alcun convertitore di tipi predefiniti per l'attributo. Inoltre, l'[estensione di markup x:Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md) richiede un parametro `type`.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Funzionalità del linguaggio dello spazio dei nomi XAML (x:)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [Estensioni XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [Estensione di markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [Estensione di markup Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)  
 [Estensione del markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)  
 [Estensione di markup x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
