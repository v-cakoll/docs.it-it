---
title: "Procedura: Attivare l'enumerazione TextTrimming"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474143"
---
# <a name="how-to-enable-text-trimming"></a>Procedura: Attivare l'enumerazione TextTrimming

Questo esempio viene illustrato l'utilizzo e gli effetti dei valori disponibili nel <xref:System.Windows.TextTrimming> enumerazione.

## <a name="example"></a>Esempio

L'esempio seguente definisce una <xref:System.Windows.Controls.TextBlock> elemento con la <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> set di attributi.

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

L'impostazione corrispondente <xref:System.Windows.TextTrimming> proprietà nel codice come illustrato di seguito.

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

Esistono attualmente tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis**, e **None**.

Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **CharacterEllipsis**, il testo viene tagliato e con i puntini di sospensione in corrispondenza del carattere più vicino al bordo del taglio.  Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.  La figura seguente mostra l'effetto di questa impostazione su un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.

![Esempio: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")

Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **WordEllipsis**, il testo viene tagliato e con i puntini di sospensione alla fine della prima parola completa più vicina al bordo del taglio.  Questa impostazione non visualizzerà le parole, ma non è possibile tagliare il testo come da vicino al bordo del taglio come le **CharacterEllipsis** impostazione.  La figura seguente mostra l'effetto di questa impostazione per il <xref:System.Windows.Controls.TextBlock> definiti in precedenza.

![Esempio: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")

Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **None**, non viene eseguita alcuna operazione di taglio del testo.  In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.  La figura seguente mostra l'effetto di questa impostazione su un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.

![Esempio: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")
