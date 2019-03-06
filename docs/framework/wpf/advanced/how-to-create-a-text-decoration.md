---
title: 'Procedura: Creare un effetto di testo'
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
ms.openlocfilehash: a142604fdb36ec6f85e9411b37077bfffff587d4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363917"
---
# <a name="how-to-create-a-text-decoration"></a>Procedura: Creare un effetto di testo
Oggetto <xref:System.Windows.TextDecoration> oggetto è un ornamento visivo è possibile aggiungere al testo. Esistono quattro tipi di effetti del testo: sottolineato, linea di base, quali il barrato e linea sopra. Nell'esempio seguente mostra la posizione delle decorazioni di testo rispetto al testo.  
  
 ![Diagramma della posizione delle decorazioni di testo](./media/textdecoration01.gif "TextDecoration01")  
Esempio di tipi di effetto di testo  
  
 Per aggiungere un effetto di testo al testo, creare un <xref:System.Windows.TextDecoration> dell'oggetto e modificarne le proprietà. Usare il <xref:System.Windows.TextDecoration.Location%2A> proprietà per specificare dove viene visualizzato l'effetto di testo, quali sottolineato. Usare il <xref:System.Windows.TextDecoration.Pen%2A> proprietà per specificare l'aspetto dell'effetto di testo, ad esempio un riempimento a tinta unita o sfumatura di colore. Se non si specifica un valore per il <xref:System.Windows.TextDecoration.Pen%2A> proprietà, i valori predefiniti delle decorazioni sullo stesso colore del testo. Dopo aver definito una <xref:System.Windows.TextDecoration> dell'oggetto, aggiungerla al <xref:System.Windows.TextDecorations> insieme dell'oggetto testo desiderato.  
  
 L'esempio seguente illustra un effetto di testo che è stato disegnato con un pennello sfumato lineare e una penna tratteggiata.  
  
 ![Decorazione di testo con sottolineatura sfumata lineare](./media/textdecoration02.png "TextDecoration02")  
Esempio di un carattere di sottolineatura nello stile con una sfumatura lineare brush e pen tratteggiate  
  
 Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto dinamico. Per impostazione predefinita <xref:System.Windows.Documents.Hyperlink> Usa un <xref:System.Windows.TextDecoration> oggetto per visualizzare un carattere di sottolineatura. <xref:System.Windows.TextDecoration> gli oggetti possono essere prestazioni elevate per creare un'istanza, in particolare se si dispone di numerosi <xref:System.Windows.Documents.Hyperlink> oggetti. Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, è possibile provare a visualizzare una sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, viene visualizzata solo quando il <xref:System.Windows.ContentElement.MouseEnter> evento viene attivato.  
  
 ![Collegamenti ipertestuali con TextDecoration](./media/textdecoration03.png "TextDecoration03")  
Collegamenti ipertestuali definiti con TextDecorations  
  
 Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente, un effetto di testo sottolineato viene utilizzato il valore del tipo di carattere predefinito.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Nell'esempio di codice seguente, un effetto di testo sottolineato viene creato con un pennello di colore a tinta unita per la penna.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Nell'esempio di codice seguente, un effetto di testo sottolineato viene creato con un pennello sfumato lineare per la penna tratteggiata.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md)
