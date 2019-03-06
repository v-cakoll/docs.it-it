---
title: 'Procedura: Modificare il tipo di cursore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: e62658f4c4249c93bd24dffd3878dd2ec2b75029
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371149"
---
# <a name="how-to-change-the-cursor-type"></a>Procedura: Modificare il tipo di cursore
In questo esempio viene illustrato come modificare il <xref:System.Windows.Input.Cursor> del puntatore del mouse per un elemento specifico e per l'applicazione.  
  
 In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.  
  
## <a name="example"></a>Esempio  
 Viene creato l'interfaccia utente, che è costituito un <xref:System.Windows.Controls.ComboBox> per selezionare il valore desiderato <xref:System.Windows.Input.Cursor>, una coppia di <xref:System.Windows.Controls.RadioButton> oggetti per determinare se la modifica del cursore si applica a un solo elemento o si applica all'intera applicazione e un <xref:System.Windows.Controls.Border> ovvero l'elemento che viene applicato il nuovo cursore.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Il codice sottostante crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> gestore eventi chiamato quando il tipo di cursore è stato modificato nel <xref:System.Windows.Controls.ComboBox>.  Un'istruzione switch vengono applicati filtri al nome del cursore e imposta il <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà di <xref:System.Windows.Controls.Border> denominato *DisplayArea*.  
  
 Se la modifica del cursore è impostata su "Intera applicazione", il <xref:System.Windows.Input.Mouse.OverrideCursor%2A> è impostata sul <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà del <xref:System.Windows.Controls.Border> controllo.  In tal modo il cursore da modificare per l'intera applicazione.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'input](input-overview.md)
