---
title: 'Procedura: decorare gli elementi figlio di un riquadro'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d30e9e5ac15f48dabf983123ba007674a14626d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Procedura: decorare gli elementi figlio di un riquadro
In questo esempio viene illustrato come associare a livello di codice uno strumento decorativo visuale agli elementi figlio di un oggetto specificato <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Esempio  
 Per associare uno strumento decorativo visuale agli elementi figlio di un <xref:System.Windows.Controls.Panel>, seguire questi passaggi:  
  
1.  Dichiarare un nuovo <xref:System.Windows.Documents.AdornerLayer> oggetto e chiamare il `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metodo per trovare un livello dello strumento decorativo per l'elemento per decorare i cui elementi figlio.  
  
2.  Enumerare gli elementi figlio dell'elemento padre e chiamata di <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare un adorner a ogni elemento figlio.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) per gli elementi figlio di un <xref:System.Windows.Controls.StackPanel> denominato *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sugli strumenti decorativi](../../../../docs/framework/wpf/controls/adorners-overview.md)
