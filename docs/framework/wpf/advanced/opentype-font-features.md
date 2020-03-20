---
title: Funzionalità dei tipi di carattere OpenType
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: 52fe73bccd625c9508b398874fd6b075af2445e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186812"
---
# <a name="opentype-font-features"></a>Funzionalità dei tipi di carattere OpenType

In questo argomento viene fornita una panoramica di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]alcune delle funzionalità principali della tecnologia dei tipi di carattere OpenType in .  
  
<a name="overview"></a>
## <a name="opentype-font-format"></a>Formato dei tipi di carattere OpenType  
 Il formato del carattere OpenType è un'estensione del formato di carattere TrueType®, aggiungendo il supporto per i dati dei caratteri PostScript. Il formato di carattere OpenType è stato sviluppato congiuntamente da Microsoft e Adobe Corporation. I tipi di carattere OpenType e i servizi del sistema operativo che supportano i tipi di carattere OpenType forniscono agli utenti un modo semplice per installare e utilizzare i tipi di carattere, indipendentemente dal fatto che i tipi di carattere contengano strutture TrueType o CFF (PostScript).  
  
 Il formato dei tipi di carattere OpenType risolve le seguenti sfide per gli sviluppatori:  
  
- Supporto multipiattaforma più esteso.  
  
- Supporto migliore per set di caratteri internazionali.  
  
- Migliore protezione per i dati dei tipi di carattere.  
  
- Dimensioni di file minori per rendere più efficiente la distribuzione dei tipi di carattere.  
  
- Supporto più ampio per il controllo tipografico avanzato.  
  
> [!NOTE]
> Windows SDK contiene un set di tipi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] carattere OpenType di esempio che è possibile utilizzare con le applicazioni. Questi tipi di carattere offrono la maggior parte delle funzionalità descritte nelle altre sezioni di questo argomento. Per ulteriori informazioni, consultate Esempio di pacchetto di [caratteri OpenType](sample-opentype-font-pack.md).  
  
