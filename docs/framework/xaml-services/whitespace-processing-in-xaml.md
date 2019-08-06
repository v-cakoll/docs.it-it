---
title: Elaborazione degli spazi vuoti in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 077f19690d204d3b8f682d01c51feee9e9edbfd4
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796819"
---
# <a name="white-space-processing-in-xaml"></a>Elaborazione degli spazi vuoti in XAML
Le regole del linguaggio per lo stato XAML che gli spazi vuoti significativi devono essere [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] elaborati da un'implementazione del processore. In questo argomento vengono illustrate queste regole del linguaggio XAML, Viene inoltre documentata la gestione di spazi vuoti aggiuntiva definita [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] dall'implementazione del processore XAML e del writer XAML per la serializzazione.  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>Definizione di spazio vuoto  
 Coerente con [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]gli spazi vuoti in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sono spazi, avanzamento riga e tabulazione. Questi corrispondono per rispettivamente ai valori [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] 0020, 000A e 0009.  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>Normalizzazione degli spazi vuoti  
 Per impostazione predefinita, la normalizzazione degli spazi vuoti seguente [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] si verifica quando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] un processore elabora un file:  
  
1. I caratteri di avanzamento riga inseriti tra i caratteri dell'Asia orientale vengono rimossi. Per una definizione dei "caratteri dell'Asia orientale", vedere la sezione relativa più avanti in questo argomento.  
  
2. Tutti i caratteri di spazio vuoto (spazio, avanzamento riga, tabulazione) vengono convertiti in spazi.  
  
3. Tutti gli spazi consecutivi vengono eliminati e sostituiti da un unico spazio.  
  
4. Uno spazio immediatamente successivo al tag di inizio viene eliminato.  
  
5. Uno spazio immediatamente precedente al tag di fine viene eliminato.  
  
 L'"impostazione predefinita" corrisponde allo stato indicato dal valore predefinito dell'attributo [XML:space](xml-space-handling-in-xaml.md) .  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>Spazi vuoti nel testo interno e primitive di stringa  
 Le regole di normalizzazione precedenti si applicano al testo interno presente negli elementi XAML. Dopo la normalizzazione, un processore XAML converte qualsiasi testo interno in un tipo appropriato come illustrato di seguito:  
  
- Se il tipo della proprietà non è una raccolta, ma non è nemmeno un tipo <xref:System.Object> , il processore XAML tenta di eseguire la conversione a quel tipo usando il convertitore dei tipi. Una conversione non riuscita causa un errore in fase di compilazione.  
  
- Se il tipo della proprietà è una raccolta e il testo interno è contiguo, (non sono frapposti tag di elementi), il testo interno viene analizzato come singolo oggetto <xref:System.String>. Se il tipo di raccolta non accetta <xref:System.String>, anche in questo caso si verifica un errore in fase di compilazione.  
  
- Se il tipo della proprietà è <xref:System.Object>, il testo interno viene analizzato come un singolo oggetto <xref:System.String>. Se sono frapposti tag di elementi, viene generato un errore in fase di compilazione, in quanto il tipo <xref:System.Object> implica un solo oggetto (<xref:System.String> o diverso).  
  
