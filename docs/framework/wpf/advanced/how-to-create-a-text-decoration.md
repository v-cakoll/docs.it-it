---
title: 'Procedura: creare un effetto di testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: c16073dd2413c1258f4875ac4118e0656d29b171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-text-decoration"></a>Procedura: creare un effetto di testo
Oggetto <xref:System.Windows.TextDecoration> oggetto è un visual ornamenti, è possibile aggiungere testo. Sono disponibili quattro tipi di effetti del testo: sottolineato, linea di base, barrato e linea sopra. L'esempio seguente mostra la posizione delle decorazioni di testo rispetto al testo.  
  
 ![Diagramma di posizione delle decorazioni di testo](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")  
Esempio di tipi di effetti di testo  
  
 Per aggiungere un effetto di testo, creare un <xref:System.Windows.TextDecoration> dell'oggetto e modificarne le proprietà. Utilizzare il <xref:System.Windows.TextDecoration.Location%2A> proprietà per specificare dove viene visualizzato l'effetto di testo, quali sottolineato. Utilizzare il <xref:System.Windows.TextDecoration.Pen%2A> proprietà per specificare l'aspetto dell'effetto di testo, ad esempio un riempimento a tinta unita o sfumatura di colore. Se non si specifica un valore per il <xref:System.Windows.TextDecoration.Pen%2A> proprietà, i valori predefiniti effetti sullo stesso colore del testo. Dopo aver definito una <xref:System.Windows.TextDecoration> dell'oggetto, aggiungerlo al <xref:System.Windows.TextDecorations> raccolta dell'oggetto testo desiderato.  
  
 Nell'esempio seguente viene illustrato un effetto di testo disegnato con pennello sfumato lineare e una penna tratteggiata.  
  
 ![Decorazione di testo con sottolineatura sfumata lineare](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
Esempio di un carattere di sottolineatura disegnata con una sfumatura lineare pennello e penna tratteggiata  
  
 Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto di flusso. Per impostazione predefinita, <xref:System.Windows.Documents.Hyperlink> utilizza un <xref:System.Windows.TextDecoration> oggetto per visualizzare un carattere di sottolineatura. <xref:System.Windows.TextDecoration> gli oggetti possono essere prestazioni elevate per creare un'istanza, in particolare se si dispone di numerosi <xref:System.Windows.Documents.Hyperlink> oggetti. Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, si consiglia di provare a visualizzare un carattere di sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, viene visualizzata solo quando il <xref:System.Windows.ContentElement.MouseEnter> evento viene generato.  
  
 ![Collegamenti ipertestuali con TextDecoration](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Collegamenti ipertestuali definiti con TextDecorations  
  
 Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente, un effetto di testo sottolineato viene utilizzato il valore di tipo di carattere predefinito.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Nell'esempio di codice riportato di seguito, un effetto di testo sottolineato viene creato con un pennello tinta unita per la penna.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Nell'esempio di codice seguente viene creato un effetto di testo sottolineato con pennello sfumato lineare per la penna tratteggiata.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [Specificare se un collegamento ipertestuale è sottolineato](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
