---
title: 'Procedura: Impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 9b7102db4de0df7183355e50e3b372eac30d81b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191445"
---
# <a name="how-to-make-a-freezable-read-only"></a>Procedura: Impostare la proprietà di sola lettura per un oggetto Freezable
In questo esempio viene illustrato come effettuare una <xref:System.Windows.Freezable> sola lettura chiamando relativo <xref:System.Windows.Freezable.Freeze%2A> (metodo).  
  
 Non è possibile bloccare una <xref:System.Windows.Freezable> dell'oggetto se una delle condizioni seguenti è `true` sull'oggetto:  
  
-   È stata eseguita l'animazione o le proprietà con associazione a dati.  
  
-   Include proprietà impostate da una risorsa dinamica. Per altre informazioni sulle risorse dinamiche, vedere la [risorse XAML](xaml-resources.md).  
  
-   Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se si verificano queste condizioni `false` per il <xref:System.Windows.Freezable> oggetto e non si intende modificarlo, prendere in considerazione il blocco in modo da migliorare le prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si blocca una <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Per altre informazioni sulle <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure relative alle proprietà](base-elements-how-to-topics.md)
