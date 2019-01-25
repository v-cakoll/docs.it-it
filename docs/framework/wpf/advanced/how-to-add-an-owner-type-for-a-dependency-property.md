---
title: 'Procedura: Aggiungere un tipo di proprietario per una proprietà di dipendenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 528ec28750c6ce7dffb1104d750679a546df0487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697062"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Procedura: Aggiungere un tipo di proprietario per una proprietà di dipendenza
In questo esempio viene illustrato come aggiungere una classe come proprietario di una proprietà di dipendenza registrato per un tipo diverso. In questo modo, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lettore e sistema di proprietà sono entrambi in grado di riconoscere la classe come proprietario della proprietà aggiuntivo. Aggiungere come proprietario, facoltativamente, consente alla classe aggiunta fornire i metadati specifici del tipo.  
  
 Nell'esempio riportato di seguito `StateProperty` è una proprietà registrata per il `MyStateControl` classe. La classe `UnrelatedStateControl` aggiunge se stesso come proprietario del `StateProperty` usando il <xref:System.Windows.DependencyProperty.AddOwner%2A> metodo, in modo specifico usando la firma che consente di nuovi metadati della proprietà di dipendenza esistente sul tipo aggiunto. Si noti che è necessario fornire [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] funzioni di accesso per la proprietà simile all'esempio illustrato nel [implementare una proprietà di dipendenza](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) esempio, nonché esporre nuovamente l'identificatore di proprietà di dipendenza nella classe da aggiungere come proprietario.  
  
 Senza wrapper, la proprietà di dipendenza funzionerà ancora dalla prospettiva di accesso a livello di codice usando <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. Ma si desidera questo comportamento del sistema di proprietà con in parallelo in genere il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] wrapper della proprietà. I wrapper rendono più semplice impostare la proprietà di dipendenza a livello di codice e consentono di impostare le proprietà come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributi.  
  
 Per scoprire come eseguire l'override dei metadati predefiniti, vedere [eseguire l'Override dei metadati per una proprietà di dipendenza](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Vedere anche
- [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
