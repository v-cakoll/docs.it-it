---
title: L'elaborazione in XAML gli spazi vuoti
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 89f8a4675b3edc23913549bc24f0d9ae16917519
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216799"
---
# <a name="white-space-processing-in-xaml"></a>L'elaborazione in XAML gli spazi vuoti
Le regole del linguaggio per XAML di stato che lo spazio vuoto significativo deve essere elaborato da un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] l'implementazione del processore. In questo argomento vengono illustrate queste regole del linguaggio XAML, Illustra inoltre la gestione degli spazi vuoti aggiuntivi definita dal [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementazione del processore XAML e writer XAML per la serializzazione.  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>Definizione di spazio vuoto  
 Coerente con [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)], i caratteri spazi vuoti in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sono spazi, avanzamento riga e della scheda. Questi corrispondono per rispettivamente ai valori [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] 0020, 000A e 0009.  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>Normalizzazione degli spazi vuoti  
 Per impostazione predefinita la normalizzazione di spazi vuoti seguente si verifica quando un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processi di processore un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file:  
  
1.  I caratteri di avanzamento riga inseriti tra i caratteri dell'Asia orientale vengono rimossi. Per una definizione dei "caratteri dell'Asia orientale", vedere la sezione relativa più avanti in questo argomento.  
  
2.  Tutti i caratteri di spazio vuoto (spazio, avanzamento riga, scheda) vengono convertiti in spazi.  
  
3.  Tutti gli spazi consecutivi vengono eliminati e sostituiti da un unico spazio.  
  
4.  Uno spazio immediatamente successivo al tag di inizio viene eliminato.  
  
5.  Uno spazio immediatamente precedente al tag di fine viene eliminato.  
  
 L'"impostazione predefinita" corrisponde allo stato indicato dal valore predefinito dell'attributo [XML:space](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md) .  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>Spazi vuoti nel testo interno e primitive di stringa  
 Le regole di normalizzazione precedenti si applicano al testo interno presente negli elementi XAML. Dopo la normalizzazione, un processore XAML converte qualsiasi testo interno in un tipo appropriato come illustrato di seguito:  
  
-   Se il tipo della proprietà non è una raccolta, ma non è nemmeno un tipo <xref:System.Object> , il processore XAML tenta di eseguire la conversione a quel tipo usando il convertitore dei tipi. Una conversione non riuscita causa un errore in fase di compilazione.  
  
-   Se il tipo della proprietà è una raccolta e il testo interno è contiguo, (non sono frapposti tag di elementi), il testo interno viene analizzato come singolo oggetto <xref:System.String>. Se il tipo di raccolta non accetta <xref:System.String>, anche in questo caso si verifica un errore in fase di compilazione.  
  
-   Se il tipo della proprietà è <xref:System.Object>, il testo interno viene analizzato come un singolo oggetto <xref:System.String>. Se sono frapposti tag di elementi, viene generato un errore in fase di compilazione, in quanto il tipo <xref:System.Object> implica un solo oggetto (<xref:System.String> o diverso).  
  
