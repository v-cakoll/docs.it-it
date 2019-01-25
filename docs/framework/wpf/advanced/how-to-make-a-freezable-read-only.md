---
title: 'Procedura: Impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: e0cc5d73f9b9f15fc02bf20a70c84da1a7c535c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671668"
---
# <a name="how-to-make-a-freezable-read-only"></a>Procedura: Impostare la proprietà di sola lettura per un oggetto Freezable
In questo esempio viene illustrato come effettuare una <xref:System.Windows.Freezable> sola lettura chiamando relativo <xref:System.Windows.Freezable.Freeze%2A> (metodo).  
  
 Non è possibile bloccare una <xref:System.Windows.Freezable> dell'oggetto se una delle condizioni seguenti è `true` sull'oggetto:  
  
-   È stata eseguita l'animazione o le proprietà con associazione a dati.  
  
-   Include proprietà impostate da una risorsa dinamica. Per altre informazioni sulle risorse dinamiche, vedere la [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se si verificano queste condizioni `false` per il <xref:System.Windows.Freezable> oggetto e non si intende modificarlo, prendere in considerazione il blocco in modo da migliorare le prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si blocca una <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Per altre informazioni sulle <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
