---
title: 'Procedura: modificare il tipo di cursore'
description: Modificare il cursore del puntatore del mouse per un elemento e per un'applicazione in Windows Presentation Foundation. Questo esempio è costituito da XAML e da un file code-behind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165963"
---
# <a name="how-to-change-the-cursor-type"></a>Procedura: modificare il tipo di cursore
Questo esempio illustra come modificare l'oggetto <xref:System.Windows.Input.Cursor> del puntatore del mouse per un elemento specifico e per l'applicazione.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
## <a name="example"></a>Esempio  
 Viene creata l'interfaccia utente, costituita da un oggetto <xref:System.Windows.Controls.ComboBox> per selezionare l'oggetto desiderato <xref:System.Windows.Input.Cursor> , una coppia di <xref:System.Windows.Controls.RadioButton> oggetti per determinare se la modifica del cursore viene applicata solo a un singolo elemento o si applica all'intera applicazione e a un oggetto <xref:System.Windows.Controls.Border> che è l'elemento a cui viene applicato il nuovo cursore.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Il codice sottostante seguente crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> gestore eventi che viene chiamato quando il tipo di cursore viene modificato in <xref:System.Windows.Controls.ComboBox> .  Un'istruzione switch filtra sul nome del cursore e imposta la <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà nell'oggetto, <xref:System.Windows.Controls.Border> denominato *DisplayArea*.  
  
 Se la modifica del cursore è impostata su "intera applicazione", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> proprietà viene impostata sulla <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà del <xref:System.Windows.Controls.Border> controllo.  In questo modo si impone la modifica del cursore per l'intera applicazione.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
