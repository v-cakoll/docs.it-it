---
title: 'Procedura: impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460066"
---
# <a name="how-to-make-a-freezable-read-only"></a>Procedura: impostare la proprietà di sola lettura per un oggetto Freezable
In questo esempio viene illustrato come creare un <xref:System.Windows.Freezable> di sola lettura chiamando il relativo metodo <xref:System.Windows.Freezable.Freeze%2A>.  
  
 Non è possibile bloccare un oggetto <xref:System.Windows.Freezable> se una delle condizioni seguenti è `true` sull'oggetto:  
  
- Dispone di proprietà animate o con associazione a dati.  
  
- Dispone di proprietà impostate da una risorsa dinamica. Per ulteriori informazioni sulle risorse dinamiche, vedere le [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se queste condizioni vengono `false` per l'oggetto <xref:System.Windows.Freezable> e non si intende modificarle, provare a bloccarlo per ottenere vantaggi in termini di prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Per ulteriori informazioni sugli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure relative alle proprietà](base-elements-how-to-topics.md)
