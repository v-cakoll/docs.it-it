---
title: Panoramica sugli oggetti incorporati e TextPattern
description: Leggere una panoramica del modo in cui automazione interfaccia utente espone oggetti incorporati, o elementi figlio, all'interno di un documento di testo o di un contenitore usando TextPattern e TextPatternRange.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, TextPattern class
- embedded objects, accessing
- accessing embedded objects
- embedded objects, UI Automation
ms.assetid: 93fdfbb9-0025-4b72-8ca0-0714adbb70d5
ms.openlocfilehash: 0a06fb72b280fc61faeb12f6f2c3a05d957ec7b9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163557"
---
# <a name="textpattern-and-embedded-objects-overview"></a>Panoramica sugli oggetti incorporati e TextPattern
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questa panoramica è descritto come l' [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] espone oggetti incorporati, o elementi figlio, all'interno di un documento di testo o di un contenitore.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] un oggetto incorporato è qualsiasi elemento con limiti non testuali, ad esempio un'immagine, un collegamento ipertestuale, una tabella o un tipo di documento, ad esempio un foglio di calcolo di Microsoft Excel o un file Microsoft Windows Media. Questa definizione è diversa dalla definizione standard, che prevede che un elemento venga creato in un'applicazione e incorporato o collegato in un'altra. Nel contesto dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]è irrilevante che l'oggetto possa essere modificato all'interno dell'applicazione originale.  
  
<a name="Embedded_Objects_and_the_UI_Automation_Tree"></a>
## <a name="embedded-objects-and-the-ui-automation-tree"></a>Oggetti incorporati e albero di automazione interfaccia utente  
 Gli oggetti incorporati vengono considerati come singoli elementi all'interno della vista di controllo dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Gli oggetti vengono esposti come elementi figlio del contenitore di testo, in modo che sia possibile accedervi tramite lo stesso modello degli altri controlli nell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 ![Tabella incorporata con immagine in un contenitore di testo](./media/uia-textpattern-embedded-objects-overview-example1.png "UIA_TextPattern_Embedded_Objects_Overview_Example1")  
