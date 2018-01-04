---
title: "Funzionalità dei tipi di carattere OpenType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
caps.latest.revision: "38"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6344fed6cf480e3d3f91a559c99b79f438afa985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="opentype-font-features"></a>Funzionalità dei tipi di carattere OpenType
Questo argomento contiene una panoramica di alcune delle funzionalità principali della tecnologia [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  

  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>Formato dei tipi di carattere OpenType  
 Il formato dei tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] è un'estensione del formato [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)], a cui è stato aggiunto il supporto per dati dei tipi di carattere PostScript. Il formato [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] è stato sviluppato da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] e Adobe Corporation insieme. I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] e i servizi del sistema operativo che supportano i tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] offrono agli utenti un semplice strumento per installare e usare i tipi di carattere, indipendentemente dal fatto che questi contengano strutture [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] o strutture CFF (PostScript).  
  
 Il formato [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] permette di affrontare le sfide di sviluppo seguenti:  
  
-   Supporto multipiattaforma più esteso.  
  
-   Supporto migliore per set di caratteri internazionali.  
  
-   Migliore protezione per i dati dei tipi di carattere.  
  
-   Dimensioni di file minori per rendere più efficiente la distribuzione dei tipi di carattere.  
  
-   Supporto più ampio per il controllo tipografico avanzato.  
  
> [!NOTE]
>  Windows SDK contiene un set di tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] di esempio, che è possibile usare con applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Questi tipi di carattere offrono la maggior parte delle funzionalità descritte nelle altre sezioni di questo argomento. Per altre informazioni, vedere [Esempio di pacchetto di tipi di carattere OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Vedere la [specifica OpenType](http://go.microsoft.com/fwlink/?LinkId=96731) per informazioni dettagliate sul formato [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
### <a name="advanced-typographic-extensions"></a>Estensioni tipografiche avanzate  
 Le tabelle tipografiche avanzate (tabelle dei layout [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]) estendono le funzionalità dei tipi di carattere con strutture [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] o CFF. I tipi di carattere con layout [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] contengono informazioni aggiuntive che estendono le funzionalità dei tipi di carattere per supportare la tipografia internazionale di alta qualità. La maggior parte dei tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] espone solo un subset delle funzionalità [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] totali disponibili. I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] offrono le funzionalità seguenti.  
  
-   Mapping avanzato tra caratteri e glifi che supportano legature, formati posizionali, glifi alternativi e altre sostituzioni di tipi di carattere.  
  
-   Supporto per posizionamento bidimensionale e collegamento di glifi.  
  
