---
title: 'Procedura: Specificare se un collegamento ipertestuale è sottolineato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 1968e1b2730f08eb76670a477f1d2bdb0a9140bf
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408704"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>Procedura: Specificare se un collegamento ipertestuale è sottolineato
Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto dinamico. Per impostazione predefinita <xref:System.Windows.Documents.Hyperlink> Usa un <xref:System.Windows.TextDecoration> oggetto per visualizzare un carattere di sottolineatura. <xref:System.Windows.TextDecoration> gli oggetti possono essere prestazioni elevate per creare un'istanza, in particolare se si dispone di numerosi <xref:System.Windows.Documents.Hyperlink> oggetti. Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, è possibile provare a visualizzare una sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, vale a dire, essa viene visualizzata solo quando il <xref:System.Windows.ContentElement.MouseEnter> evento viene attivato.  
  
  ![Collegamenti ipertestuali con TextDecoration](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  
  
  
## <a name="example"></a>Esempio  
 L'esempio di markup seguente mostra un <xref:System.Windows.Documents.Hyperlink> definito con e senza sottolineatura:  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Esempio di codice seguente viene illustrato come creare un carattere di sottolineatura per il <xref:System.Windows.Documents.Hyperlink> nella <xref:System.Windows.ContentElement.MouseEnter> evento e rimuoverlo nel <xref:System.Windows.ContentElement.MouseLeave> evento.  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Creare un effetto di testo](how-to-create-a-text-decoration.md)
