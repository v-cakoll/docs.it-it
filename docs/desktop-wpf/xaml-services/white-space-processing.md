---
title: Elaborazione degli spazi vuoti in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 05f28c9115326424164b92e1b704c52bba31cf35
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071605"
---
# <a name="white-space-processing-in-xaml"></a>Elaborazione degli spazi vuoti in XAML

Le regole del linguaggio per XAML indicano [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] che uno spazio vuoto significativo deve essere elaborato da un'implementazione del processore. Questo articolo documenta queste regole del linguaggio XAML. Documenta inoltre la gestione degli spazi [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] vuoti aggiuntivi definita dall'implementazione del processore XAML e del writer XAML per la serializzazione.

## <a name="white-space-definition"></a>Definizione di spazio vuoto

Coerentemente con XML, gli [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] spazi vuoti in sono spazio, avanzamento riga e tabulazione. Questi corrispondono ai valori Unicode 0020, 000A e 0009 rispettivamente.

## <a name="white-space-normalization"></a>Normalizzazione degli spazi vuoti

Per impostazione predefinita, la seguente [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] normalizzazione degli [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] spazi vuoti si verifica quando un processore elabora un file:

1. I caratteri di avanzamento riga inseriti tra i caratteri dell'Asia orientale vengono rimossi. Per una definizione dei "caratteri dell'Asia orientale", vedere la sezione relativa più avanti in questo argomento.

2. Tutti gli spazi vuoti (spazio, avanzamento riga, tabulazione) vengono convertiti in spazi.

3. Tutti gli spazi consecutivi vengono eliminati e sostituiti da un unico spazio.

4. Uno spazio immediatamente successivo al tag di inizio viene eliminato.

5. Uno spazio immediatamente precedente al tag di fine viene eliminato.

L'"impostazione predefinita" corrisponde allo stato indicato dal valore predefinito dell'attributo [XML:space](xml-space-handling.md) .

## <a name="white-space-in-inner-text-and-string-primitives"></a>Spazio vuoto nel testo interno e primitive di stringa

Le regole di normalizzazione precedenti si applicano al testo interno presente negli elementi XAML. Dopo la normalizzazione, un processore XAML converte qualsiasi testo interno in un tipo appropriato come illustrato di seguito:

- Se il tipo della proprietà non è una raccolta, ma non è nemmeno un tipo <xref:System.Object> , il processore XAML tenta di eseguire la conversione a quel tipo usando il convertitore dei tipi. Una conversione non riuscita causa un errore in fase di compilazione.

- Se il tipo della proprietà è una raccolta e il testo interno è contiguo, (non sono frapposti tag di elementi), il testo interno viene analizzato come singolo oggetto <xref:System.String>. Se il tipo di raccolta non accetta <xref:System.String>, anche in questo caso si verifica un errore in fase di compilazione.

- Se il tipo della proprietà è <xref:System.Object>, il testo interno viene analizzato come un singolo oggetto <xref:System.String>. Se sono frapposti tag di elementi, viene generato un errore in fase di compilazione, in quanto il tipo <xref:System.Object> implica un solo oggetto (<xref:System.String> o diverso).

- Se il tipo della proprietà è una raccolta e il testo interno non è contiguo, la prima sottostringa viene convertita in un oggetto <xref:System.String> e aggiunta come elemento della raccolta. Quindi l'elemento frapposto sarà aggiunto come elemento della raccolta e infine la sottostringa finale (se presente) verrà aggiunta alla raccolta come terzo elemento <xref:System.String> .

## <a name="preserving-white-space"></a>Conservazione degli spazi vuoti

Esistono diverse tecniche per mantenere lo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] spazio vuoto nell'origine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] per la presentazione finale che non sono interessate dalla normalizzazione degli spazi vuoti del processore.

**xml:space'"preserve"**: specifica questo attributo a livello dell'elemento in cui si desidera la conservazione degli spazi vuoti. Vengono così mantenuti tutti gli spazi vuoti, inclusi gli spazi che potrebbero essere aggiunti dalle applicazioni di modifica del codice per allineare gli elementi in modo ottimale, come nidificazione visivamente intuitiva. Tuttavia, il rendering di tali spazi dipende ancora una volta dal modello di contenuto per l'elemento contenitore. Evitare `xml:space="preserve"` di specificare a livello di radice perché la maggior parte dei modelli a oggetti non considera gli spazi vuoti come significativi indipendentemente da come si imposta l'attributo. L'impostazione `xml:space` globalmente può avere conseguenze sulle prestazioni dell'elaborazione XAML, in particolare la serializzazione, in alcune implementazioni. È consigliabile impostare l'attributo solo in modo specifico a livello di elementi che eseguono il rendering di spazi vuoti all'interno di stringhe o sono raccolte significative di spazi vuoti.

