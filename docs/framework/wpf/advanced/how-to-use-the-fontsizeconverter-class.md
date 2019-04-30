---
title: 'Procedura: Usare la classe FontSizeConverter'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: f33a297ae07d5509d2b4d9a98636086ac433a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051039"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>Procedura: Usare la classe FontSizeConverter
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.FontSizeConverter> e usarlo per modificare una dimensione del carattere.  
  
 L'esempio definisce un metodo personalizzato denominato `changeSize` che converte il contenuto di un <xref:System.Windows.Controls.ListBoxItem>, come definito in un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, a un'istanza di <xref:System.Double>e successivamente in un <xref:System.String>. Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.FontSizeConverter> oggetto, che converte le <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Double>. Questo valore viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.TextBlock.FontSize%2A> proprietà del <xref:System.Windows.Controls.TextBlock> elemento.  
  
 In questo esempio definisce anche un secondo metodo personalizzato che viene chiamato `changeFamily`. Questo metodo converte il <xref:System.Windows.Controls.ContentControl.Content%2A> del <xref:System.Windows.Controls.ListBoxItem> per un <xref:System.String>e quindi passa tale valore per il <xref:System.Windows.Controls.TextBlock.FontFamily%2A> proprietà del <xref:System.Windows.Controls.TextBlock> elemento.  
  
 Questo esempio non viene eseguito.  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FontSizeConverter>
