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
ms.openlocfilehash: eeba54ebd63b26a50c8c01a2478e847b3e660a3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937686"
---
# <a name="drawing-formatted-text"></a>Disegno di testo formattato
In questo argomento viene fornita una panoramica delle funzionalità dell' <xref:System.Windows.Media.FormattedText> oggetto. che offre un controllo di basso livello per il disegno di testo nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 L' <xref:System.Windows.Media.FormattedText> oggetto consente di creare testo su più righe, in cui ogni carattere del testo può essere formattato singolarmente. L'esempio seguente mostra un testo a cui sono stati applicati diversi formati.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Per gli sviluppatori che eseguono la migrazione dall'API [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], nella tabella della sezione [Migrazione Win32](#win32_migration) sono elencati i flag DrawText di [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e gli elementi corrispondenti in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### <a name="reasons-for-using-formatted-text"></a>Motivi per l'uso del testo formattato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per la creazione di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni. In generale, l' <xref:System.Windows.Controls.TextBlock> elemento deve essere utilizzato quando è necessario il supporto di testo limitato, ad esempio una breve frase [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]in un. <xref:System.Windows.Controls.Label>può essere utilizzato quando è richiesto un supporto di testo minimo. Per altre informazioni, vedere [Documenti in WPF](documents-in-wpf.md).  
  
 L' <xref:System.Windows.Media.FormattedText> oggetto fornisce funzionalità di formattazione del testo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] maggiori rispetto ai controlli testo e può essere utile nei casi in cui si desidera utilizzare il testo come elemento decorativo. Per altre informazioni, vedere la sezione seguente [Conversione del testo formattato in una geometria](#converting_formatted_text).  
  
 Inoltre, l'oggetto <xref:System.Windows.Media.FormattedText> è utile per la creazione di oggetti derivati da testo. <xref:System.Windows.Media.DrawingVisual> <xref:System.Windows.Media.DrawingVisual>è una classe di disegno semplificata utilizzata per il rendering di forme, immagini o testo. Per altre informazioni, vedere [Esempio di hit test mediante DrawingVisual](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Uso dell'oggetto FormattedText  
 Per creare un testo formattato, <xref:System.Windows.Media.FormattedText.%23ctor%2A> chiamare il costruttore per <xref:System.Windows.Media.FormattedText> creare un oggetto. Dopo aver creato la stringa di testo formattato iniziale, è possibile applicare una gamma di stili di formattazione.  
  
 Utilizzare la <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> proprietà per vincolare il testo a una larghezza specifica. Il testo andrà a capo automaticamente per evitare di superare la larghezza specificata. Utilizzare la <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> proprietà per vincolare il testo a un'altezza specifica. Saranno visualizzati dei puntini di sospensione ("...") nel caso in cui il testo superi l'altezza specificata.  
  
 ![Testo visualizzato con WordWrap e puntini di sospensione.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 È possibile applicare vari stili di formattazione a uno o più caratteri. Ad esempio, è possibile chiamare entrambi i <xref:System.Windows.Media.FormattedText.SetFontSize%2A> metodi <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> e per modificare la formattazione dei primi cinque caratteri del testo.  
  
 Nell'esempio di codice seguente viene <xref:System.Windows.Media.FormattedText> creato un oggetto, quindi vengono applicati diversi stili di formattazione al testo.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Unità di misura delle dimensioni del carattere  
 Come per gli altri oggetti di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] testo nelle applicazioni <xref:System.Windows.Media.FormattedText> , l'oggetto usa pixel indipendenti dal dispositivo come unità di misura. Tuttavia, la maggior parte delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] usa i punti come unità di misura. Se si vuole usare il testo visualizzato in unità di punti nelle [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni, è necessario convertire le unità indipendenti dal dispositivo (1/1/96 pollice per unità) in punti. Nell'esempio di codice seguente viene illustrato come eseguire questa conversione.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Conversione del testo formattato in una geometria  
 È possibile convertire il testo formattato in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo visivamente interessante. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Testo con pennello immagine applicato al tratto ed evidenziato](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Quando il testo viene convertito in <xref:System.Windows.Media.Geometry> un oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito. Per altre informazioni, vedere [Creare testo con contorni](how-to-create-outlined-text.md).  
  
 È anche possibile convertire il testo formattato <xref:System.Windows.Media.PathGeometry> in un oggetto e usare l'oggetto per evidenziare il testo. Ad esempio, è possibile applicare un'animazione all' <xref:System.Windows.Media.PathGeometry> oggetto in modo che l'animazione segua il contorno del testo formattato.  
  
 Nell'esempio seguente viene illustrato il testo formattato che è stato <xref:System.Windows.Media.PathGeometry> convertito in un oggetto. Un'ellisse animata segue il percorso dei tratti del testo di cui è stato eseguito il rendering.  
  
 ![Sfera che segue la geometria del percorso del testo](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Sfera che segue la geometria del percorso del testo  
  
 Per altre informazioni, vedere [Procedura: Creare un'animazione PathGeometry per il](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))testo.  
  
 È possibile creare altri usi interessanti per il testo formattato dopo che è stato convertito <xref:System.Windows.Media.PathGeometry> in un oggetto. Ad esempio, è possibile ritagliare video da visualizzare all'interno del testo.  
  
 ![Video visualizzato nella geometria del percorso del testo](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Migrazione Win32  
 Le funzionalità di <xref:System.Windows.Media.FormattedText> per il disegno di testo sono simili alle funzionalità [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] della funzione DrawText. Per gli sviluppatori che eseguono la migrazione dall'API [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], nella tabella seguente sono elencati i flag DrawText di [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e gli elementi corrispondenti in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Flag DrawText|Elemento corrispondente in WPF|Note|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilizzare la <xref:System.Windows.Media.FormattedText.Height%2A> proprietà per calcolare una posizione " [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y" di DrawText appropriata.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Usare le <xref:System.Windows.Media.FormattedText.Height%2A> proprietà <xref:System.Windows.Media.FormattedText.Width%2A> e per calcolare il rettangolo di output.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilizzare la <xref:System.Windows.Media.FormattedText.TextAlignment%2A> proprietà con il valore impostato su <xref:System.Windows.TextAlignment.Center>.|  
|DT_EDITCONTROL|Nessuna|Non richiesto La larghezza dello spazio e il rendering dell'ultima riga sono uguali a quelli del controllo di modifica del framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilizzare la <xref:System.Windows.Media.FormattedText.Trimming%2A> proprietà con il valore <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Usare <xref:System.Windows.TextTrimming.WordEllipsis> per ottenere [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DT_END_ELLIPSIS con i puntini di sospensione DT_WORD_ELIPSIS, in questo caso i puntini di sospensione dei caratteri si verificano solo su parole che non rientrano in una singola riga.|  
|DT_EXPAND_TABS|Nessuna|Non richiesto Le tabulazioni vengono espanse automaticamente per interrompersi ogni 4 em, all'incirca a una larghezza di 8 caratteri indipendenti dalla lingua.|  
|DT_EXTERNALLEADING|Nessuna|Non richiesto L'interlinea esterna è sempre inclusa nell'interlinea. Utilizzare la <xref:System.Windows.Media.FormattedText.LineHeight%2A> proprietà per creare un'interlinea definita dall'utente.|  
|DT_HIDEPREFIX|Nessuna|Non supportati. Rimuovere ' &' dalla stringa prima di costruire l' <xref:System.Windows.Media.FormattedText> oggetto.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Impostazione predefinita per l'allineamento del testo. Utilizzare la <xref:System.Windows.Media.FormattedText.TextAlignment%2A> proprietà con il valore impostato su <xref:System.Windows.TextAlignment.Left>. (solo WPF).|  
|DT_MODIFYSTRING|Nessuna|Non supportati.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Il ritaglio non viene eseguito automaticamente. Se si vuole ritagliare il testo, usare <xref:System.Windows.Media.Visual.VisualClip%2A> la proprietà.|  
|DT_NOFULLWIDTHCHARBREAK|Nessuna|Non supportati.|  
|DT_NOPREFIX|Nessuna|Non richiesto Il carattere "&" nelle stringhe viene sempre considerato un carattere normale.|  
|DT_PATHELLIPSIS|Nessuna|Utilizzare la <xref:System.Windows.Media.FormattedText.Trimming%2A> proprietà con il valore <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|Nessuna|Non supportati. Se si desidera utilizzare caratteri di sottolineatura per il testo, ad esempio un tasto di scelta rapida o <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> un collegamento, utilizzare il metodo.|  
|DT_PREFIXONLY|Nessuna|Non supportati.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilizzare la <xref:System.Windows.Media.FormattedText.TextAlignment%2A> proprietà con il valore impostato su <xref:System.Windows.TextAlignment.Right>. (solo WPF).|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Impostare la proprietà <xref:System.Windows.Media.FormattedText.FlowDirection%2A> su <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|Nessuna|Non richiesto <xref:System.Windows.Media.FormattedText>gli oggetti si comportano come un controllo a riga singola <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> , a meno che non sia impostata la proprietà o il testo contenga un ritorno a capo/avanzamento riga (CR/LF).|  
|DT_TABSTOP|Nessuna|Nessun supporto per le posizioni delle tabulazioni definite dall'utente.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Non richiesto Il testo è giustificato nella parte superiore per impostazione predefinita. È possibile definire altri valori di posizionamento verticale usando la <xref:System.Windows.Media.FormattedText.Height%2A> proprietà per calcolare una posizione " [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y" di DrawText appropriata.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilizzare la <xref:System.Windows.Media.FormattedText.Height%2A> proprietà per calcolare una posizione " [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y" di DrawText appropriata.|  
|DT_WORDBREAK|Nessuna|Non richiesto L'interruzione delle parole si <xref:System.Windows.Media.FormattedText> verifica automaticamente con gli oggetti. Non è possibile disabilitare questa impostazione.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilizzare la <xref:System.Windows.Media.FormattedText.Trimming%2A> proprietà con il valore <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- [Documenti in WPF](documents-in-wpf.md)
- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Creare testo con contorni](how-to-create-outlined-text.md)
- [Procedura: Creare un'animazione PathGeometry per il testo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
