---
title: 'Procedura: Utilizzare un oggetto ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 22215a155f4a204e3edeebc464413d5718290bb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577071"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Procedura: Utilizzare un oggetto ThicknessConverter
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.ThicknessConverter> e usarlo per modificare lo spessore di un bordo.  
  
 L'esempio definisce un metodo personalizzato denominato `changeThickness`; questo metodo converte prima di tutto il contenuto di un <xref:System.Windows.Controls.ListBoxItem>, come definito in un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, a un'istanza di <xref:System.Windows.Thickness>e lo converte in un secondo momento il contenuto in un <xref:System.String>. Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> oggetto, che converte le <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Windows.Thickness>. Questo valore viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà del <xref:System.Windows.Controls.Border>.  
  
 Questo esempio non viene eseguito.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [Procedura: Modificare la proprietà Margin](https://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)
- [Procedura: Convertire un oggetto ListBoxItem in un nuovo tipo di dati](https://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)
- [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
