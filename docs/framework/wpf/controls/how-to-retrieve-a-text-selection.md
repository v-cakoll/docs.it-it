---
title: 'Procedura: recuperare un testo selezionato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: 6b25c555d5e6cac93b2e1518b25e7880ab77c866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552012"
---
# <a name="how-to-retrieve-a-text-selection"></a>Procedura: recuperare un testo selezionato
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.TextBox.SelectedText%2A> proprietà per recuperare il testo che l'utente ha selezionato in un <xref:System.Windows.Controls.TextBox> controllo.  
  
## <a name="example"></a>Esempio  
 Le operazioni seguenti [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] riportato di seguito viene illustrata la definizione di un <xref:System.Windows.Controls.TextBox> controllo che contiene del testo da selezionare, e un <xref:System.Windows.Controls.Button> controllo con un oggetto specificato <xref:System.Windows.Controls.Button.OnClick%2A> metodo.  
  
 In questo esempio, un pulsante con un oggetto associato <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi viene utilizzato per recuperare il testo selezionato. Quando l'utente fa clic sul pulsante, il <xref:System.Windows.Controls.Button.OnClick%2A> metodo copia testo selezionato nella casella di testo in una stringa. Particolari circostanze per cui la selezione di testo viene recuperata (facendo clic su un pulsante), nonché l'azione eseguita su tale selezione (copia la selezione di testo in una stringa), possono essere facilmente modificati per supportare un'ampia gamma di scenari.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Esempio  
 Illustrato nell'esempio c# seguente un' <xref:System.Windows.Controls.Button.OnClick%2A> gestore eventi per il pulsante definito nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per questo esempio.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
