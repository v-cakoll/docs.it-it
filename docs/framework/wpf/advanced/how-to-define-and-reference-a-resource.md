---
title: 'Procedura: definire e fare riferimento a una risorsa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 173be3048f7bf082db2eef2ea21eb1e0319f9a43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-reference-a-resource"></a>Procedura: definire e fare riferimento a una risorsa
In questo esempio viene illustrato come definire una risorsa e di farvi riferimento tramite un attributo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce due tipi di risorse: un <xref:System.Windows.Media.SolidColorBrush> risorse e numerosi <xref:System.Windows.Style> risorse. Il <xref:System.Windows.Media.SolidColorBrush> risorse `MyBrush` viene utilizzata per fornire il valore di diverse proprietà che accettano un <xref:System.Windows.Media.Brush> tipo valore. Il <xref:System.Windows.Style> risorse `PageBackground`, `TitleText` e `Label` ogni destinazione di un particolare tipo di controllo. Gli stili di impostano numerose proprietà sui controlli di destinazione, per tale risorsa di stile fa riferimento una chiave di risorsa, viene utilizzato per impostare il <xref:System.Windows.FrameworkElement.Style%2A> proprietà dei diversi elementi di controllo specifico, definito in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Si noti che una delle proprietà all'interno dei metodi di impostazione del `Label` stile fa riferimento anche il `MyBrush` risorsa definita in precedenza. Questa è una tecnica comune, ma è importante ricordare che le risorse vengono analizzate e immessi in un dizionario risorse nell'ordine in cui vengono loro assegnati. Le risorse sono richieste anche l'ordine trovato nel dizionario, se si utilizza il [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) per fare riferimento a esse all'interno di un'altra risorsa. Assicurarsi che tutte le risorse a cui si fa riferimento sono definita in precedenza all'interno della raccolta di risorse rispetto a quella in cui è richiesta la risorsa. Se necessario, è possibile risolvere il rigido ordine di creazione di riferimenti a risorse tramite un [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) per fare riferimento alla risorsa in fase di esecuzione, ma occorre tenere presente che questa DynamicResource tecnica incide sulle prestazioni. Per informazioni dettagliate, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>Vedere anche  
 [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