-   Se il tipo della proprietà è una raccolta e il testo interno non è contiguo, la prima sottostringa viene convertita in un oggetto <xref:System.String> e aggiunta come elemento della raccolta. Quindi l'elemento frapposto sarà aggiunto come elemento della raccolta e infine la sottostringa finale (se presente) verrà aggiunta alla raccolta come terzo elemento <xref:System.String> .  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>Conservare lo spazio vuoto  
 Esistono diverse tecniche per la conservazione di spazi vuoti nell'origine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] per la presentazione conclusiva che non sono interessati da [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] normalizzazione di spazi vuoti del processore.  
  
 **XML: space = "preserve"**: specificare questo attributo a livello di elemento quando è richiesta la conservazione degli spazi vuoti. Vengono così mantenuti tutti gli spazi vuoti, inclusi gli spazi che potrebbero essere aggiunti dalle applicazioni di modifica del codice per allineare gli elementi in modo ottimale, come nidificazione visivamente intuitiva. Tuttavia, il rendering di tali spazi dipende ancora una volta dal modello di contenuto per l'elemento contenitore. Evitare di specificare `xml:space="preserve"` a livello di radice spazio significativo indipendentemente dal modo in cui si impostato l'attributo perché la maggior parte dei modelli a oggetti non considera il bianchi. L'impostazione `xml:space` globalmente può avere conseguenze sulle prestazioni dell'elaborazione XAML, in particolare la serializzazione, in alcune implementazioni. È invece consigliabile impostare solo l'attributo in modo specifico a livello di elementi che consentono di eseguire il rendering di spazi vuoti all'interno di stringhe, o sono raccolte di spazi vuoti significative.  
  
 **Entità e spazi unificatori**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] supporta il posizionamento di qualsiasi entità [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] all'interno di un modello di testo a oggetti. È possibile usare entità dedicate quali gli spazi unificatori (&\#160; nella codifica UTF-8). È anche possibile usare controlli rich text che supportano caratteri spazio unificatore. È necessario prestare molta attenzione se si usano entità per simulare caratteristiche di layout, ad esempio il rientro, in quanto l'output di runtime delle entità varierà in base a un maggior numero di fattori rispetto alle funzionalità per ottenere i risultati di rientro in un sistema di layout tipico, ad esempio l'utilizzo corretto di pannelli e margini. Ad esempio, viene eseguito il mapping delle entità ai tipi di carattere, pertanto le dimensioni possono cambiare in funzione della selezione del tipo di carattere operata dall'utente.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Caratteri dell'Asia orientale  
 I "caratteri dell'Asia orientale" vengono definiti come un set di caratteri [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] compresi tra U+20000 a U+2FFFD e tra U+30000 a U+3FFFD. Questo sottoinsieme talvolta è denominato anche "ideogrammi CJK". Per altre informazioni, vedere [http://www.unicode.org](http://www.unicode.org/).  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>Gli spazi vuoti e contenuti modelli di testo  
 In pratica, conservazione di spazi vuoti riguarda solo un subset di tutti i possibili modelli di contenuto. Tale sottoinsieme è composto dai modelli di contenuto che accettano un tipo <xref:System.String> Singleton in una determinata forma, una raccolta <xref:System.String> dedicata o una combinazione di <xref:System.String> e di altri tipi in un raccolta <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>Modelli di contenuto di spazi vuoti e testo in WPF  
 Per scopo illustrativo, nella restante parte di questa sezione viene fatto riferimento a tipi particolari definiti da WPF. Le funzionalità di gestione degli spazi vuoti che sono descritte in questo argomento sono generalmente pertinenti ai servizi XAML di .NET Framework sia WPF. Per una dimostrazione di questo comportamento, potrebbe essere utile provare a usare parti del markup XAML di WPF, osservare i risultati prodotti in un oggetto grafico, quindi indirizzare di nuovo la serializzazione al markup.  
  
 Anche per i modelli di contenuto che accettano le stringhe, il comportamento predefinito entro questi modelli di contenuto è che gli spazi vuoti che rimane non viene considerato come significativi. Ad esempio, <xref:System.Windows.Controls.ListBox> accetta un <xref:System.Collections.IList>, ma lo spazio vuoto (ad esempio gli avanzamenti riga tra ogni <xref:System.Windows.Controls.ListBoxItem>) non viene mantenuto e non sottoposti a rendering. Se si tenta di usare i caratteri di avanzamento riga come separatori tra le stringhe per elementi <xref:System.Windows.Controls.ListBoxItem> l'esito sarà negativo; le stringhe separate dai caratteri di avanzamento riga sono considerate come una singola stringa e un singolo elemento.  
  
 Le raccolte che trattano gli spazi vuoti come significativi sono in genere parte del modello di documento dinamico. La raccolta primaria che supporta il comportamento di conservazione degli spazi vuoti è <xref:System.Windows.Documents.InlineCollection>. Questa classe di raccolta viene dichiarata con la <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; quando questo attributo viene trovato, il [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processore tratterà spazi vuoti all'interno della raccolta come significativi. La combinazione delle `xml:space="preserve"` e gli spazi vuoti all'interno di un <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> insieme denotato che tutti gli spazi vuoti viene mantenuto e viene eseguito il rendering. La combinazione delle `xml:space="default"` e gli spazi vuoti all'interno di un <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> causa la normalizzazione di spazi vuoti inizio descritta in precedenza, in modo da lasciare uno spazio vuoto in determinate posizioni e tali spazi è conservati e viene eseguito il rendering. Sarà l'utente a decidere il comportamento più appropriato e a usare `xml:space` in maniera selettiva per abilitare il comportamento desiderato.  
  
 Inoltre, determinati elementi inline che implicano un'interruzione in un modello di documento dinamico devono evitare l'introduzione di uno spazio aggiuntivo persino in un insieme significativo di spazi vuoti. Ad esempio, il <xref:System.Windows.Documents.LineBreak> elemento ha lo stesso scopo la \<BR / > tag in [!INCLUDE[TLA2#tla_html](../../../includes/tla2sharptla-html-md.md)]e per migliorare la leggibilità nel markup, in genere un <xref:System.Windows.Documents.LineBreak> è separato dal testo successivo da un avanzamento di riga creata. Tale avanzamento riga non deve essere normalizzato per l'utilizzo come spazio iniziale nella riga successiva. Per abilitare questo comportamento, la definizione di classe per il <xref:System.Windows.Documents.LineBreak> elemento si applica il <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, che viene quindi interpretato dalle [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processore per indicare che lo spazio vuoto che circonda <xref:System.Windows.Documents.LineBreak> sarà sempre tagliato.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Entità carattere XML e XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [XML: space in XAML gestisce](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md)
