---
title: Linee guida per la progettazione di controlli a cui è possibile applicare degli stili
ms.date: 03/30/2017
helpviewer_keywords:
- style design for controls [WPF]
- controls [WPF], style design
ms.assetid: c52dde45-a311-4531-af4c-853371c4d5f4
ms.openlocfilehash: a5a91d6a1f046b31ff26e769e9fcc1c7516904c8
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662598"
---
# <a name="guidelines-for-designing-stylable-controls"></a>Linee guida per la progettazione di controlli a cui è possibile applicare degli stili

Questo documento offre un riepilogo di una serie di procedure consigliate per la progettazione di un controllo a cui siano facilmente applicabili stili e modelli. Questo è il risultato di molti tentativi ed errori durante l’elaborazione degli stili dei controlli dei temi per il set di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incorporato. La corretta applicazione degli stili è una funzione che non dipende solo dalla corretta progettazione del modello a oggetti ma anche dallo stile stesso. I destinatari di questo documento sono gli autori dei controlli, non gli autori degli stili.

<a name="Terminology"></a>

## <a name="terminology"></a>Terminologia

Per applicazione di stili e modelli si intende un insieme di tecnologie che consente a un autore di controlli di rinviare gli aspetti visivi del controllo allo stile e al modello del controllo. Questo insieme di tecnologie include:

- Stili (inclusi i setter delle proprietà, i trigger e gli storyboard).

- Risorse.

- Modelli di controllo.

- Modelli di dati.

Per un'introduzione all'applicazione di stili e modelli, vedere [Applicazione di stili e modelli](styling-and-templating.md).

<a name="Before_You_Start__Understanding_Your_Control"></a>

## <a name="before-you-start-understanding-your-control"></a>Prima di iniziare: Informazioni sul controllo

Prima di leggere queste linee guida, è importante aver compreso e definito l'uso comune del controllo. L'applicazione degli stili offre spesso una serie di possibilità che non seguono regole precise. I controlli creati per un ampio utilizzo (in un gran numero di applicazioni, da molti sviluppatori) presentano il problema che l'applicazione degli stili può essere usata per apportare modifiche di vasta portata all'aspetto visivo del controllo, al punto che il controllo a cui è stato applicato uno stile potrebbe non corrispondere al progetto dell'autore. Poiché la flessibilità offerta dall'applicazione degli stili è essenzialmente illimitata, è possibile usare il concetto di uso comune per circoscrivere l’ambito delle proprie decisioni.

Per comprendere l'uso comune del controllo, è consigliabile valutare la proposta di valore del controllo. Quali sono i vantaggi che porta il controllo alla tabella e che nessun altro controllo può offrire? L'uso comune non è legato a uno specifico aspetto visivo, ma piuttosto alla filosofia del controllo e a una serie di ragionevoli aspettative per l'uso del controllo stesso. Questa considerazione consente di formulare delle ipotesi sul modello di composizione e sui comportamenti standard del controllo definiti dallo stile. Nel caso di <xref:System.Windows.Controls.ComboBox>, ad esempio, la comprensione di uso comune non sarà è alcuna informazione su se un particolare <xref:System.Windows.Controls.ComboBox> presenta angoli arrotondati, ma in questo caso sarà approfondite del fatto che il <xref:System.Windows.Controls.ComboBox> probabilmente richiede una finestra popup e alcune modalità di attivazione/disattivazione se è aperto.

<a name="General_Guidelines"></a>

## <a name="general-guidelines"></a>Indicazioni generali

- **Non applicare in maniera rigida i contratti dei modelli.** Il contratto del modello di un controllo può includere elementi, comandi, associazioni, trigger o anche impostazioni di proprietà richieste o previste per il corretto funzionamento del controllo.

  - Ridurre al minimo i contratti il più possibile.

  - Eseguire la progettazione con la consapevolezza che in questa fase (ovvero quando si usa uno strumento di progettazione) è normale che il modello del controllo sia in uno stato incompleto. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non offre un'infrastruttura di stato di composizione. La compilazione dei controlli deve essere eseguita con la prospettiva che tale stato possa essere valido.

  - Non generare eccezioni quando un aspetto qualsiasi di un contratto del modello non viene seguito. In tal senso i pannelli non devono generare eccezioni se contengono un numero troppo elevato o troppo esiguo di elementi figlio.