Per informazioni dettagliate sul formato del tipo di carattere OpenType, vedere la [specifica OpenType](https://docs.microsoft.com/typography/opentype/spec/).  
  
### <a name="advanced-typographic-extensions"></a>Estensioni tipografiche avanzate  
 Le tabelle tipografiche avanzate (tabelle Layout OpenType) estendono la funzionalità dei tipi di carattere con i contorni TrueType o CFF. I tipi di carattere OpenType Layout contengono informazioni aggiuntive che estendono le funzionalità dei tipi di carattere per supportare la tipografia internazionale di alta qualità. La maggior parte dei font OpenType espone solo un sottoinsieme delle funzionalità OpenType totali disponibili. I tipi di carattere OpenType forniscono le funzionalità seguenti.  
  
- Mapping avanzato tra caratteri e glifi che supportano legature, formati posizionali, glifi alternativi e altre sostituzioni di tipi di carattere.  
  
- Supporto per posizionamento bidimensionale e collegamento di glifi.  
  
- Informazioni esplicite su script e lingua contenute in un carattere, per permettere a un'applicazione di elaborazione del testo di modificare il proprio comportamento di conseguenza.  
  
 Le tabelle di layout OpenType sono descritte in modo più dettagliato nella sezione ["Tabelle dei file](https://www.microsoft.com/typography/otspec/otff.htm) di font" della specifica OpenType.  
  
 Nella parte restante di questa panoramica vengono presentate l'ampiezza e la flessibilità di <xref:System.Windows.Documents.Typography> alcune delle funzionalità OpenType visivamente interessanti esposte dalle proprietà dell'oggetto. Per altre informazioni su questo oggetto, vedere [Classe Typography](#typography_class).  
  
<a name="variants"></a>
## <a name="variants"></a>Varianti  
 Le varianti vengono usate per eseguire il rendering di stili tipografici diversi, come gli apici e i pedici.  
  
### <a name="superscripts-and-subscripts"></a>Apici e pedici  
 La <xref:System.Windows.Documents.Typography.Variants%2A> proprietà consente di impostare i valori di apice e pedice per un tipo di carattere OpenType.  
  
 Il testo seguente mostra apici per il tipo di carattere Palatino Linotype.  
  
 ![Testo con apici OpenType](./media/opentype-font-features/opentype-superscripts.gif "Testo con apici OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire apici per <xref:System.Windows.Documents.Typography> il tipo di carattere Palatino Linotype, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 Il testo seguente mostra pedici per il tipo di carattere Palatino Linotype.  
  
 ![Testo con pedici OpenType](./media/opentype-font-features/opentype-subscripts.gif "Testo con pedici OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire pedici <xref:System.Windows.Documents.Typography> per il tipo di carattere Palatino Linotype, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Uso decorativo di apici e pedici  
 È anche possibile usare apici e pedici per creare effetti decorativi di testo con maiuscole e minuscole miste. Il testo seguente mostra testo in apice e pedice per il tipo di carattere Palatino Linotype. Si noti che questa formattazione non influisce sulle maiuscole.  
  
 ![Testo con apici e pedici OpenType](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Testo con apici e pedici OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire apici <xref:System.Windows.Documents.Typography> e pedici per un tipo di carattere, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>
## <a name="capitals"></a>Caratteri maiuscoli  
 I caratteri maiuscoli sono un set di caratteri tipografici per il rendering del testo in glifi in stile maiuscolo. In genere, quando il testo viene visualizzato come tutto maiuscolo, la spaziatura tra le lettere può risultare insufficiente, mentre lo spessore e le proporzioni delle lettere possono apparire eccessivi. OpenType supporta una serie di formati di stile per le maiuscole, tra cui maiuscoletto, maiuscoletto, titolazione e spaziatura tra maiuscole. Questi formati permettono di controllare l'aspetto dei caratteri maiuscoli.  
  
 Il testo seguente visualizza lettere maiuscole standard per il tipo di carattere Pescadero, seguite da lettere in stile "SmallCaps" e "AllSmallCaps". In questo caso, viene usata la stessa dimensione di carattere per tutte e tre le parole.  
  
 ![Testo con caratteri maiuscoli OpenType](./media/opentype-font-features/opentype-capitals.gif "Testo con caratteri maiuscoli OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire le maiuscole <xref:System.Windows.Documents.Typography> per il tipo di carattere Pescadero, utilizzando le proprietà dell'oggetto. Quando si usa il formato "SmallCaps", tutte le iniziali maiuscole vengono ignorate.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Caratteri maiuscoli di titolazione  
 I caratteri maiuscoli di titolazione hanno spessore e proporzioni minori e sono progettati per conferire un aspetto più elegante rispetto alle lettere maiuscole normali. I caratteri maiuscoli di titolazione vengono in genere usati con dimensioni di carattere maggiori come intestazioni. Il testo seguente mostra caratteri maiuscoli normali e di titolazione per il tipo di carattere Pescadero. Notare la larghezza minore delle aste nel testo della seconda riga.  
  
 ![Testo con caratteri maiuscoli di titolazione OpenType](./media/opentype-font-features/opentype-titling-capitals.gif "Testo con caratteri maiuscoli per i titoli OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire le lettere maiuscole per <xref:System.Windows.Documents.Typography> il tipo di carattere Pescadero, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Spaziatura tra caratteri maiuscoli  
 La spaziatura tra caratteri maiuscoli è una funzionalità che permette di aggiungere più spazio quando si usano caratteri tutti maiuscoli nel testo. Le lettere maiuscole sono in genere progettate per essere combinate con lettere minuscole. La gradevole spaziatura tra una lettera maiuscola e una minuscola può risultare troppo ridotta quando si usano lettere tutte maiuscole. Il testo seguente mostra una spaziatura normale e una tra caratteri maiuscoli per il tipo di carattere Pescadero.  
  
 ![Testo con spaziatura tra caratteri maiuscoli OpenType](./media/opentype-font-features/opentype-capital-spacing.gif "Testo con spaziatura tra caratteri maiuscoli OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire la spaziatura di capitale per il tipo di carattere Pescadero, utilizzando le proprietà dell'oggetto. <xref:System.Windows.Documents.Typography>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>
## <a name="ligatures"></a>Legature  
 Le legature sono due o più glifi uniti a formare un singolo glifo per creare un testo più leggibile o gradevole. I font OpenType supportano quattro tipi di legature:  
  
- **Legature standard**. Progettate per migliorare la leggibilità. Le legature standard includono "fi", "fl" e "ff".  
  
- **Legature contestuali**. Progettate per migliorare la leggibilità applicando un accostamento migliore tra i caratteri che costituiscono la legatura.  
  
- **Legature discrezionali**. Progettate per scopi ornamentali e non appositamente ideate per favorire la leggibilità.  
  
- **Legature storiche**. Progettate per testi di tipo storico e non appositamente ideate per favorire la leggibilità.  
  
 Il testo seguente mostra glifi con legature standard per il tipo di carattere Pericles.  
  
 ![Testo con legature standard OpenType](./media/opentype-font-features/opentype-standard-ligatures.gif "Testo con legature standard OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire glifi di legature standard <xref:System.Windows.Documents.Typography> per il tipo di carattere Pericles, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 Il testo seguente mostra glifi con legature discrezionali per il tipo di carattere Pericles.  
  
 ![Testo con legature discrezionali OpenType](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Testo con legature discrezionali OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire glifi di legature discrezionali per il tipo di carattere Pericles, utilizzando le proprietà dell'oggetto. <xref:System.Windows.Documents.Typography>  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 Per impostazione predefinita, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] i font OpenType in abilitano le legature standard. Se si usa, ad esempio, il tipo di carattere Palatino Linotype, le legature standard "fi", "ff" e "fl" verranno visualizzate come glifi di caratteri combinati. Si noti che nella coppia di caratteri per ogni legatura standard i caratteri si toccano tra loro.  
  
 ![Testo con legature standard OpenType con Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Testo con legature standard OpenType con Palatino Linotype")

 Tuttavia, è possibile disabilitare le funzionalità di legatura standard in modo che una legatura standard come "ff" venga visualizzata come due glifi separati invece che come glifo di caratteri combinati.  
  
 ![Testo con le legature standard OpenType disabilitate](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Testo con legature standard OpenType disabilitate")  

 Nell'esempio di markup seguente viene illustrato come disabilitare i glifi di <xref:System.Windows.Documents.Typography> legature standard per il tipo di carattere Palatino Linotype, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>
## <a name="swashes"></a>Glifi ornati  
 I glifi ornati sono glifi decorativi che usano ornamenti elaborati spesso associati alla calligrafia. Il testo seguente mostra glifi standard e ornati per il tipo di carattere Pescadero.  
  
 ![Testo con glifi standard e ornati OpenType](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Testo con glifi standard e ornati OpenType")  

 I glifi ornati vengono spesso usati come elementi decorativi in brevi frasi come gli annunci di eventi. Il testo seguente usa glifi ornati per porre in risalto le lettere maiuscole del nome dell'evento.  
  
 ![Testo con glifi ornati OpenType](./media/opentype-font-features/opentype-swashes.gif "Testo con glifi ornati OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire gli <xref:System.Windows.Documents.Typography> orti per un tipo di carattere, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Glifi ornati contestuali  
 Alcune combinazioni di glifi ornati possono creare un aspetto poco gradevole, ad esempio con tratti discendenti che si sovrappongono nelle lettere adiacenti. L'uso di un glifo ornato contestuale permette di usare un glifo ornato sostitutivo che conferisce un aspetto migliore. Il testo seguente mostra la stessa parola prima e dopo l'applicazione di un glifo ornato contestuale.  
  
 ![Testo con glifi ornati contestuali OpenType](./media/opentype-font-features/opentype-contextual-swashes.gif "Testo con glifi ornati contestuali OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire un urlo contestuale <xref:System.Windows.Documents.Typography> per il tipo di carattere Pescadero, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>
## <a name="alternates"></a>Glifi alternativi  
 I glifi alternativi possono essere usati per sostituire un glifo standard. I font OpenType, ad esempio il tipo di carattere Pericles utilizzato negli esempi seguenti, possono contenere glifi alternativi che è possibile utilizzare per creare aspetti diversi per il testo. Il testo seguente mostra i glifi standard per il tipo di carattere Pericles.  
  
 ![Testo con glifi standard OpenType](./media/opentype-font-features/opentype-standard-glyphs.gif "Testo con glifi standard OpenType")  

 Il font Pericles OpenType contiene glifi aggiuntivi che forniscono alternative stilistiche al set standard di glifi. Il testo seguente mostra glifi con stile alternativo.  
  
 ![Testo con glifi con stile alternativo OpenType](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Testo con glifi con stile alternativo OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire glifi alternativi stilistici <xref:System.Windows.Documents.Typography> per il tipo di carattere Pericles, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 Il testo seguente mostra altri glifi con stile alternativo per il tipo di carattere Pericles.  
  
 ![Testo con glifi alternativi stilistici OpenType per il tipo di carattere Pericles](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Testo con glifi alternativi stilistici OpenType per il tipo di carattere Pericles")

 L'esempio di markup seguente mostra come definire questi altri glifi con stile alternativo.  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Alternative contestuali casuali  
 Le alternative contestuali casuali forniscono più glifi sostitutivi per un singolo carattere. Se implementate con tipi di carattere di tipo script, questa funzionalità può simulare la scrittura manuale tramite un set di glifi scelti casualmente con differenze di aspetto minime. Il testo seguente usa alternative contestuali casuali per il tipo di carattere Lindsey. Notare come la lettera "a" varia leggermente nell'aspetto.  
  
 ![Testo con alternative contestuali casuali OpenType](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Testo con alternative contestuali casuali OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire alternative contestuali casuali <xref:System.Windows.Documents.Typography> per il tipo di carattere Lindsey, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Formati di tipo storico  
 I formati di tipo storico sono convenzioni tipografiche usate comunemente in passato. Il testo seguente mostra la frase "Boston, Massachusetts" usando glifi con un formato di tipo storico per il tipo di carattere Palatino Linotype.  
  
 ![Testo con formati di tipo storico OpenType](./media/opentype-font-features/opentype-historical-forms.gif "Testo con formati di tipo storico OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire forme cronologiche <xref:System.Windows.Documents.Typography> per il tipo di carattere Palatino Linotype, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>
## <a name="numerical-styles"></a>Stili numerici  
 I tipi di carattere OpenType supportano numerose funzionalità che possono essere usate con i valori numerici nel testo.  
  
### <a name="fractions"></a>Frazioni  
 I tipi di carattere OpenType supportano gli stili per le frazioni, incluse le frazioni barrate e sovrapposte.  
  
 Il testo seguente mostra stili di frazione per il tipo di carattere Palatino Linotype.  
  
 ![Testo con frazioni con barra e frazioni sovrapposte OpenType](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Testo con frazioni con barra e frazioni sovrapposte OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire gli stili <xref:System.Windows.Documents.Typography> di frazione per il tipo di carattere Palatino Linotype, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Caratteri numerici in stile antico  
 I font OpenType supportano un formato numerico vecchio stile. Questo formato è utile per visualizzare valori numerici in stili che non sono più quelli standard. Il testo seguente mostra una data del 18° secolo con formati numerici standard e in stile antico per il tipo di carattere Palatino Linotype.  
  
 ![Testo con caratteri numerici in stile antico OpenType](./media/opentype-font-features/opentype-old-style-numerals.gif "Testo con caratteri numerici in stile antico OpenType")  

 Il testo seguente mostra caratteri numerici standard per il tipo di carattere Palatino Linotype, seguiti da caratteri numerici in stile antico.  
  
 ![Testo con set di caratteri numerici in stile antico OpenType](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Testo con set di caratteri numerici in stile antico OpenType")  
  
 Nell'esempio di markup seguente viene illustrato come definire i numeri di stile <xref:System.Windows.Documents.Typography> precedente per il tipo di carattere Palatino Linotype, utilizzando le proprietà dell'oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Cifre proporzionali e tabulari  
 I font OpenType supportano una funzione di figura proporzionale e tabulare per controllare l'allineamento delle larghezze quando si utilizzano i numeri. Le cifre proporzionali gestiscono ogni carattere numerico applicando una larghezza diversa: "1" è più stretto di "5". Le cifre tabulari vengono gestite come caratteri numerici di uguale larghezza in modo da poter essere allineate in verticale, per aumentare la leggibilità delle informazioni di tipo finanziario.  
  
 Il testo seguente mostra due cifre proporzionali nella prima colonna usando il tipo di carattere Miramonte. Notare la differenza in larghezza tra i caratteri numerici "5" e "1". La seconda colonna mostra gli stessi valori numerici, le cui larghezze sono state modificate tramite la funzionalità per le cifre tabulari.  
  
 ![Testo con cifre proporzionali e tabulari OpenType](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Testo con cifre proporzionali e tabulari OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire le figure proporzionali e tabulari per il tipo di carattere Miramonte, utilizzando le proprietà dell'oggetto. <xref:System.Windows.Documents.Typography>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Zero barrato  
 I font OpenType supportano un formato numerico zero barrato per enfatizzare la differenza tra la lettera "O" e il numero "0". Il carattere numerico zero barrato viene spesso usato per gli identificatori all'interno di informazioni finanziarie e aziendali.  
  
 Il testo seguente mostra un identificatore di ordine di esempio con il tipo di carattere Miramonte. La prima riga usa caratteri numerici standard. La seconda riga usa caratteri numerici con zero barrato per distinguere meglio il carattere numerico dalla lettera "O" maiuscola.  
  
 ![Testo con caratteri numerici con zero barrato OpenType](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Testo con caratteri numerici con zero barrato OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire i numeri zero barrati per il tipo di carattere Miramonte, utilizzando le proprietà dell'oggetto. <xref:System.Windows.Documents.Typography>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>
## <a name="typography-class"></a>Classe Typography  
 L'oggetto <xref:System.Windows.Documents.Typography> espone il set di funzionalità supportate da un tipo di carattere OpenType. Impostando le proprietà <xref:System.Windows.Documents.Typography> di nel markup, è possibile creare facilmente documenti che sfruttano le funzionalità OpenType.  
  
 Il testo seguente visualizza lettere maiuscole standard per il tipo di carattere Pescadero, seguite da lettere in stile "SmallCaps" e "AllSmallCaps". In questo caso, viene usata la stessa dimensione di carattere per tutte e tre le parole.  
  
 ![Testo con caratteri maiuscoli OpenType](./media/opentype-font-features/opentype-capitals.gif "Testo con caratteri maiuscoli OpenType")  

 Nell'esempio di markup seguente viene illustrato come definire le maiuscole <xref:System.Windows.Documents.Typography> per il tipo di carattere Pescadero, utilizzando le proprietà dell'oggetto. Quando si usa il formato "SmallCaps", tutte le iniziali maiuscole vengono ignorate.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 L'esempio di codice seguente esegue la stessa attività dell'esempio di markup precedente.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Proprietà della classe Typography  
 Nella tabella seguente sono elencati le proprietà, i valori e le impostazioni predefinite dell'oggetto. <xref:System.Windows.Documents.Typography>  
  
|Proprietà|Valore/i|Default Value|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Valore numerico, byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps>&#124; <xref:System.Windows.FontCapitals.AllSmallCaps> <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; &#124; &#124; &#124; &#124;<xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Valore numerico, byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji><xref:System.Windows.FontEastAsianLanguage.Jis04> <xref:System.Windows.FontEastAsianLanguage.Jis78> <xref:System.Windows.FontEastAsianLanguage.Jis83> <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> <xref:System.Windows.FontEastAsianLanguage.Simplified> <xref:System.Windows.FontEastAsianLanguage.Traditional><xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full>&#124; <xref:System.Windows.FontEastAsianWidths.Half> <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; &#124; &#124; &#124;<xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|Valore numerico, byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|Valore numerico, byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior>&#124; <xref:System.Windows.FontVariants.Normal> <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> <xref:System.Windows.FontVariants.Subscript> &#124; &#124; &#124; &#124;<xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.Typography>
- [Specifiche OpenType](https://docs.microsoft.com/typography/opentype/spec/)
- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Esempio di pacchetto di tipi di carattere OpenType](sample-opentype-font-pack.md)
- [Includere i tipi di carattere nel pacchetto delle applicazioni](packaging-fonts-with-applications.md)
