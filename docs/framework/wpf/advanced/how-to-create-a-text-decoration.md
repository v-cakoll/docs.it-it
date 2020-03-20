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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185927"
---
# <a name="how-to-create-a-text-decoration"></a>Procedura: creare un effetto di testo
Un <xref:System.Windows.TextDecoration> oggetto è un ornamento visivo che è possibile aggiungere al testo. Esistono quattro tipi di decorazioni di testo: sottolineatura, linea di base, barrato e overline. L'esempio seguente mostra le posizioni delle decorazioni di testo relative al testo.  
  
 ![Diagramma dei tipi di decorazione del testo](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 Per aggiungere una decorazione di <xref:System.Windows.TextDecoration> testo al testo, creare un oggetto e modificarne le proprietà. Utilizzare <xref:System.Windows.TextDecoration.Location%2A> la proprietà per specificare dove viene visualizzata la decorazione di testo, ad esempio sottolineatura. Utilizzare <xref:System.Windows.TextDecoration.Pen%2A> la proprietà per specificare l'aspetto della decorazione di testo, ad esempio un riempimento a tinta unita o un colore sfumato. Se non si specifica un <xref:System.Windows.TextDecoration.Pen%2A> valore per la proprietà, per impostazione predefinita le decorazioni hanno lo stesso colore del testo. Dopo aver definito <xref:System.Windows.TextDecoration> un oggetto, <xref:System.Windows.TextDecorations> aggiungerlo alla raccolta dell'oggetto di testo desiderato.  
  
 L'esempio seguente mostra una decorazione di testo a cui è stata creata uno stile con un pennello sfumato lineare e una penna tratteggiata.  
  
 ![Decorazione di testo con sottolineatura sfumata lineare](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 L'oggetto <xref:System.Windows.Documents.Hyperlink> è un elemento di contenuto del flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto del flusso. Per impostazione <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.TextDecoration> predefinita, utilizza un oggetto per visualizzare una sottolineatura. <xref:System.Windows.TextDecoration>Gli oggetti possono richiedere un utilizzo intensivo delle prestazioni per creare un'istanza, in particolare se si dispone di molti <xref:System.Windows.Documents.Hyperlink> oggetti. Se si fa <xref:System.Windows.Documents.Hyperlink> ampio uso di elementi, è consigliabile visualizzare una sottolineatura <xref:System.Windows.ContentElement.MouseEnter> solo quando si attiva un evento, ad esempio l'evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "Msn" <xref:System.Windows.ContentElement.MouseEnter> è dinamica, ma viene visualizzata solo quando l'evento viene attivato.  
  
 ![Collegamenti ipertestuali con TextDecoration](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente, una decorazione di testo sottolineato utilizza il valore del carattere predefinito.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Nell'esempio di codice seguente viene creata una decorazione di testo sottolineato con un pennello a tinta unita per la penna.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Nell'esempio di codice seguente viene creata una decorazione di testo sottolineato con un pennello sfumato lineare per la penna tratteggiata.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md)
