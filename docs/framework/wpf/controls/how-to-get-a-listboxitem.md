---
title: 'Procedura: ottenere un oggetto ListBoxItem'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: f1e25ce60ff5feb8fd644a5864dbd762b4b5fa39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552727"
---
# <a name="how-to-get-a-listboxitem"></a>Procedura: ottenere un oggetto ListBoxItem
Se è necessario ottenere un oggetto specifico <xref:System.Windows.Controls.ListBoxItem> da un indice specifico in un <xref:System.Windows.Controls.ListBox>, è possibile utilizzare un <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un <xref:System.Windows.Controls.ListBox> e i relativi elementi.  
  
 [!code-xaml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene illustrato come recuperare l'elemento specificando l'indice dell'elemento di <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> proprietà del <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 Dopo aver recuperato l'elemento casella di riepilogo, è possibile visualizzare il contenuto dell'elemento, come illustrato nell'esempio seguente.  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
