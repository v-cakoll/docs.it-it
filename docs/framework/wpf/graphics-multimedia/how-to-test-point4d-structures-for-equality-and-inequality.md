---
title: "Procedura: Verificare l'uguaglianza e la disuguaglianza di strutture Point4D"
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050636"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>Procedura: Verificare l'uguaglianza e la disuguaglianza di strutture Point4D
In questo esempio viene illustrato come testare <xref:System.Windows.Media.Media3D.Point4D> strutture di uguaglianza e disuguaglianza.  
  
 Il codice seguente illustra come testare <xref:System.Windows.Media.Media3D.Point4D> strutture di uguaglianza e disuguaglianza con il <xref:System.Windows.Media.Media3D.Point4D> metodi di uguaglianza.  Il <xref:System.Windows.Media.Media3D.Point4D> strutture vengono verificate per stabilirne l'uguaglianza mediante l'uguaglianza di overload (`==`) operatore, quindi per verificarne la disuguaglianza con la disuguaglianza di overload (`!=`) (operatore) e infine una <xref:System.Windows.Media.Media3D.Point3D> struttura e un <xref:System.Windows.Media.Media3D.Point4D> struttura vengono verificate per stabilirne l'uguaglianza mediante il metodo statico <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> (metodo).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
