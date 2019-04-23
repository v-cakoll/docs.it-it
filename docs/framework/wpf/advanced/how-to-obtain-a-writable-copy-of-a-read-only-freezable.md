---
title: 'Procedura: Ottenere una copia scrivibile di un oggetto Freezable di sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206473"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Procedura: Ottenere una copia scrivibile di un oggetto Freezable di sola lettura
Questo esempio illustra come usare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare una copia scrivibile di sola lettura <xref:System.Windows.Freezable>.  
  
 Dopo un <xref:System.Windows.Freezable> oggetto è contrassegnato come di sola lettura ("bloccato"), è possibile modificarla. Tuttavia, è possibile usare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare un clone modificabile dell'oggetto bloccato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un clone modificabile di un oggetto bloccato <xref:System.Windows.Media.SolidColorBrush> oggetto.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Per altre informazioni sulle <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure relative alle proprietà](base-elements-how-to-topics.md)
