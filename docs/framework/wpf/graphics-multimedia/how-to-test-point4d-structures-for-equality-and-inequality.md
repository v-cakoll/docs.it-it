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
ms.openlocfilehash: d72aef8a1328742f0b04c2ad009126e21390398a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367206"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="9e7cd-102">Procedura: Verificare l'uguaglianza e la disuguaglianza di strutture Point4D</span><span class="sxs-lookup"><span data-stu-id="9e7cd-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="9e7cd-103">In questo esempio viene illustrato come testare <xref:System.Windows.Media.Media3D.Point4D> strutture di uguaglianza e disuguaglianza.</span><span class="sxs-lookup"><span data-stu-id="9e7cd-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="9e7cd-104">Il codice seguente illustra come testare <xref:System.Windows.Media.Media3D.Point4D> strutture di uguaglianza e disuguaglianza con il <xref:System.Windows.Media.Media3D.Point4D> metodi di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="9e7cd-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="9e7cd-105">Il <xref:System.Windows.Media.Media3D.Point4D> strutture vengono verificate per stabilirne l'uguaglianza mediante l'uguaglianza di overload (`==`) operatore, quindi per verificarne la disuguaglianza con la disuguaglianza di overload (`!=`) (operatore) e infine una <xref:System.Windows.Media.Media3D.Point3D> struttura e un <xref:System.Windows.Media.Media3D.Point4D> struttura vengono verificate per stabilirne l'uguaglianza mediante il metodo statico <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="9e7cd-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e7cd-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e7cd-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="9e7cd-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e7cd-107">See also</span></span>
- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
