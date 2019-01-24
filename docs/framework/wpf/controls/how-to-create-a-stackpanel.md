---
title: 'Procedura: Creare uno StackPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: 20e2b21b10129c096398606501768a7ace0617fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674232"
---
# <a name="how-to-create-a-stackpanel"></a>Procedura: Creare uno StackPanel
In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Esempio  
 Oggetto <xref:System.Windows.Controls.StackPanel> consente di sovrapporre gli elementi in una direzione specificata. Usando le proprietà definite su <xref:System.Windows.Controls.StackPanel>, il contenuto può fluire in verticale, ovvero l'impostazione predefinita, orizzontalmente o verticalmente.  
  
 Nell'esempio seguente in uno stack verticale cinque <xref:System.Windows.Controls.TextBlock> controlli, ognuno con un diverso <xref:System.Windows.Controls.Border> e <xref:System.Windows.Controls.Border.Background%2A>, usando <xref:System.Windows.Controls.StackPanel>. Gli elementi figlio che contengono non è specificata alcuna <xref:System.Windows.FrameworkElement.Width%2A> adattata per riempire la finestra padre; tuttavia, gli elementi figlio che hanno un determinato <xref:System.Windows.FrameworkElement.Width%2A>, sono centrati nella finestra.  
  
 La direzione predefinita in un <xref:System.Windows.Controls.StackPanel> è verticale. Flusso di controllo contenuto in un <xref:System.Windows.Controls.StackPanel>, usare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà. È possibile controllare l'allineamento orizzontale tramite il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.StackPanel>
- [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