Esempio di un contenitore di testo con oggetti incorporati tabella, immagine e collegamento ipertestuale  
  
 ![Visualizzazione del contenuto dell'esempio precedente](./media/uia-textpattern-embedded-objects-overview-example2.PNG "UIA_TextPattern_Embedded_Objects_Overview_Example2")  
Esempio di visualizzazione del contenuto di una parte del contenitore di testo precedente  
  
<a name="Expose_Embedded_Objects_Using_TextPattern_and"></a>
## <a name="expose-embedded-objects-using-textpattern-and-textpatternrange"></a>Esporre oggetti incorporati tramite TextPattern e TextPatternRange  
 Usate in combinazione, le classi pattern di controllo <xref:System.Windows.Automation.TextPattern> e <xref:System.Windows.Automation.Text.TextPatternRange> espongono metodi e proprietà che facilitano lo spostamento e l'esecuzione di query di oggetti incorporati.  
  
 Il contenuto testuale (o testo interno) di un contenitore di testo o di un oggetto incorporato, ad esempio una cella di tabella o un collegamento ipertestuale, viene esposto come un flusso di testo continuo sia nella vista di controllo che nella visualizzazione del contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . I limiti dell'oggetto vengono ignorati. Se un client di automazione interfaccia utente sta recuperando il testo a scopo di esposizione, interpretazione o analisi, è necessario verificare l'eventuale presenza di casi speciali nell'intervallo di testo, ad esempio una tabella con contenuto testuale o altri oggetti incorporati. Questa operazione può essere eseguita chiamando <xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A> per ottenere un <xref:System.Windows.Automation.AutomationElement> per ogni oggetto incorporato e chiamando quindi <xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> per ottenere un intervallo di testo per ogni elemento. Questa operazione viene eseguita in modo ricorsivo fino a quando non è stato recuperato l'intero contenuto testuale.  
  
 ![Intervalli di testo estesi da oggetti incorporati](./media/uia-textpattern-embeddedobjecttextranges.png "UIA_TextPattern_EmbeddedObjectTextRanges")  
Esempio di un flusso di testo con oggetti incorporati e le estensioni degli intervalli corrispondenti  
  
 Quando è necessario scorrere il contenuto di un intervallo di testo, per garantire una corretta esecuzione del metodo <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> è prevista una serie di passaggi dietro le quinte.  
  
1. L'intervallo di testo viene normalizzato, ovvero viene compresso in un intervallo degenerato all'endpoint <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> . Ciò rende superfluo l'endpoint <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> . Questo passaggio è necessario per rimuovere l'ambiguità nelle situazioni in cui un intervallo di testo si estende <xref:System.Windows.Automation.Text.TextUnit> sui limiti: ad esempio, `{The URL https://www.microsoft.com is embedded in text` dove "{" e "}" sono gli endpoint dell'intervallo di testo.  
  
2. L'intervallo risultante viene spostato indietro in <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> all'inizio del limite <xref:System.Windows.Automation.Text.TextUnit> richiesto.  
  
3. L'intervallo viene spostato avanti o indietro in <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> per il numero richiesto di limiti <xref:System.Windows.Automation.Text.TextUnit> .  
  
4. L'intervallo viene quindi espanso dallo stato di intervallo degenerato spostando l'endpoint <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> di un limite <xref:System.Windows.Automation.Text.TextUnit> richiesto.  
  
 ![Regolazioni degli intervalli per spostamento & ExpandToEnclosingUnit](./media/uia-textpattern-moveandexpand-examples.png "UIA_TextPattern_MoveAndExpand_Examples")  
Esempi di regolazione di un intervallo di testo per Move() ed ExpandToEnclosingUnit()  
  
<a name="Common_Scenarios"></a>
## <a name="common-scenarios"></a>Scenari comuni  
 Nelle sezioni seguenti vengono illustrati esempi degli scenari più comuni che prevedono l'uso di oggetti incorporati.  
  
 Legenda per gli esempi illustrati:  
  
 { = <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start>  
  
 } = <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End>  
  
### <a name="hyperlink"></a>Hyperlink  

**Esempio 1: intervallo di testo che contiene un collegamento ipertestuale con testo incorporato**
  
`{The URL https://www.microsoft.com is embedded in text}.`
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Restituisce la stringa `The URL https://www.microsoft.com is embedded in text`.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Restituisce l' <xref:System.Windows.Automation.AutomationElement> più interno che racchiude l'intervallo di testo, in questo caso, l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il provider di testo stesso.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Restituisce un <xref:System.Windows.Automation.AutomationElement> che rappresenta il controllo collegamento ipertestuale.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> dove <xref:System.Windows.Automation.AutomationElement> è l'oggetto restituito dal metodo `GetChildren` precedente.|Restituisce l'intervallo che rappresenta `https://www.microsoft.com` .|  
  
 **Esempio 2: intervallo di testo che si estende parzialmente su un collegamento ipertestuale con testo incorporato**  
  
 L'URL `https://{[www]}` è incorporato nel testo.  
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Restituisce la stringa "www".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Restituisce l' <xref:System.Windows.Automation.AutomationElement> più interno che racchiude l'intervallo di testo, in questo caso, il controllo collegamento ipertestuale.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Restituisce `null` poiché l'intervallo di testo non si estende sull'intera stringa dell'URL.|  
  
**Esempio 3: intervallo di testo che si estende parzialmente sul contenuto di un contenitore di testo. Il contenitore di testo dispone di un collegamento ipertestuale con testo incorporato che non fa parte dell'intervallo di testo.**  
  
`{The URL} [https://www.microsoft.com](https://www.microsoft.com) is embedded in text.`
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Restituisce la stringa "L'URL".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Restituisce l' <xref:System.Windows.Automation.AutomationElement> più interno che racchiude l'intervallo di testo, in questo caso, l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il provider di testo stesso.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> con i parametri (TextUnit.Word, 1).|Sposta l'estensione dell'intervallo di intervallo di testo ad "http", poiché il testo del collegamento ipertestuale è costituito da parole singole. In questo caso, il collegamento ipertestuale non viene considerato come oggetto singolo.<br /><br /> L'URL {[http]} è incorporato nel testo.|  
  
<a name="Image"></a>
### <a name="image"></a>Immagine  
 **Esempio 1: intervallo di testo che contiene un'immagine incorporata**  
  
 {L' ![esempio image Embedded Image](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample") è incorporato nel testo}.  
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Restituisce la stringa "L'immagine è incorporata nel testo". Non è possibile prevedere l'inclusione nel flusso di testo dell'eventuale testo alternativo associato all'immagine.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Restituisce l' <xref:System.Windows.Automation.AutomationElement> più interno che racchiude l'intervallo di testo, in questo caso, l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il provider di testo stesso.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Restituisce un <xref:System.Windows.Automation.AutomationElement> che rappresenta il controllo immagine.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> dove <xref:System.Windows.Automation.AutomationElement> è l'oggetto restituito dal metodo <xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A> precedente.|Restituisce l'intervallo degenerato che rappresenta "![esempio di immagine incorporata](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample")".|  
  
 **Esempio 2: intervallo di testo che si estende parzialmente sul contenuto di un contenitore di testo. Il contenitore di testo contiene un'immagine incorporata che non fa parte dell'intervallo di testo.**  
  
 {Immagine} ![Esempio di immagine incorporata](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample") incorporata nel testo.  
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Restituisce la stringa "L'immagine".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Restituisce l' <xref:System.Windows.Automation.AutomationElement> più interno che racchiude l'intervallo di testo, in questo caso, l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il provider di testo stesso.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> con i parametri (TextUnit.Word, 1).|Sposta l'estensione dell'intervallo di testo a "è". Poiché solo gli oggetti incorporati basati su testo sono considerati parte del flusso di testo, l'immagine in questo esempio non influisce su Move o sul valore restituito da questo metodo (1 in questo caso).|  
  
<a name="Table"></a>
### <a name="table"></a>Tabella  
  
### <a name="table-used-for-examples"></a>Tabella usata per gli esempi  
  
|Cella con immagine|Cella con testo|  
|---------------------|--------------------|  
|![Esempio di immagine incorporata](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample")|X|  
|![Esempio di immagine incorporata 2](./media/uia-textpattern-embedded-objects-overview-imageexample2.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample2")|Y|  
|![Esempio di immagine incorporata 3](./media/uia-textpattern-embedded-objects-overview-imageexample3.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample3")<br /><br /> Immagine per Z|Z|  
  
 **Esempio 1: ottenere il contenitore di testo dal contenuto di una cella.**  
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.GridPattern.GetItem%2A> con parametri (0,0)|Restituisce l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il contenuto della cella della tabella; in questo caso, l'elemento è un controllo di testo.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> dove <xref:System.Windows.Automation.AutomationElement> è l'oggetto restituito dal metodo `GetItem` precedente.|Restituisce l'intervallo che si estende nell' ![esempio di immagine incorporata](./media/uia-textpattern-embedded-objects-overview-imageexample.PNG "UIA_TextPattern_Embedded_Objects_Overview_ImageExample")image.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> per l'oggetto restituito dal metodo `RangeFromChild` precedente.|Restituisce l' <xref:System.Windows.Automation.AutomationElement> che rappresenta la cella della tabella; in questo caso, l'elemento è un controllo di testo che supporta TableItemPattern.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> per l'oggetto restituito dal metodo `GetEnclosingElement` precedente.|Restituisce l' <xref:System.Windows.Automation.AutomationElement> che rappresenta la tabella.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> per l'oggetto restituito dal metodo `GetEnclosingElement` precedente.|Restituisce l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il provider di testo stesso.|  
  
 **Esempio 2: ottenere il contenitore di testo di una cella.**  
  
|Metodo chiamato|Risultato|  
|-------------------|------------|  
|<xref:System.Windows.Automation.GridPattern.GetItem%2A> con parametri (1,1).|Restituisce l' <xref:System.Windows.Automation.AutomationElement> che rappresenta il contenuto della cella della tabella; in questo caso, l'elemento è un controllo di testo.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> dove <xref:System.Windows.Automation.AutomationElement> è l'oggetto restituito dal metodo `GetItem` precedente.|Restituisce "Y".|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.TextPattern>
- <xref:System.Windows.Automation.Text.TextPatternRange>
- <xref:System.Windows.Automation.Provider.ITextProvider>
- <xref:System.Windows.Automation.Provider.ITextRangeProvider>
- [Accedere agli oggetti incorporati utilizzando l'automazione interfaccia utente](access-embedded-objects-using-ui-automation.md)
- [Esporre il contenuto di una tabella utilizzando l'automazione interfaccia utente](expose-the-content-of-a-table-using-ui-automation.md)
- [Scorrere il testo utilizzando automazione interfaccia utente](traverse-text-using-ui-automation.md)
- [Esempio di ricerca e selezione di TextPattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FindText)
