---
title: 'Procedura: Applicare materiale emissivo a un oggetto 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112154"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a>Procedura: Applicare materiale emissivo a un oggetto 3D
Nell'esempio seguente viene <xref:System.Windows.Media.Media3D.EmissiveMaterial> illustrato come utilizzare per aggiungere un colore a un materiale esistente uguale al colore del pennello di EmissiveMaterial. Il codice <xref:System.Windows.Media.Media3D.DiffuseMaterial> seguente <xref:System.Windows.Media.Media3D.EmissiveMaterial> mostra e applicato in combinazione per aggiungere blu all'aspetto di DiffuseMaterial.  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 Nel codice procedurale:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra l'intero esempio in XAML.  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato l'intero esempio nel codice procedurale.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Animare le proprietà Material in una scena 3D](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto 3D](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
