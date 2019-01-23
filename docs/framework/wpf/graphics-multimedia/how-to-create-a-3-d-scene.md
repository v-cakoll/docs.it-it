---
title: 'Procedura: Creare una scena tridimensionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 23e01934eac0d9e1ea9fb5fbbbc5d8c9d8aabbc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494380"
---
# <a name="how-to-create-a-3-d-scene"></a>Procedura: Creare una scena tridimensionale
In questo esempio viene illustrato come creare un oggetto 3D che è simile a un foglio di carta cui è stata ruotata. Oggetto <xref:System.Windows.Controls.Viewport3D> insieme ai componenti seguenti vengono usati per creare questa scena 3D semplice:  
  
-   Viene creata una fotocamera utilizzando un <xref:System.Windows.Media.Media3D.PerspectiveCamera>. La fotocamera specifica quale parte della scena 3D è visualizzabile.  
  
-   Viene creata una mesh per specificare la forma dell'oggetto 3D (foglio di carta) utilizzando il <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Viene specificato un materiale da visualizzare sulla superficie dell'oggetto (in questo esempio, una sfumatura lineare) utilizzando il <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Viene creata una luce per gli sviluppatori nell'oggetto utilizzando <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra come creare una scena 3D in XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra come creare la stessa scena 3D in codice procedurale.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sulla grafica tridimensionale](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
