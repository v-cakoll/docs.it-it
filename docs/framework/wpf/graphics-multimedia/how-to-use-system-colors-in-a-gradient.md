---
title: 'Procedura: utilizzare i colori di sistema in una sfumatura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 105e22588f68d999811f5482342d53851a4d25eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>Procedura: utilizzare i colori di sistema in una sfumatura
Per utilizzare un colore di sistema in una sfumatura, si utilizza il  *\<SystemColor >*colore e  *\<SystemColor >*ColorKey proprietà statiche della <xref:System.Windows.SystemColors> classe per ottenere un riferimento al colore, in cui  *\<SystemColor >* è il nome del colore di sistema desiderato. Utilizzare il  *\<SystemColor >*ColorKey proprietà quando si desidera creare un riferimento dinamico viene aggiornato automaticamente quando cambia il tema del sistema. In caso contrario, utilizzare il  *\<SystemColor >*proprietà dei colori.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa risorse di colore di sistema dinamiche per creare una sfumatura.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 L'esempio seguente usa risorse di colore di sistema statiche per creare una sfumatura.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.SystemColors>  
 [Disegnare un'area con un pennello di sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
