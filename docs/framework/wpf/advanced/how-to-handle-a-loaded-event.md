---
title: 'Procedura: Gestire un evento caricato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 187d75c436913140855f4d860eb3b6ad4656f309
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682943"
---
# <a name="how-to-handle-a-loaded-event"></a>Procedura: Gestire un evento caricato
In questo esempio viene illustrato come gestire il <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> evento e uno scenario adatto per la gestione di tale evento. Il gestore crea un <xref:System.Windows.Controls.Button> quando la pagina viene caricata.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] insieme a un file code-behind.  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.FrameworkElement>
- [Eventi di durata degli oggetti](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)
- [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
