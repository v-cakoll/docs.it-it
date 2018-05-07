---
title: 'Procedura: specificare se un collegamento ipertestuale è sottolineato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 3d57039d959aa63c031ef467cd2f8398fc3ffd96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>Procedura: specificare se un collegamento ipertestuale è sottolineato
Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto di flusso. Per impostazione predefinita, <xref:System.Windows.Documents.Hyperlink> utilizza un <xref:System.Windows.TextDecoration> oggetto per visualizzare un carattere di sottolineatura. <xref:System.Windows.TextDecoration> gli oggetti possono essere prestazioni elevate per creare un'istanza, in particolare se si dispone di numerosi <xref:System.Windows.Documents.Hyperlink> oggetti. Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, si consiglia di provare a visualizzare un carattere di sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, viene visualizzata solo quando il <xref:System.Windows.ContentElement.MouseEnter> evento viene generato.  
  
 ![Collegamenti ipertestuali con TextDecoration](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Collegamenti ipertestuali definiti con TextDecorations  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato un <xref:System.Windows.Documents.Hyperlink> definito con e senza un carattere di sottolineatura:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Esempio di codice riportato di seguito viene illustrato come creare un carattere di sottolineatura per il <xref:System.Windows.Documents.Hyperlink> sul <xref:System.Windows.ContentElement.MouseEnter> evento e rimuoverlo nel <xref:System.Windows.ContentElement.MouseLeave> evento.  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Creare un effetto di testo](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
