---
title: 'Procedura: Determinare se un oggetto Freezable è bloccato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776233"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Procedura: Determinare se un oggetto Freezable è bloccato
In questo esempio viene illustrato come determinare se un <xref:System.Windows.Freezable> oggetto è stato bloccato. Se si prova a modificare un oggetto bloccato <xref:System.Windows.Freezable> dell'oggetto, genera un <xref:System.InvalidOperationException>. Per evitare la generazione di questa eccezione, usare il <xref:System.Windows.Freezable.IsFrozen%2A> proprietà del <xref:System.Windows.Freezable> oggetto per determinare se è bloccato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si blocca una <xref:System.Windows.Media.SolidColorBrush> e quindi verifica l'evento utilizzando il <xref:System.Windows.Freezable.IsFrozen%2A> proprietà per determinare se è bloccato.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Per altre informazioni sulle <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure relative alle proprietà](base-elements-how-to-topics.md)
