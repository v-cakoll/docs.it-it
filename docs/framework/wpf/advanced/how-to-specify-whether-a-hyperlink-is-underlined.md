---
title: 'Procedura: Specificare se un collegamento ipertestuale è sottolineato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 5718912e24a0697f209669b0ab4e7f4df1765ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943949"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="cc567-102">Procedura: Specificare se un collegamento ipertestuale è sottolineato</span><span class="sxs-lookup"><span data-stu-id="cc567-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="cc567-103">Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="cc567-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="cc567-104">Per impostazione predefinita <xref:System.Windows.Documents.Hyperlink> Usa un <xref:System.Windows.TextDecoration> oggetto per visualizzare un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cc567-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="cc567-105"><xref:System.Windows.TextDecoration> gli oggetti possono essere prestazioni elevate per creare un'istanza, in particolare se si dispone di numerosi <xref:System.Windows.Documents.Hyperlink> oggetti.</span><span class="sxs-lookup"><span data-stu-id="cc567-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="cc567-106">Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, è possibile provare a visualizzare una sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento.</span><span class="sxs-lookup"><span data-stu-id="cc567-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="cc567-107">Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, vale a dire, essa viene visualizzata solo quando il <xref:System.Windows.ContentElement.MouseEnter> evento viene attivato.</span><span class="sxs-lookup"><span data-stu-id="cc567-107">In the following example, the underline for the "My MSN" link is dynamic, that is, it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
  ![Collegamenti ipertestuali con TextDecoration](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  

## <a name="example"></a><span data-ttu-id="cc567-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc567-109">Example</span></span>  
 <span data-ttu-id="cc567-110">L'esempio di markup seguente mostra un <xref:System.Windows.Documents.Hyperlink> definito con e senza sottolineatura:</span><span class="sxs-lookup"><span data-stu-id="cc567-110">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="cc567-111">Esempio di codice seguente viene illustrato come creare un carattere di sottolineatura per il <xref:System.Windows.Documents.Hyperlink> nella <xref:System.Windows.ContentElement.MouseEnter> evento e rimuoverlo nel <xref:System.Windows.ContentElement.MouseLeave> evento.</span><span class="sxs-lookup"><span data-stu-id="cc567-111">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="cc567-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc567-112">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="cc567-113">Ottimizzazione delle prestazioni di applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="cc567-113">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="cc567-114">Creare un effetto di testo</span><span class="sxs-lookup"><span data-stu-id="cc567-114">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)