- Se il tipo della proprietà è una raccolta e il testo interno non è contiguo, la prima sottostringa viene convertita in un oggetto <xref:System.String> e aggiunta come elemento della raccolta. Quindi l'elemento frapposto sarà aggiunto come elemento della raccolta e infine la sottostringa finale (se presente) verrà aggiunta alla raccolta come terzo elemento <xref:System.String> .  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>Conservazione degli spazi vuoti  
 Esistono diverse tecniche per preservare gli spazi vuoti nell'origine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] per la presentazione finale che non sono interessati dalla normalizzazione degli [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] spazi vuoti del processore.  
  
 **xml:space="preserve"** : Specificare questo attributo al livello dell'elemento in cui si desidera mantenere lo spazio vuoto. Vengono così mantenuti tutti gli spazi vuoti, inclusi gli spazi che potrebbero essere aggiunti dalle applicazioni di modifica del codice per allineare gli elementi in modo ottimale, come nidificazione visivamente intuitiva. Tuttavia, il rendering di tali spazi dipende ancora una volta dal modello di contenuto per l'elemento contenitore. Evitare di `xml:space="preserve"` specificare al livello radice, perché la maggior parte dei modelli a oggetti non considera gli spazi vuoti come significativi, indipendentemente dalla modalità di impostazione dell'attributo. L'impostazione `xml:space` globalmente può avere conseguenze sulle prestazioni dell'elaborazione XAML, in particolare la serializzazione, in alcune implementazioni. È consigliabile impostare solo l'attributo specificamente al livello degli elementi che eseguono il rendering degli spazi vuoti all'interno delle stringhe o sono raccolte significative di spazi vuoti.  
  
 **Entità e spazi unificatori**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] supporta il posizionamento di qualsiasi entità [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] all'interno di un modello di testo a oggetti. È possibile usare entità dedicate, ad esempio lo spazio unificatore (&\#160; nella codifica UTF-8). È anche possibile usare controlli rich text che supportano caratteri spazio unificatore. È necessario prestare molta attenzione se si usano entità per simulare caratteristiche di layout, ad esempio il rientro, in quanto l'output di runtime delle entità varierà in base a un maggior numero di fattori rispetto alle funzionalità per ottenere i risultati di rientro in un sistema di layout tipico, ad esempio l'utilizzo corretto di pannelli e margini. Ad esempio, viene eseguito il mapping delle entità ai tipi di carattere, pertanto le dimensioni possono cambiare in funzione della selezione del tipo di carattere operata dall'utente.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Caratteri asiatici orientali  
 I "caratteri dell'Asia orientale" vengono definiti come un set di caratteri [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] compresi tra U+20000 a U+2FFFD e tra U+30000 a U+3FFFD. Questo sottoinsieme talvolta è denominato anche "ideogrammi CJK". Per altre informazioni, vedere <https://www.unicode.org>.  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>Spazi vuoti e modelli di contenuto di testo  
 In pratica, la conservazione degli spazi vuoti riguarda solo un subset di tutti i possibili modelli di contenuto. Tale sottoinsieme è composto dai modelli di contenuto che accettano un tipo <xref:System.String> Singleton in una determinata forma, una raccolta <xref:System.String> dedicata o una combinazione di <xref:System.String> e di altri tipi in un raccolta <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>Spazi vuoti e modelli di contenuto di testo in WPF  
 Per scopo illustrativo, nella restante parte di questa sezione viene fatto riferimento a tipi particolari definiti da WPF. Le funzionalità di gestione degli spazi vuoti descritte in questo argomento sono in genere pertinenti sia per .NET Framework servizi XAML che per WPF. Per una dimostrazione di questo comportamento, potrebbe essere utile provare a usare parti del markup XAML di WPF, osservare i risultati prodotti in un oggetto grafico, quindi indirizzare di nuovo la serializzazione al markup.  
  
 Anche per i modelli di contenuto che possono assumere stringhe, il comportamento predefinito all'interno di questi modelli di contenuto è che gli spazi vuoti rimanenti non vengono considerati significativi. Ad esempio, <xref:System.Windows.Controls.ListBox> accetta un <xref:System.Collections.IList>oggetto, ma lo spazio vuoto (ad esempio avanzamento riga tra <xref:System.Windows.Controls.ListBoxItem>ogni) non viene mantenuto e non viene sottoposto a rendering. Se si tenta di usare i caratteri di avanzamento riga come separatori tra le stringhe per elementi <xref:System.Windows.Controls.ListBoxItem> l'esito sarà negativo; le stringhe separate dai caratteri di avanzamento riga sono considerate come una singola stringa e un singolo elemento.  
  
 Le raccolte che trattano gli spazi vuoti come significativi sono in genere parte del modello di documento dinamico. La raccolta primaria che supporta il comportamento di mantenimento degli spazi <xref:System.Windows.Documents.InlineCollection>vuoti è. Questa classe di raccolte viene dichiarata con <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>. quando viene trovato questo attributo, il [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processore tratterà gli spazi vuoti all'interno della raccolta come significativi. La combinazione di `xml:space="preserve"` e di uno spazio vuoto <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> all'interno di una raccolta denotata è che tutti gli spazi vuoti vengono conservati e sottoposti a rendering. La combinazione di `xml:space="default"` e lo spazio vuoto all' <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> interno di un oggetto determina la normalizzazione dello spazio vuoto iniziale descritta in precedenza, che lascia uno spazio in determinate posizioni e tali spazi vengono conservati e sottoposti a rendering. Sarà l'utente a decidere il comportamento più appropriato e a usare `xml:space` in maniera selettiva per abilitare il comportamento desiderato.  
  
 Inoltre, alcuni elementi inline che connotano un LineBreak in un modello di documento dinamico non devono introdurre intenzionalmente uno spazio aggiuntivo anche in una raccolta significativa di spazi vuoti. Ad esempio, l' <xref:System.Windows.Documents.LineBreak> elemento ha lo stesso scopo del tag \<br/> in HTML e per migliorare la leggibilità nel markup, in genere un <xref:System.Windows.Documents.LineBreak> è separato dal testo successivo da un avanzamento riga creato. Tale avanzamento riga non deve essere normalizzato per l'utilizzo come spazio iniziale nella riga successiva. Per abilitare questo comportamento, la definizione della classe per <xref:System.Windows.Documents.LineBreak> l'elemento applica <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>l'oggetto, che [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] viene quindi interpretato dal processore per indicare che gli spazi <xref:System.Windows.Documents.LineBreak> vuoti circostanti vengono sempre eliminati.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Entità carattere XML e XAML](xml-character-entities-and-xaml.md)
- [gestione di XML: Space in XAML](xml-space-handling-in-xaml.md)
