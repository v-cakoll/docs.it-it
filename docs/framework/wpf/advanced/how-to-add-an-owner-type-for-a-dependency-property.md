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
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401127"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Procedura: Aggiungere un tipo di proprietario per una proprietà di dipendenza
In questo esempio viene illustrato come aggiungere una classe come proprietario di una proprietà di dipendenza registrata per un tipo diverso. In questo modo, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Reader e il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sistema di proprietà sono in grado di riconoscere la classe come proprietario aggiuntivo della proprietà. Se si aggiunge come proprietario, facoltativamente, la classe aggiuntiva consente di fornire metadati specifici del tipo.  
  
 Nell'esempio `StateProperty` seguente è una proprietà registrata `MyStateControl` dalla classe. La classe `UnrelatedStateControl` si aggiunge come proprietario dell'oggetto `StateProperty` utilizzando il <xref:System.Windows.DependencyProperty.AddOwner%2A> metodo, specificando in particolare la firma che consente la presenza di nuovi metadati per la proprietà di dipendenza esistente nel tipo di aggiunta. Si noti che è necessario fornire le funzioni di accesso Common Language Runtime (CLR) per la proprietà in modo simile all'esempio illustrato nell'esempio [implementare una proprietà di dipendenza](how-to-implement-a-dependency-property.md) , nonché esporre nuovamente l'identificatore della proprietà di dipendenza nella classe aggiunta come proprietario.  
  
 Senza wrapper, la proprietà di dipendenza continuerà a funzionare dalla prospettiva di accesso a livello <xref:System.Windows.DependencyObject.GetValue%2A> di <xref:System.Windows.DependencyObject.SetValue%2A>codice tramite o. Tuttavia, in genere si desidera eseguire in parallelo questo comportamento del sistema di proprietà con i wrapper della proprietà CLR. I wrapper facilitano l'impostazione della proprietà di dipendenza a livello di codice e consentono di impostare le proprietà come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributi.  
  
 Per informazioni su come eseguire l'override dei metadati predefiniti, vedere [eseguire l'override dei metadati per una proprietà di dipendenza](how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
