---
title: "Procedura: verificare l'uguaglianza e la disuguaglianza di strutture Point4D"
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: 1ec844c8fb0aceaaec6030c2e9d5cb30cf984f43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
