---
title: Disegno di testo formattato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: a61031c36dea84449ad07175287bf834544df886
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129090"
---
# <a name="drawing-formatted-text"></a>Disegno di testo formattato
In questo argomento viene fornita una panoramica delle funzionalità del <xref:System.Windows.Media.FormattedText> oggetto. che offre un controllo di basso livello per il disegno di testo nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 Il <xref:System.Windows.Media.FormattedText> oggetto consente di disegnare il testo su più righe, in cui ogni carattere del testo può essere formattato singolarmente. L'esempio seguente mostra un testo a cui sono stati applicati diversi formati.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
>  Per gli sviluppatori che eseguono la migrazione dall'API [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], nella tabella della sezione [Migrazione Win32](#win32_migration) sono elencati i flag DrawText di [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e gli elementi corrispondenti in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### <a name="reasons-for-using-formatted-text"></a>Motivi per l'uso del testo formattato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per il disegno di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni. In generale, il <xref:System.Windows.Controls.TextBlock> elemento deve essere usato quando è richiesto, ad esempio una breve frase in un supporto limitato del testo un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> può essere utilizzato quando è necessario il supporto minimo del testo. Per altre informazioni, vedere [Documenti in WPF](documents-in-wpf.md).  
  
 Il <xref:System.Windows.Media.FormattedText> oggetto offre maggiore funzionalità rispetto di formattazione del testo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controlli di testo e può essere utile nei casi in cui si desidera usare testo come elemento decorativo. Per altre informazioni, vedere la sezione seguente [Conversione del testo formattato in una geometria](#converting_formatted_text).  
  
 Inoltre, il <xref:System.Windows.Media.FormattedText> oggetti sono utili per la creazione di orientati al testo <xref:System.Windows.Media.DrawingVisual>-oggetti derivati. <xref:System.Windows.Media.DrawingVisual> è una classe di disegno semplificata che consente di eseguire il rendering di forme, immagini o testo. Per altre informazioni, vedere [Esempio di hit test mediante DrawingVisual](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Uso dell'oggetto FormattedText  
 Per creare testo formattato, chiamare il <xref:System.Windows.Media.FormattedText.%23ctor%2A> costruttore per creare un <xref:System.Windows.Media.FormattedText> oggetto. Dopo aver creato la stringa di testo formattato iniziale, è possibile applicare una gamma di stili di formattazione.  
  
 Usare il <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> proprietà per limitare il testo a una larghezza specifica. Il testo andrà a capo automaticamente per evitare di superare la larghezza specificata. Usare il <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> proprietà per limitare il testo a un'altezza specifica. Saranno visualizzati dei puntini di sospensione ("...") nel caso in cui il testo superi l'altezza specificata.  
  
 ![Testo visualizzato con ritorno a capo automatico e puntini di sospensione.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 È possibile applicare vari stili di formattazione a uno o più caratteri. Ad esempio, è possibile chiamare entrambi i <xref:System.Windows.Media.FormattedText.SetFontSize%2A> e <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> metodi per modificare la formattazione dei primi cinque caratteri del testo.  
  
 L'esempio di codice seguente crea un <xref:System.Windows.Media.FormattedText> dell'oggetto e vengono quindi applicati diversi stili di formattazione al testo.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Unità di misura delle dimensioni del carattere  
 Come con altri oggetti di testo nelle [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le applicazioni, il <xref:System.Windows.Media.FormattedText> oggetto Usa device independent pixel come unità di misura. Tuttavia, la maggior parte delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] usa i punti come unità di misura. Se si desidera usare il testo visualizzato in una scala di punti nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], sarà necessario convertire le [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] in punti. Nell'esempio di codice seguente viene illustrato come eseguire questa conversione.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Conversione del testo formattato in una geometria  
 È possibile convertire il testo formattato in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo dall'aspetto accattivante. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Testo con pennello immagine applicato per tracciare ed evidenziare](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Quando il testo viene convertito in un <xref:System.Windows.Media.Geometry> dell'oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito. Per altre informazioni, vedere [Creare testo con contorni](how-to-create-outlined-text.md).  
  
 È anche possibile convertire il testo formattato a un <xref:System.Windows.Media.PathGeometry> oggetti e usare l'oggetto per evidenziare il testo. Ad esempio, è possibile applicare un'animazione per il <xref:System.Windows.Media.PathGeometry> oggetto in modo che segua la struttura del testo formattato.  
  
 L'esempio seguente mostra il testo formattato che è stato convertito in un <xref:System.Windows.Media.PathGeometry> oggetto. Un'ellisse animata segue il percorso dei tratti del testo di cui è stato eseguito il rendering.  
  
 ![Sfera che segue la geometria del percorso del testo](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Sfera che segue la geometria del percorso del testo  
  
 Per altre informazioni, vedere [Procedura: Creare animazioni PathGeometry per il testo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 È possibile creare altri usi interessanti del testo formattato dopo che è stata convertita in un <xref:System.Windows.Media.PathGeometry> oggetto. Ad esempio, è possibile ritagliare video da visualizzare all'interno del testo.  
  
 ![Video visualizzato nella geometria del percorso del testo](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Migrazione Win32  
 Le funzionalità di <xref:System.Windows.Media.FormattedText> per il disegno di testo sono simili alle caratteristiche del [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] funzione DrawText. Per gli sviluppatori che eseguono la migrazione dall'API [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], nella tabella seguente sono elencati i flag DrawText di [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e gli elementi corrispondenti in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Flag DrawText|Elemento corrispondente in WPF|Note|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Usare la <xref:System.Windows.Media.FormattedText.Height%2A> proprietà per calcolare una [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] posizione "y" di DrawText.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Usare la <xref:System.Windows.Media.FormattedText.Height%2A> e <xref:System.Windows.Media.FormattedText.Width%2A> proprietà per la quale calcolare il rettangolo di output.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Usare la <xref:System.Windows.Media.FormattedText.TextAlignment%2A> proprietà con il valore impostato su <xref:System.Windows.TextAlignment.Center>.|  
|DT_EDITCONTROL|nessuno|Non richiesto La larghezza dello spazio e il rendering dell'ultima riga sono uguali a quelli del controllo di modifica del framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Usare la <xref:System.Windows.Media.FormattedText.Trimming%2A> proprietà con il valore <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Uso <xref:System.Windows.TextTrimming.WordEllipsis> per ottenere [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DT_END_ELLIPSIS e terminano con puntini di sospensione, in questo caso, i puntini di sospensione di caratteri si verifica solo su parole che non rientrano in una singola riga.|  
|DT_EXPAND_TABS|nessuno|Non richiesto Le tabulazioni vengono espanse automaticamente per interrompersi ogni 4 em, all'incirca a una larghezza di 8 caratteri indipendenti dalla lingua.|  
|DT_EXTERNALLEADING|nessuno|Non richiesto L'interlinea esterna è sempre inclusa nell'interlinea. Usare il <xref:System.Windows.Media.FormattedText.LineHeight%2A> proprietà per creare un'interlinea definita dall'utente.|  
|DT_HIDEPREFIX|nessuno|Non supportato. Rimuovere "&" dalla stringa prima di costruire il <xref:System.Windows.Media.FormattedText> oggetto.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Impostazione predefinita per l'allineamento del testo. Usare la <xref:System.Windows.Media.FormattedText.TextAlignment%2A> proprietà con il valore impostato su <xref:System.Windows.TextAlignment.Left>. (solo WPF).|  
|DT_MODIFYSTRING|nessuno|Non supportato.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Il ritaglio non viene eseguito automaticamente. Se desidera per ritagliare il testo, utilizzare il <xref:System.Windows.Media.Visual.VisualClip%2A> proprietà.|  
|DT_NOFULLWIDTHCHARBREAK|nessuno|Non supportato.|  
|DT_NOPREFIX|nessuno|Non richiesto Il carattere "&" nelle stringhe viene sempre considerato un carattere normale.|  
|DT_PATHELLIPSIS|nessuno|Usare la <xref:System.Windows.Media.FormattedText.Trimming%2A> proprietà con il valore <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|nessuno|Non supportato. Se si desidera utilizzare caratteri di sottolineatura per il testo, ad esempio un tasto di scelta rapida o un collegamento, usare il <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> (metodo).|  
|DT_PREFIXONLY|nessuno|Non supportato.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Usare la <xref:System.Windows.Media.FormattedText.TextAlignment%2A> proprietà con il valore impostato su <xref:System.Windows.TextAlignment.Right>. (solo WPF).|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Impostare la proprietà <xref:System.Windows.Media.FormattedText.FlowDirection%2A> su <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|nessuno|Non richiesto <xref:System.Windows.Media.FormattedText> gli oggetti si comportano come un controllo a riga singola, a meno che entrambe le <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> viene impostata o il testo contiene un ritorno a capo/avanzamento riga (CR/LF).|  
|DT_TABSTOP|nessuno|Nessun supporto per le posizioni delle tabulazioni definite dall'utente.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Non richiesto Il testo è giustificato nella parte superiore per impostazione predefinita. Altri valori per il posizionamento verticale possono essere definiti tramite il <xref:System.Windows.Media.FormattedText.Height%2A> proprietà per calcolare una [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] posizione "y" di DrawText.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Usare la <xref:System.Windows.Media.FormattedText.Height%2A> proprietà per calcolare una [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] posizione "y" di DrawText.|  
|DT_WORDBREAK|nessuno|Non richiesto Le parole vengono interrotte automaticamente con <xref:System.Windows.Media.FormattedText> oggetti. Non è possibile disabilitare questa impostazione.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Usare la <xref:System.Windows.Media.FormattedText.Trimming%2A> proprietà con il valore <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- [Documenti in WPF](documents-in-wpf.md)
- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Creare testo con contorni](how-to-create-outlined-text.md)
- [Procedura: Creare animazioni PathGeometry per il testo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