**Entità e spazi unificatori:** [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] supporta il posizionamento di qualsiasi entità Unicode all'interno di un modello a oggetti di testo. È possibile utilizzare entità dedicate, ad \#esempio lo spazio unificatore (&160; nella codifica UTF-8). È anche possibile usare controlli rich text che supportano caratteri spazio unificatore. È necessario prestare molta attenzione se si usano entità per simulare caratteristiche di layout, ad esempio il rientro, in quanto l'output di runtime delle entità varierà in base a un maggior numero di fattori rispetto alle funzionalità per ottenere i risultati di rientro in un sistema di layout tipico, ad esempio l'utilizzo corretto di pannelli e margini. Ad esempio, viene eseguito il mapping delle entità ai tipi di carattere, pertanto le dimensioni possono cambiare in funzione della selezione del tipo di carattere operata dall'utente.

## <a name="east-asian-characters"></a>Caratteri dell'Asia orientale

"Caratteri dell'Asia orientale" è definito come un set di intervalli di caratteri Unicode da U-20000 a U-2FFFD e da U-3FFFD a U-3FFFD. Questo sottoinsieme talvolta è denominato anche "ideogrammi CJK". Per altre informazioni, vedere <https://www.unicode.org>.

## <a name="white-space-and-text-content-models"></a>Modelli di contenuto di testo e spazi vuoti

In pratica, preservare lo spazio vuoto è solo preoccupante per un sottoinsieme di tutti i possibili modelli di contenuto. Tale sottoinsieme è composto dai modelli di contenuto che accettano un tipo <xref:System.String> Singleton in una determinata forma, una raccolta <xref:System.String> dedicata o una combinazione di <xref:System.String> e di altri tipi in un raccolta <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .

### <a name="white-space-and-text-content-models-in-wpf"></a>Modelli di contenuto di testo e spazi vuoti in WPFWPFWhite space and text content models in WPFWPF

Per scopo illustrativo, nella restante parte di questa sezione viene fatto riferimento a tipi particolari definiti da WPF. Le funzionalità di gestione degli spazi vuoti descritte in questo articolo sono pertinenti sia ai servizi XAML .NET che a WPF. Per una dimostrazione di questo comportamento, potrebbe essere utile provare a usare parti del markup XAML di WPF, osservare i risultati prodotti in un oggetto grafico, quindi indirizzare di nuovo la serializzazione al markup.

Anche per i modelli di contenuto che possono accettare stringhe, il comportamento predefinito all'interno di questi modelli di contenuto è che qualsiasi spazio vuoto che rimane non viene considerato significativo. Ad esempio, <xref:System.Windows.Controls.ListBox> <xref:System.Collections.IList>accetta un oggetto , ma lo spazio <xref:System.Windows.Controls.ListBoxItem>vuoto (ad esempio gli avanzamenti riga tra ciascuno ) non viene mantenuto e non sottoposto a rendering. Se si tenta di usare i caratteri di avanzamento riga come separatori tra le stringhe per elementi <xref:System.Windows.Controls.ListBoxItem> l'esito sarà negativo; le stringhe separate dai caratteri di avanzamento riga sono considerate come una singola stringa e un singolo elemento.

Le raccolte che trattano gli spazi vuoti come significativi fanno in genere parte del modello di documento dinamico. L'insieme primario che supporta il <xref:System.Windows.Documents.InlineCollection>comportamento di conservazione degli spazi vuoti è . Questa classe di raccolta <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>viene dichiarata con l'oggetto ; Quando questo attributo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] viene trovato, il processore considererà significativi gli spazi vuoti all'interno della raccolta. La combinazione `xml:space="preserve"` di e <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> spazio vuoto all'interno di una raccolta denotata è che tutti gli spazi vuoti vengono mantenuti e sottoposti a rendering. La combinazione `xml:space="default"` di e <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> spazio bianco all'interno di un determina la normalizzazione iniziale degli spazi vuoti descritta in precedenza, che lascia uno spazio in determinate posizioni, e tali spazi vengono mantenuti e sottoposti a rendering. Sarà l'utente a decidere il comportamento più appropriato e a usare `xml:space` in maniera selettiva per abilitare il comportamento desiderato.

Inoltre, alcuni elementi inline che connotano un'interruzione di riga in un modello di documento dinamico non devono introdurre deliberatamente uno spazio aggiuntivo anche in una raccolta significativa di spazi vuoti. Ad esempio, <xref:System.Windows.Documents.LineBreak> l'elemento ha \<lo stesso scopo del tag BR/> in <xref:System.Windows.Documents.LineBreak> HTML e per la leggibilità nel markup, in genere un oggetto è separato da qualsiasi testo successivo da un avanzamento riga creato. Tale avanzamento riga non deve essere normalizzato per l'utilizzo come spazio iniziale nella riga successiva. Per abilitare tale comportamento, <xref:System.Windows.Documents.LineBreak> la definizione della classe per l'elemento applica l'oggetto <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, che viene quindi interpretato dal [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processore per indicare che lo spazio vuoto circostante <xref:System.Windows.Documents.LineBreak> viene sempre tagliato.

## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)XAML overview (WPF)](../fundamentals/xaml.md)
- [XML character entities and XAML](xml-character-entities.md)
- [Xml:gestione dello spazio in XAML](xml-space-handling.md)
