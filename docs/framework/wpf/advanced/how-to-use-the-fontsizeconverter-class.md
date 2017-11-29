---
title: 'Procedura: Usare la classe FontSizeConverter'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcf2d7348ca5b6b9d3b2edc44f92afbd46d32594
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>Procedura: Usare la classe FontSizeConverter
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.FontSizeConverter> e usarlo per modificare la dimensione del carattere.  
  
 L'esempio definisce un metodo personalizzato denominato `changeSize` che converte il contenuto di un <xref:System.Windows.Controls.ListBoxItem>, come definito in un apposito [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, a un'istanza di <xref:System.Double>e versioni successive in un <xref:System.String>. Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> per un <xref:System.Windows.FontSizeConverter> oggetto, che converte il <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Double>. Questo valore viene quindi passato nuovamente come valore del <xref:System.Windows.Controls.TextBlock.FontSize%2A> proprietà del <xref:System.Windows.Controls.TextBlock> elemento.  
  
 In questo esempio definisce anche un secondo metodo personalizzato che viene chiamato `changeFamily`. Questo metodo converte il <xref:System.Windows.Controls.ContentControl.Content%2A> del <xref:System.Windows.Controls.ListBoxItem> per un <xref:System.String>e quindi passare tale valore per il <xref:System.Windows.Controls.TextBlock.FontFamily%2A> proprietà del <xref:System.Windows.Controls.TextBlock> elemento.  
  
 Questo esempio non viene eseguito.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FontSizeConverter>