-   Informazioni esplicite su script e lingua contenute in un carattere, per permettere a un'applicazione di elaborazione del testo di modificare il proprio comportamento di conseguenza.  
  
 Le tabelle dei layout [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] vengono descritte più dettagliatamente nella sezione relativa alle [tabelle dei file dei tipi di carattere](http://www.microsoft.com/typography/otspec/otff.htm) della specifica [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
 Nella parte restante di questa panoramica viene la profondità e la flessibilità di alcune delle visivamente interessanti [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] funzionalità esposte dalle proprietà del <xref:System.Windows.Documents.Typography> oggetto. Per altre informazioni su questo oggetto, vedere [Classe Typography](#typography_class).  
  
<a name="variants"></a>   
## <a name="variants"></a>Varianti  
 Le varianti vengono usate per eseguire il rendering di stili tipografici diversi, come gli apici e i pedici.  
  
### <a name="superscripts-and-subscripts"></a>Apici e pedici  
 Il <xref:System.Windows.Documents.Typography.Variants%2A> proprietà consente di impostare valori apici e pedici per un [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tipo di carattere.  
  
 Il testo seguente mostra apici per il tipo di carattere Palatino Linotype.  
  
 ![Testo con apici OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")  
Testo con apici OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire gli apici per il tipo di formati di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 Il testo seguente mostra pedici per il tipo di carattere Palatino Linotype.  
  
 ![Testo con pedici OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")  
Testo con pedici OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire gli indici per il tipo di formati di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Uso decorativo di apici e pedici  
 È anche possibile usare apici e pedici per creare effetti decorativi di testo con maiuscole e minuscole miste. Il testo seguente mostra testo in apice e pedice per il tipo di carattere Palatino Linotype. Si noti che questa formattazione non influisce sulle maiuscole.  
  
 ![Testo con apici OpenType e pedici](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")  
Testo con apici e pedici OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire gli apici e pedici per un tipo di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>Caratteri maiuscoli  
 I caratteri maiuscoli sono un set di caratteri tipografici per il rendering del testo in glifi in stile maiuscolo. In genere, quando il testo viene visualizzato come tutto maiuscolo, la spaziatura tra le lettere può risultare insufficiente, mentre lo spessore e le proporzioni delle lettere possono apparire eccessivi. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supporta diversi formati di stile per le maiuscole, tra cui maiuscoletto, maiuscoletto ridotto, titolazione e spaziatura tra caratteri maiuscoli. Questi formati permettono di controllare l'aspetto dei caratteri maiuscoli.  
  
 Il testo seguente visualizza lettere maiuscole standard per il tipo di carattere Pescadero, seguite da lettere in stile "SmallCaps" e "AllSmallCaps". In questo caso, viene usata la stessa dimensione di carattere per tutte e tre le parole.  
  
 ![Testo con caratteri maiuscoli OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")  
Testo con caratteri maiuscoli OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire le maiuscole per il tipo di carattere Pescadero, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto. Quando si usa il formato "SmallCaps", tutte le iniziali maiuscole vengono ignorate.  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Caratteri maiuscoli di titolazione  
 I caratteri maiuscoli di titolazione hanno spessore e proporzioni minori e sono progettati per conferire un aspetto più elegante rispetto alle lettere maiuscole normali. I caratteri maiuscoli di titolazione vengono in genere usati con dimensioni di carattere maggiori come intestazioni. Il testo seguente mostra caratteri maiuscoli normali e di titolazione per il tipo di carattere Pescadero. Notare la larghezza minore delle aste nel testo della seconda riga.  
  
 ![Testo con le lettere maiuscole di titolazione OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")  
Testo con caratteri maiuscoli per i titoli OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire le maiuscole per il tipo di carattere Pescadero, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Spaziatura tra caratteri maiuscoli  
 La spaziatura tra caratteri maiuscoli è una funzionalità che permette di aggiungere più spazio quando si usano caratteri tutti maiuscoli nel testo. Le lettere maiuscole sono in genere progettate per essere combinate con lettere minuscole. La gradevole spaziatura tra una lettera maiuscola e una minuscola può risultare troppo ridotta quando si usano lettere tutte maiuscole. Il testo seguente mostra una spaziatura normale e una tra caratteri maiuscoli per il tipo di carattere Pescadero.  
  
 ![Testo con spaziatura tra caratteri maiuscoli OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")  
Testo con spaziatura tra caratteri maiuscoli OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire la spaziatura tra maiuscole per il tipo di carattere Pescadero, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>Legature  
 Le legature sono due o più glifi uniti a formare un singolo glifo per creare un testo più leggibile o gradevole. I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supportano quattro tipi di legature:  
  
-   **Legature standard**. Progettate per migliorare la leggibilità. Le legature standard includono "fi", "fl" e "ff".  
  
-   **Legature contestuali**. Progettate per migliorare la leggibilità applicando un accostamento migliore tra i caratteri che costituiscono la legatura.  
  
-   **Legature discrezionali**. Progettate per scopi ornamentali e non appositamente ideate per favorire la leggibilità.  
  
-   **Legature storiche**. Progettate per testi di tipo storico e non appositamente ideate per favorire la leggibilità.  
  
 Il testo seguente mostra glifi con legature standard per il tipo di carattere Pericles.  
  
 ![Testo con legature standard OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")  
Testo con legature standard OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire i glifi di legature standard per il tipo di carattere Pericles, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 Il testo seguente mostra glifi con legature discrezionali per il tipo di carattere Pericles.  
  
 ![Testo con legature discrezionali OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")  
Testo con legature discrezionali OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire i glifi di legature discrezionali per il tipo di carattere Pericles, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 Per impostazione predefinita, i tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] permettono legature standard. Se si usa, ad esempio, il tipo di carattere Palatino Linotype, le legature standard "fi", "ff" e "fl" verranno visualizzate come glifi di caratteri combinati. Si noti che nella coppia di caratteri per ogni legatura standard i caratteri si toccano tra loro.  
  
 ![Testo con legature standard OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")  
Testo con legature standard OpenType  
  
 Tuttavia, è possibile disabilitare le funzionalità di legatura standard in modo che una legatura standard come "ff" venga visualizzata come due glifi separati invece che come glifo di caratteri combinati.  
  
 ![Testo con legature standard OpenType disabilitate](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")  
Testo con legature standard OpenType disabilitate  
  
 Nell'esempio di codice seguente viene illustrato come disabilitare i glifi di legature standard per il tipo di formati di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>Glifi ornati  
 I glifi ornati sono glifi decorativi che usano ornamenti elaborati spesso associati alla calligrafia. Il testo seguente mostra glifi standard e ornati per il tipo di carattere Pescadero.  
  
 ![Testo con glifi standard e ornati OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
Testo con glifi standard e ornati OpenType  
  
 I glifi ornati vengono spesso usati come elementi decorativi in brevi frasi come gli annunci di eventi. Il testo seguente usa glifi ornati per porre in risalto le lettere maiuscole del nome dell'evento.  
  
 ![Testo con caratteri ornati OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")  
Testo con glifi ornati OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire caratteri ornati per un tipo di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Glifi ornati contestuali  
 Alcune combinazioni di glifi ornati possono creare un aspetto poco gradevole, ad esempio con tratti discendenti che si sovrappongono nelle lettere adiacenti. L'uso di un glifo ornato contestuale permette di usare un glifo ornato sostitutivo che conferisce un aspetto migliore. Il testo seguente mostra la stessa parola prima e dopo l'applicazione di un glifo ornato contestuale.  
  
 ![Testo con caratteri ornati contestuali OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")  
Testo con glifi ornati contestuali OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire un ornati contestuali per il tipo di carattere Pescadero, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>Glifi alternativi  
 I glifi alternativi possono essere usati per sostituire un glifo standard. I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], come il tipo di carattere Pericles usato negli esempi seguenti, possono contenere glifi alternativi, da usare per conferire aspetti diversi al testo. Il testo seguente mostra i glifi standard per il tipo di carattere Pericles.  
  
 ![Testo con glifi standard OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")  
Testo con glifi standard OpenType  
  
 Il tipo di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Pericles contiene glifi aggiuntivi che offrono alternative stilistiche al set di glifi standard. Il testo seguente mostra glifi con stile alternativo.  
  
 ![Testo con glifi di stile alternativo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
Testo con glifi con stile alternativo OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire i glifi di stile alternativo per il tipo di carattere Pericles, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 Il testo seguente mostra altri glifi con stile alternativo per il tipo di carattere Pericles.  
  
 ![Testo con glifi di stile alternativo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")  
Testo con glifi con stile alternativo OpenType  
  
 L'esempio di markup seguente mostra come definire questi altri glifi con stile alternativo.  
  
 [!code-xaml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Alternative contestuali casuali  
 Le alternative contestuali casuali forniscono più glifi sostitutivi per un singolo carattere. Se implementate con tipi di carattere di tipo script, questa funzionalità può simulare la scrittura manuale tramite un set di glifi scelti casualmente con differenze di aspetto minime. Il testo seguente usa alternative contestuali casuali per il tipo di carattere Lindsey. Notare come la lettera "a" varia leggermente nell'aspetto.  
  
 ![Testo con alternative contestuali casuali OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")  
Testo con alternative contestuali casuali OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire le alternative contestuali casuali per il tipo di carattere Lindsey, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Formati di tipo storico  
 I formati di tipo storico sono convenzioni tipografiche usate comunemente in passato. Il testo seguente mostra la frase "Boston, Massachusetts" usando glifi con un formato di tipo storico per il tipo di carattere Palatino Linotype.  
  
 ![Il testo utilizzando storico OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")  
Testo con formati di tipo storico OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire storico per il tipo di formati di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>Stili numerici  
 I tipi di carattere OpenType supportano numerose funzionalità che possono essere usate con i valori numerici nel testo.  
  
### <a name="fractions"></a>Frazioni  
 I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supportano stili per le frazioni, tra cui frazioni con barra e frazioni sovrapposte.  
  
 Il testo seguente mostra stili di frazione per il tipo di carattere Palatino Linotype.  
  
 ![Testo che utilizza barra e frazioni sovrapposte](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")  
Testo con frazioni con barra e frazioni sovrapposte OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire stili per il tipo di formati di carattere, utilizzando le proprietà di frazioni di <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Caratteri numerici in stile antico  
 I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supportano un formato numerico in stile antico. Questo formato è utile per visualizzare valori numerici in stili che non sono più quelli standard. Il testo seguente mostra una data del 18° secolo con formati numerici standard e in stile antico per il tipo di carattere Palatino Linotype.  
  
 ![Testo con stile antico OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")  
Testo con caratteri numerici in stile antico OpenType  
  
 Il testo seguente mostra caratteri numerici standard per il tipo di carattere Palatino Linotype, seguiti da caratteri numerici in stile antico.  
  
 ![Utilizzo di set di caratteri numerici in stile antico OpenType testo](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")  
Testo con set di caratteri numerici in stile antico OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire stile antico per il tipo di formati di carattere, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Cifre proporzionali e tabulari  
 I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supportano una funzionalità per cifre proporzionali e tabulari, che permette di controllare l'allineamento delle larghezze quando si usano caratteri numerici. Le cifre proporzionali gestiscono ogni carattere numerico applicando una larghezza diversa: "1" è più stretto di "5". Le cifre tabulari vengono gestite come caratteri numerici di uguale larghezza in modo da poter essere allineate in verticale, per aumentare la leggibilità delle informazioni di tipo finanziario.  
  
 Il testo seguente mostra due cifre proporzionali nella prima colonna usando il tipo di carattere Miramonte. Notare la differenza in larghezza tra i caratteri numerici "5" e "1". La seconda colonna mostra gli stessi valori numerici, le cui larghezze sono state modificate tramite la funzionalità per le cifre tabulari.  
  
 ![Testo con cifre proporzionali e tabulari OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")  
Testo con cifre proporzionali e tabulari OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire le cifre proporzionali e tabulari per il tipo di carattere Miramonte, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Zero barrato  
 I tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supportano un formato numerico con zero barrato per evidenziare la differenza tra la lettera "O" e il carattere numerico "0". Il carattere numerico zero barrato viene spesso usato per gli identificatori all'interno di informazioni finanziarie e aziendali.  
  
 Il testo seguente mostra un identificatore di ordine di esempio con il tipo di carattere Miramonte. La prima riga usa caratteri numerici standard. La seconda riga usa caratteri numerici con zero barrato per distinguere meglio il carattere numerico dalla lettera "O" maiuscola.  
  
 ![Testo che utilizza zero barrato](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")  
Testo con caratteri numerici con zero barrato OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire zero barrato per il tipo di carattere Miramonte, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>Classe Typography  
 Il <xref:System.Windows.Documents.Typography> oggetto espone il set di funzionalità che un [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] supporta tipi di carattere. Impostando le proprietà di <xref:System.Windows.Documents.Typography> nel markup, è possibile creare facilmente i documenti che sfruttano [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] funzionalità.  
  
 Il testo seguente visualizza lettere maiuscole standard per il tipo di carattere Pescadero, seguite da lettere in stile "SmallCaps" e "AllSmallCaps". In questo caso, viene usata la stessa dimensione di carattere per tutte e tre le parole.  
  
 ![Testo con caratteri maiuscoli OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")  
Testo con caratteri maiuscoli OpenType  
  
 Nell'esempio di codice seguente viene illustrato come definire le maiuscole per il tipo di carattere Pescadero, utilizzando le proprietà del <xref:System.Windows.Documents.Typography> oggetto. Quando si usa il formato "SmallCaps", tutte le iniziali maiuscole vengono ignorate.  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 L'esempio di codice seguente esegue la stessa attività dell'esempio di markup precedente.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Proprietà della classe Typography  
 Nella tabella seguente sono elencate le proprietà, valori e le impostazioni predefinite del <xref:System.Windows.Documents.Typography> oggetto.  
  
|Proprietà|Valore/i|Valore predefinito|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Valore numerico, byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Valore numerico, byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
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
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Documents.Typography>  
 [Specifica OpenType](http://go.microsoft.com/fwlink/?LinkId=96731)  
 [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Esempio di pacchetto di tipi di carattere OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)  
 [Includere i tipi di carattere nel pacchetto delle applicazioni](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
