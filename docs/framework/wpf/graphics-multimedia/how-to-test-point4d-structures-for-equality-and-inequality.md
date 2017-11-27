---
title: 'Procedura: verificare l''uguaglianza e la disuguaglianza di strutture Point4D'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 849082fc1b933c4172c0d22ec3c9c2a1644a32fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>Procedura: verificare l'uguaglianza e la disuguaglianza di strutture Point4D
Questo esempio viene illustrato come testare <xref:System.Windows.Media.Media3D.Point4D> strutture di uguaglianza e disuguaglianza.  
  
 Il codice seguente viene illustrato come verificare <xref:System.Windows.Media.Media3D.Point4D> l'uguaglianza e disuguaglianza con strutture di <xref:System.Windows.Media.Media3D.Point4D> metodi di uguaglianza.  Il <xref:System.Windows.Media.Media3D.Point4D> strutture vengono testate per verificarne l'uguaglianza con l'overload di uguaglianza (`==`) (operatore), quindi per stabilirne la disuguaglianza utilizzando la disuguaglianza di overload (`!=`) (operatore) e infine un <xref:System.Windows.Media.Media3D.Point3D> struttura e un <xref:System.Windows.Media.Media3D.Point4D> verifica dell'uguaglianza utilizzando il metodo statico <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> metodo.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
