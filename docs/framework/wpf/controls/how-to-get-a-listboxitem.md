---
title: 'Procedura: Ottenere un oggetto ListBoxItem'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: 27a435feb4a941c77af221ab25bd63ea98b16e92
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360498"
---
# <a name="how-to-get-a-listboxitem"></a>Procedura: Ottenere un oggetto ListBoxItem
Se è necessario ottenere una determinata <xref:System.Windows.Controls.ListBoxItem> in corrispondenza dell'indice specifico in un <xref:System.Windows.Controls.ListBox>, è possibile usare un <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un <xref:System.Windows.Controls.ListBox> e i relativi elementi.  
  
 [!code-xaml[ListBoxItems#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene illustrato come recuperare l'elemento specificando l'indice dell'elemento nella <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> proprietà del <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
 [!code-csharp[ListBoxItems#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 Dopo aver recuperato l'elemento casella di riepilogo, è possibile visualizzare il contenuto dell'elemento, come illustrato nell'esempio seguente.  
  
 [!code-csharp[ListBoxItems#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
