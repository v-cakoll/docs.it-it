---
title: "Procedura: determinare se un oggetto Freezable è bloccato"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5eed85f982687bfc90f53e57ab1ec3949820097e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Procedura: determinare se un oggetto Freezable è bloccato
In questo esempio viene illustrato come determinare se un <xref:System.Windows.Freezable> oggetto è bloccato. Se si tenta di modificare un oggetto bloccato <xref:System.Windows.Freezable> dell'oggetto, genera un <xref:System.InvalidOperationException>. Per evitare la generazione di questa eccezione, utilizzare il <xref:System.Windows.Freezable.IsFrozen%2A> proprietà del <xref:System.Windows.Freezable> oggetto per determinare se è bloccato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush> quindi testato utilizzando le <xref:System.Windows.Freezable.IsFrozen%2A> proprietà per determinare se è bloccato.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Per ulteriori informazioni su <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
