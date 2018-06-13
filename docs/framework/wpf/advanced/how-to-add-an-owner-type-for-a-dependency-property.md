---
title: 'Procedura: aggiungere un tipo di proprietario per una proprietà di dipendenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: bf3f73743d1c76145bf520ed859c27c4d3aaf662
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542776"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Procedura: aggiungere un tipo di proprietario per una proprietà di dipendenza
In questo esempio viene illustrato come aggiungere una classe come proprietario di una proprietà di dipendenza registrato per un tipo diverso. In questo modo, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lettore e sistema di proprietà sono entrambi in grado di riconoscere la classe come proprietario della proprietà aggiuntivo. L'aggiunta come proprietario consente alla classe aggiunta fornire i metadati specifici del tipo.  
  
 Nell'esempio seguente, `StateProperty` è una proprietà registrata per il `MyStateControl` classe. La classe `UnrelatedStateControl` viene aggiunto come proprietario del `StateProperty` utilizzando il <xref:System.Windows.DependencyProperty.AddOwner%2A> (metodo), in particolare utilizzando la firma che consente di nuovi metadati per la proprietà di dipendenza nello stato attuale per il tipo di aggiunta. Si noti che è necessario fornire [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] funzioni di accesso per la proprietà è simile all'esempio illustrato nel [implementare una proprietà di dipendenza](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) esempio, nonché esporre nuovamente l'identificatore della proprietà di dipendenza nella classe da aggiungere come proprietario.  
  
 Senza wrapper, la proprietà di dipendenza funzionerà comunque dal punto di vista dell'accesso a livello di programmazione utilizzando <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. Ma si desidera in genere parallela di questo comportamento del sistema di proprietà con il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] wrapper della proprietà. I wrapper rendono più semplice impostare la proprietà di dipendenza a livello di codice e consentono di impostare le proprietà come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributi.  
  
 Per informazioni su come eseguire l'override dei metadati predefiniti, vedere [eseguire l'Override dei metadati per una proprietà di dipendenza](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Vedere anche  
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
