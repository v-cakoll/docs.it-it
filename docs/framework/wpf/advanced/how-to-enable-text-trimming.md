---
title: "Procedura: Attivare l'enumerazione TextTrimming"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 97bc88b298500892fcc7d26e61f8052a05d9e593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543540"
---
# <a name="how-to-enable-text-trimming"></a>Procedura: Attivare l'enumerazione TextTrimming
Questo esempio viene illustrato l'utilizzo e gli effetti dei valori disponibili nel <xref:System.Windows.TextTrimming> enumerazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un <xref:System.Windows.Controls.TextBlock> elemento con la <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> set di attributi.  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a>Esempio  
 L'impostazione corrispondente <xref:System.Windows.TextTrimming> proprietà nel codice è illustrato di seguito.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 Esistono attualmente tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis**, e **Nessuno**.  
  
 Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **CharacterEllipsis**, il testo viene tagliato e con i puntini di sospensione in corrispondenza del carattere più vicino al bordo di taglio.  Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.  Nella figura seguente mostra l'effetto di questa impostazione in un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.  
  
 ![Esempio: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")  
  
 Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **WordEllipsis**, il testo viene tagliato e con i puntini di sospensione alla fine della prima parola completa più vicina del bordo di taglio.  Questa impostazione non visualizzerà le parole, ma non è possibile tagliare testo quanto più accuratamente il bordo di taglio come il **CharacterEllipsis** impostazione.  Nella figura seguente mostra l'effetto di questa impostazione per il <xref:System.Windows.Controls.TextBlock> definiti in precedenza.  
  
 ![Esempio: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")  
  
 Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **Nessuno**, non viene eseguita alcuna operazione di taglio del testo.  In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.  Nella figura seguente mostra l'effetto di questa impostazione in un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.  
  
 ![Esempio: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")
