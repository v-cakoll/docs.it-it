---
title: 'Procedura: Recuperare un testo selezionato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b7f0b9ee02a7ace717787fc8eeb6e15649829a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224585"
---
# <a name="how-to-retrieve-a-text-selection"></a>Procedura: Recuperare un testo selezionato
In questo esempio illustra un modo per usare la <xref:System.Windows.Controls.TextBox.SelectedText%2A> proprietà per recuperare il testo che l'utente ha selezionato in un <xref:System.Windows.Controls.TextBox> controllo.  
  
## <a name="example"></a>Esempio  
 Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] riportato di seguito viene illustrata la definizione di un <xref:System.Windows.Controls.TextBox> controllo che contiene del testo da selezionare, e una <xref:System.Windows.Controls.Button> controllo con un determinato <xref:System.Windows.Controls.Button.OnClick%2A> (metodo).  
  
 In questo esempio, un pulsante con un oggetto associato <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi viene usato per recuperare la selezione di testo. Quando l'utente fa clic sul pulsante, il <xref:System.Windows.Controls.Button.OnClick%2A> metodo copia testo selezionato nella casella di testo in una stringa. Le specifiche circostanze mediante il quale la selezione di testo viene recuperata (facendo clic su un pulsante), così come l'azione eseguita su tale selezione (copia la selezione di testo in una stringa), possono essere facilmente modificati per soddisfare un'ampia gamma di scenari.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Esempio  
 Quanto segue C# esempio viene illustrato un <xref:System.Windows.Controls.Button.OnClick%2A> gestore evento per il pulsante definito nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in questo esempio.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
