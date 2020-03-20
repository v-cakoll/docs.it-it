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
ms.openlocfilehash: 1e82795afbdd5b1b0a05f95600ebdb92fc134b7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186557"
---
# <a name="drawing-formatted-text"></a>Disegno di testo formattato
In questo argomento viene fornita <xref:System.Windows.Media.FormattedText> una panoramica delle funzionalità dell'oggetto. che offre un controllo di basso livello per il disegno di testo nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 L'oggetto <xref:System.Windows.Media.FormattedText> consente di disegnare testo su più righe, in cui ogni carattere del testo può essere formattato singolarmente. L'esempio seguente mostra un testo a cui sono stati applicati diversi formati.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Per gli sviluppatori che eseguono la migrazione dall'API Win32, la tabella nella sezione Migrazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] [Win32](#win32_migration) elenca i flag Win32 DrawText e l'equivalente approssimativo in .  
  
### <a name="reasons-for-using-formatted-text"></a>Motivi per l'uso del testo formattato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per la creazione di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni. In generale, <xref:System.Windows.Controls.TextBlock> l'elemento deve essere utilizzato quando è richiesto un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]supporto di testo limitato, ad esempio una breve frase in un file . <xref:System.Windows.Controls.Label>può essere utilizzato quando è richiesto un supporto minimo per il testo. Per altre informazioni, vedere [Documenti in WPF](documents-in-wpf.md).  
  
 L'oggetto <xref:System.Windows.Media.FormattedText> fornisce maggiori [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funzionalità di formattazione del testo rispetto ai controlli di testo e può essere utile nei casi in cui si desidera utilizzare il testo come elemento decorativo. Per altre informazioni, vedere la sezione seguente [Conversione del testo formattato in una geometria](#converting_formatted_text).  
  
 Inoltre, l'oggetto <xref:System.Windows.Media.FormattedText> è utile per <xref:System.Windows.Media.DrawingVisual>la creazione di oggetti derivati orientati al testo. <xref:System.Windows.Media.DrawingVisual>è una classe di disegno leggera utilizzata per eseguire il rendering di forme, immagini o testo. Per altre informazioni, vedere [Esempio di hit test mediante DrawingVisual](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
## <a name="using-the-formattedtext-object"></a>Uso dell'oggetto FormattedText  
 Per creare testo formattato, chiamare <xref:System.Windows.Media.FormattedText.%23ctor%2A> <xref:System.Windows.Media.FormattedText> il costruttore per creare un oggetto . Dopo aver creato la stringa di testo formattato iniziale, è possibile applicare una gamma di stili di formattazione.  
  
 Utilizzare <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> la proprietà per vincolare il testo a una larghezza specifica. Il testo andrà a capo automaticamente per evitare di superare la larghezza specificata. Utilizzare <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> la proprietà per vincolare il testo a un'altezza specifica. Saranno visualizzati dei puntini di sospensione ("...") nel caso in cui il testo superi l'altezza specificata.  
  
 ![Testo visualizzato con il ritorno a capo automatico e i lipsia.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 È possibile applicare vari stili di formattazione a uno o più caratteri. Ad esempio, è possibile <xref:System.Windows.Media.FormattedText.SetFontSize%2A> <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> chiamare entrambi i metodi e per modificare la formattazione dei primi cinque caratteri del testo.  
  
 Nell'esempio di <xref:System.Windows.Media.FormattedText> codice riportato di seguito viene creato un oggetto che vengono quindi applicati diversi stili di formattazione al testo.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Unità di misura delle dimensioni del carattere  
 Come con altri [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] oggetti di <xref:System.Windows.Media.FormattedText> testo nelle applicazioni, l'oggetto utilizza pixel indipendenti dal dispositivo come unità di misura. Tuttavia, la maggior parte delle applicazioni Win32 utilizza punti come unità di misura. Se si desidera utilizzare il testo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] visualizzato in unità di punti nelle applicazioni, è necessario convertire le unità indipendenti dal dispositivo (1/96 di pollice per unità) in punti. Nell'esempio di codice seguente viene illustrato come eseguire questa conversione.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>
### <a name="converting-formatted-text-to-a-geometry"></a>Conversione del testo formattato in una geometria  
 È possibile convertire il <xref:System.Windows.Media.Geometry> testo formattato in oggetti, consentendo di creare altri tipi di testo visivamente interessante. Ad esempio, è <xref:System.Windows.Media.Geometry> possibile creare un oggetto in base al contorno di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Testo con pennello immagine applicato al tratto e all'evidenziazione](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Quando il testo <xref:System.Windows.Media.Geometry> viene convertito in un oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito. Per altre informazioni, vedere [Creare testo con contorni](how-to-create-outlined-text.md).  
  
 È inoltre possibile convertire il <xref:System.Windows.Media.PathGeometry> testo formattato in un oggetto e utilizzare l'oggetto per evidenziare il testo. Ad esempio, è possibile applicare <xref:System.Windows.Media.PathGeometry> un'animazione all'oggetto in modo che l'animazione segua il contorno del testo formattato.  
  
 Nell'esempio seguente viene illustrato il testo <xref:System.Windows.Media.PathGeometry> formattato che è stato convertito in un oggetto. Un'ellisse animata segue il percorso dei tratti del testo di cui è stato eseguito il rendering.  
  
 ![Sfera che segue la geometria del percorso del testo](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Sfera che segue la geometria del percorso del testo  
  
 Per altre informazioni, vedere [Procedura: Creare animazioni PathGeometry per il testo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 È possibile creare altri utilizzi interessanti per il testo <xref:System.Windows.Media.PathGeometry> formattato una volta convertito in un oggetto. Ad esempio, è possibile ritagliare video da visualizzare all'interno del testo.  
  
 ![Video visualizzato nella geometria del percorso del testo](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>
## <a name="win32-migration"></a>Migrazione Win32  
 Le caratteristiche <xref:System.Windows.Media.FormattedText> di per il disegno del testo sono simili a quelle della funzione Win32 DrawText. Per gli sviluppatori che eseguono la migrazione dall'API Win32, nella tabella [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]seguente sono elencati i flag Win32 DrawText e l'equivalente approssimativo in .  
  
|Flag DrawText|Elemento corrispondente in WPF|Note|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.Height%2A> la proprietà per calcolare una posizione 'y' Win32 DrawText appropriata.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.Height%2A> le <xref:System.Windows.Media.FormattedText.Width%2A> proprietà e per calcolare il rettangolo di output.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.TextAlignment%2A> la proprietà con <xref:System.Windows.TextAlignment.Center>il valore impostato su .|  
|DT_EDITCONTROL|nessuno|Non obbligatorio. La larghezza dello spazio e il rendering dell'ultima riga sono uguali a quelli del controllo di modifica del framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.Trimming%2A> la proprietà <xref:System.Windows.TextTrimming.CharacterEllipsis>con il valore .<br /><br /> Utilizzare <xref:System.Windows.TextTrimming.WordEllipsis> per ottenere Win32 DT_END_ELLIPSIS con i DT_WORD_ELIPSISi duello di fine, in questo caso, i ellissi carattere si verifica solo su parole che non rientrano in una singola riga.|  
|DT_EXPAND_TABS|nessuno|Non obbligatorio. Le tabulazioni vengono espanse automaticamente per interrompersi ogni 4 em, all'incirca a una larghezza di 8 caratteri indipendenti dalla lingua.|  
|DT_EXTERNALLEADING|nessuno|Non obbligatorio. L'interlinea esterna è sempre inclusa nell'interlinea. Utilizzare <xref:System.Windows.Media.FormattedText.LineHeight%2A> la proprietà per creare un'interlinea definita dall'utente.|  
|DT_HIDEPREFIX|nessuno|Non supportato. Rimuovere l'& dalla stringa prima <xref:System.Windows.Media.FormattedText> di costruire l'oggetto.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Impostazione predefinita per l'allineamento del testo. Utilizzare <xref:System.Windows.Media.FormattedText.TextAlignment%2A> la proprietà con <xref:System.Windows.TextAlignment.Left>il valore impostato su . (solo WPF).|  
|DT_MODIFYSTRING|nessuno|Non supportato.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Il ritaglio non viene eseguito automaticamente. Se si desidera ritagliare <xref:System.Windows.Media.Visual.VisualClip%2A> il testo, utilizzare la proprietà .|  
|DT_NOFULLWIDTHCHARBREAK|nessuno|Non supportato.|  
|DT_NOPREFIX|nessuno|Non obbligatorio. Il carattere "&" nelle stringhe viene sempre considerato un carattere normale.|  
|DT_PATHELLIPSIS|nessuno|Utilizzare <xref:System.Windows.Media.FormattedText.Trimming%2A> la proprietà <xref:System.Windows.TextTrimming.WordEllipsis>con il valore .|  
|DT_PREFIX|nessuno|Non supportato. Se si desidera utilizzare caratteri di sottolineatura per il testo, ad esempio un tasto di scelta rapida o un collegamento, utilizzare il <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> metodo .|  
|DT_PREFIXONLY|nessuno|Non supportato.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.TextAlignment%2A> la proprietà con <xref:System.Windows.TextAlignment.Right>il valore impostato su . (solo WPF).|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Impostare la proprietà <xref:System.Windows.Media.FormattedText.FlowDirection%2A> su <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|nessuno|Non obbligatorio. <xref:System.Windows.Media.FormattedText>gli oggetti si comportano come un <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> controllo a riga singola, a meno che la proprietà non sia impostata o il testo non contenga un ritorno a capo/avanzamento riga (CR/LF).|  
|DT_TABSTOP|nessuno|Nessun supporto per le posizioni delle tabulazioni definite dall'utente.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Non obbligatorio. Il testo è giustificato nella parte superiore per impostazione predefinita. Altri valori di posizionamento verticale <xref:System.Windows.Media.FormattedText.Height%2A> possono essere definiti utilizzando la proprietà per calcolare una posizione 'y' Win32 DrawText appropriata.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.Height%2A> la proprietà per calcolare una posizione 'y' Win32 DrawText appropriata.|  
|DT_WORDBREAK|nessuno|Non obbligatorio. L'interruzione delle <xref:System.Windows.Media.FormattedText> parole avviene automaticamente con gli oggetti. Non è possibile disabilitare questa impostazione.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilizzare <xref:System.Windows.Media.FormattedText.Trimming%2A> la proprietà <xref:System.Windows.TextTrimming.WordEllipsis>con il valore .|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- [Documenti in WPF](documents-in-wpf.md)
- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Creare testo con contorni](how-to-create-outlined-text.md)
- [Procedura: Creare animazioni PathGeometry per il testo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