- **Scomporre le funzionalità secondarie in elementi helper del modello.** Ogni controllo deve essere incentrato sulla funzionalità di base e sulla reale proposta di valore e definito in base all'uso comune. A tal fine, usare elementi di composizione e helper all'interno del modello per abilitare comportamenti e visualizzazioni secondari, cioè quei comportamenti e quelle visualizzazioni che non contribuiscono alla funzionalità di base del controllo. Questi elementi sono suddivisi in tre categorie:

  - Gli helper **autonomi** sono controlli o primitive pubblici e riutilizzabili che vengono usati "in modo anonimo" in un modello, vale a dire che l'elemento helper non è in grado di rilevare il controllo al quale è stato applicato lo stile e viceversa. Tecnicamente, qualsiasi elemento può essere di tipo anonimo, ma in questo contesto il termine descrive i tipi che incapsulano funzionalità specializzate per abilitare scenari di destinazione.

  - Gli elementi helper **basati su tipi** sono nuovi tipi che incapsulano funzionalità specializzate. Questi elementi vengono progettati in genere con una gamma di funzionalità più limitata rispetto ai controlli o alle primitive comuni. A differenza degli elementi helper autonomi, quelli basati su tipi sono in grado di rilevare il contesto in cui vengono usati e in genere devono condividere i dati con il controllo del relativo modello di appartenenza.

  - Gli elementi helper **denominati** sono controlli o primitive comuni che un controllo prevede di identificare in base al nome all'interno del relativo modello. A tali elementi viene assegnato un nome noto all'interno del modello, consentendo in questo modo a un controllo di individuare l'elemento e di interagire con esso a livello di codice. In ciascun modello può esistere un solo elemento con un determinato nome.

  La tabella seguente include gli elementi helper attualmente usati dagli stili del controllo (l'elenco non è completo):

  |Elemento|Tipo|Utilizzata da|
  |-------------|----------|-------------|
  |<xref:System.Windows.Controls.ContentPresenter>|Basato su tipi|<xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Frame>e così via (tutti <xref:System.Windows.Controls.ContentControl> tipi)|
  |<xref:System.Windows.Controls.ItemsPresenter>|Basato su tipi|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>e così via (tutti <xref:System.Windows.Controls.ItemsControl> tipi)|
  |<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Con nome|<xref:System.Windows.Controls.ToolBar>|
  |<xref:System.Windows.Controls.Primitives.Popup>|Autonomo|<xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolTip>e così via|
  |<xref:System.Windows.Controls.Primitives.RepeatButton>|Con nome|<xref:System.Windows.Controls.Slider>, <xref:System.Windows.Controls.Primitives.ScrollBar>e così via|
  |<xref:System.Windows.Controls.Primitives.ScrollBar>|Con nome|<xref:System.Windows.Controls.ScrollViewer>|
  |<xref:System.Windows.Controls.ScrollViewer>|Autonomo|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.Frame>e così via|
  |<xref:System.Windows.Controls.Primitives.TabPanel>|Autonomo|<xref:System.Windows.Controls.TabControl>|
  |<xref:System.Windows.Controls.TextBox>|Con nome|<xref:System.Windows.Controls.ComboBox>|
  |<xref:System.Windows.Controls.Primitives.TickBar>|Basato su tipi|<xref:System.Windows.Controls.Slider>|

- **Ridurre al minimo le associazioni o le impostazioni di proprietà richieste specificate dall'utente per gli elementi helper**. Un elemento helper richiede determinate associazioni o impostazioni di proprietà per un corretto funzionamento all'interno del modello di controllo. Tali impostazioni dovrebbero essere indicate, per quanto possibile, dall'elemento helper e dal controllo basato su modelli. Al momento dell'impostazione delle proprietà o della definizione delle associazioni, è necessario prestare attenzione a non eseguire l'override dei valori impostati dall'utente. Di seguito sono indicate le procedure consigliate:

  - Gli elementi helper con nome devono essere identificati dall'elemento padre, che deve stabilire le impostazioni richieste nell'elemento helper.

  - Le impostazioni richieste per gli elementi helper basati su tipi devono essere stabilite direttamente negli elementi stessi. Tale operazione potrebbe richiedere, da parte dell'elemento di supporto, l'esecuzione di una query sul contesto delle informazioni in cui viene usato, incluso l'oggetto `TemplatedParent` (il tipo di controllo del modello in cui viene usato). Ad esempio, <xref:System.Windows.Controls.ContentPresenter> associa automaticamente il `Content` proprietà del relativo `TemplatedParent` a relativo <xref:System.Windows.Controls.ContentPresenter.Content%2A> proprietà quando viene utilizzata un <xref:System.Windows.Controls.ContentControl> tipo derivato.

  - Non è possibile ottimizzare allo stesso modo gli elementi helper autonomi, perché, per definizione, l'elemento helper e l'elemento padre non sono in grado di rilevarsi a vicenda.

- **Usare la proprietà Name contrassegnare gli elementi all'interno di un modello**. Un controllo che deve individuare un elemento dello stile e accedervi a livello di codice, dovrà usare la proprietà `Name` e il paradigma `FindName`. Se l'elemento non viene trovato, il controllo non dovrà generare un'eccezione, ma disabilitare in modo normale e senza visualizzare messaggi la funzionalità in cui tale elemento era richiesto.

- **Usare le procedure consigliate per esprimere lo stato e il comportamento del controllo in uno stile.** Di seguito è riportato un elenco ordinato delle procedure consigliate per indicare le modifiche e il comportamento dello stato del controllo in uno stile. È consigliabile usare il primo elemento dell'elenco per abilitare lo scenario.

  1. Associazione di proprietà. Esempio: associazione tra <xref:System.Windows.Controls.ComboBox.IsDropDownOpen%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A?displayProperty=nameWithType>.

  2. Modifiche delle proprietà attivate o animazioni delle proprietà. Esempio: il passaggio del mouse lo stato di un <xref:System.Windows.Controls.Button>.

  3. Comando. Esempio: <xref:System.Windows.Controls.Primitives.ScrollBar.LineUpCommand>  /  <xref:System.Windows.Controls.Primitives.ScrollBar.LineDownCommand> in <xref:System.Windows.Controls.Primitives.ScrollBar>.

  4. Elementi helper autonomi. Esempio: <xref:System.Windows.Controls.Primitives.TabPanel> in <xref:System.Windows.Controls.TabControl>.

  5. Tipi di helper basati su tipi. Esempio: <xref:System.Windows.Controls.ContentPresenter> nelle <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Primitives.TickBar> in <xref:System.Windows.Controls.Slider>.

  6. Elementi helper con nome. Esempio: <xref:System.Windows.Controls.TextBox> in <xref:System.Windows.Controls.ComboBox>.

  7. Eventi propagati da tipi di supporto con nome. Se si è in ascolto di eventi propagati da un elemento dello stile, è consigliabile richiedere che l'elemento che ha generato l'evento possa venire identificato in modo univoco. Esempio: <xref:System.Windows.Controls.Primitives.Thumb> in <xref:System.Windows.Controls.ToolBar>.

  8. Comportamento di `OnRender` personalizzato. Esempio: <xref:Microsoft.Windows.Themes.ButtonChrome> in <xref:System.Windows.Controls.Button>.

- **Usare i trigger degli stili (anziché i trigger dei modelli) con moderazione**. I trigger che hanno effetto sulle proprietà degli elementi del modello devono essere dichiarati nel modello. I trigger che hanno effetto sulle proprietà del controllo (eccetto `TargetName`) possono essere dichiarati nello stile, a meno che la modifica del modello non comporti l'eliminazione del trigger.

- **Essere coerenti con i modelli di applicazione di stili esistenti.** Spesso esistono diversi modi per risolvere un problema. Essere consapevoli e, se possibile, essere coerenti con i modelli di applicazione dello stile del controllo esistenti. Ciò è particolarmente importante per i controlli che derivano dallo stesso tipo di base (ad esempio, <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.Primitives.RangeBase>e così via).

- **Esporre le proprietà per abilitare scenari di personalizzazione comuni senza applicare nuovamente i modelli**. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non supporta parti personalizzabili o collegabili; pertanto, l'utente di un controllo avrà a disposizione soltanto due metodi per la personalizzazione: l'impostazione diretta delle proprietà o l'impostazione delle proprietà tramite gli stili. È consigliabile pertanto di limitare il numero di proprietà destinate a scenari di personalizzazione molto comuni, ad alta priorità, che richiederebbero altrimenti una nuova applicazione dei modelli. Di seguito sono riportate le procedure consigliate per stabilire il momento e il metodo adatti per abilitare gli scenari di personalizzazione:

  - Le personalizzazioni molto comuni devono essere esposte come proprietà nel controllo e usate dal modello.

  - Le personalizzazioni meno comuni (anche se non rare) devono essere esposte come proprietà associate e usate dal modello.

  - È accettabile che le personalizzazioni note ma rare richiedano una nuova applicazione di modelli.

<a name="Theme_Considerations"></a>

## <a name="theme-considerations"></a>Considerazioni sui temi

- **Gli stili dei temi dovrebbero avere una semantica delle proprietà coerente in tutti i temi, tuttavia non offrono alcuna garanzia**. Come parte della documentazione, il controllo dovrebbe includere un documento con la descrizione della semantica delle proprietà del controllo, vale a dire il "significato" di una proprietà per un controllo. Ad esempio, il <xref:System.Windows.Controls.ComboBox> controllo deve definire il significato del <xref:System.Windows.Controls.Control.Background%2A> proprietà all'interno di <xref:System.Windows.Controls.ComboBox>. Gli stili predefiniti per il controllo dovrebbero attenersi alla semantica definita in tale documento per tutti i temi. Gli utenti del controllo, d'altra parte, dovrebbero essere consapevoli del fatto che la semantica delle proprietà può variare da tema a tema. In alcuni casi, potrebbe non essere possibile esprimere una determinata proprietà per i vincoli visivi richiesti da un determinato tema. Ad esempio, nel tema Classico non è disponibile un singolo bordo a cui applicare `Thickness` per molti controlli.

- **Gli stili dei temi non devono necessariamente avere una semantica dei trigger coerente in tutti i temi**. Il comportamento esposto da uno stile del controllo tramite trigger o animazioni può variare da tema a tema. Gli utenti del controllo dovrebbero essere consapevoli che un controllo non impiega necessariamente lo stesso meccanismo per ottenere un comportamento specifico in tutti i temi. Un tema, ad esempio, può usare un'animazione per esprimere il comportamento al passaggio del mouse mentre un altro tema usa un trigger. Nei controlli personalizzati è pertanto possibile che si verifichino incoerenze nella conservazione di un comportamento. La modifica della proprietà dello sfondo, ad esempio, potrebbe non avere effetto sullo stato del controllo al passaggio del mouse, se questo viene espresso mediante un trigger. Se lo stato al passaggio del mouse viene tuttavia implementato mediante un'animazione, la modifica dello sfondo potrebbe interrompere l'animazione e quindi la transizione di stato.

- **Gli stili dei temi non devono necessariamente presentare una semantica dei "layout" coerente in tutti i temi**. L'uso dello stile predefinito, ad esempio, non deve garantire che un controllo abbia le stesse dimensioni in tutti i temi o che il contenuto abbia gli stessi margini o la stessa spaziatura interna in tutti i temi.

## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](styling-and-templating.md)
- [Cenni preliminari sulla modifica di controlli](control-authoring-overview.md)
