---
title: 'Procedura: Ottenere una raccolta di righe da un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: a63470c6f0db72340f482bf638910685aa3f461f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561764"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Procedura: Ottenere una raccolta di righe da un controllo TextBox
In questo esempio viene illustrato come ottenere una raccolta di righe di testo da un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra un semplice metodo che accetta un <xref:System.Windows.Controls.TextBox> come argomento e restituisce un <xref:System.Collections.Specialized.StringCollection> contenente le righe di testo nel **nella casella di testo**.  Il <xref:System.Windows.Controls.TextBox.LineCount%2A> proprietà viene utilizzata per determinare il numero di righe è attualmente nel **nella casella di testo**e il <xref:System.Windows.Controls.TextBox.GetLineText%2A> metodo viene quindi utilizzato per estrarre ogni riga e aggiungerlo alla raccolta di righe.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
