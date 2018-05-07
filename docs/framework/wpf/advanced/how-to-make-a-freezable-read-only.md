---
title: 'Procedura: impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: be3abd74a71fc711cd9f4bf6796b7d55017355ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-a-freezable-read-only"></a>Procedura: impostare la proprietà di sola lettura per un oggetto Freezable
Questo esempio viene illustrato come rendere un <xref:System.Windows.Freezable> sola lettura, chiamare il relativo <xref:System.Windows.Freezable.Freeze%2A> (metodo).  
  
 Non è possibile bloccare un <xref:System.Windows.Freezable> oggetto se una qualsiasi delle condizioni seguenti è `true` sull'oggetto:  
  
-   È stata eseguita l'animazione o la proprietà con associazione a dati.  
  
-   Include le proprietà impostate da una risorsa dinamica. Per ulteriori informazioni sulle risorse dinamiche, vedere il [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se queste condizioni sono `false` per il <xref:System.Windows.Freezable> oggetto e non si desidera modificarlo, è consigliabile bloccarlo per migliorare le prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Per ulteriori informazioni su <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
