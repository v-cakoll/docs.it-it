---
title: Utilizzo dei contenitori di grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: 8755a95434d3fed06a55cfca0f71d86e5521cb39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525021"
---
# <a name="using-graphics-containers"></a>Utilizzo dei contenitori di grafica
Oggetto <xref:System.Drawing.Graphics> oggetto fornisce metodi, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, e <xref:System.Drawing.Graphics.DrawString%2A> per la visualizzazione di testo, immagini raster e immagini vettoriali. Oggetto <xref:System.Drawing.Graphics> oggetto dispone inoltre di diverse proprietà che determinano la qualità e l'orientamento degli elementi da cui vengono disegnate. Ad esempio, la proprietà modalità di arrotondamento determina se l'anti-aliasing viene applicato a linee e curve, e la proprietà di trasformazione world influenza la posizione e la rotazione di elementi che vengono disegnate.  
  
 Oggetto <xref:System.Drawing.Graphics> oggetto è associato a un particolare dispositivo di visualizzazione. Quando si utilizza un <xref:System.Drawing.Graphics> oggetto da disegnare in una finestra di <xref:System.Drawing.Graphics> oggetto è anche associato a quel particolare finestra.  
  
 Oggetto <xref:System.Drawing.Graphics> oggetto può essere considerato come un contenitore poiché contiene un set di proprietà che influenza il disegno e collegarla a informazioni specifiche del dispositivo. È possibile creare un contenitore secondario all'interno di un oggetto esistente <xref:System.Drawing.Graphics> oggetto chiamando il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo che <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Gestione dello stato di un oggetto Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Viene descritto come gestire le impostazioni relative alla qualità, area di ritaglio e trasformazioni di un <xref:System.Drawing.Graphics> oggetto.  
  
 [Uso di contenitori di grafica annidati](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Di seguito viene illustrato come utilizzare i contenitori per controllare lo stato del <xref:System.Drawing.Graphics> oggetto.
