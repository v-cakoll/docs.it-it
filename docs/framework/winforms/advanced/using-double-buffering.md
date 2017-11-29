---
title: Utilizzo del doppio buffer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5ad51e27c3d31ece1d11831c953023bedba3a97
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="using-double-buffering"></a>Utilizzo del doppio buffer
È possibile utilizzare grafica a doppio buffer per ridurre lo sfarfallio nelle applicazioni che contengono operazioni di disegno complesse. .NET Framework include supporto incorporato per il doppio buffer o è possibile gestire ed eseguire il rendering di grafica manualmente.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Grafica a doppio buffer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Introduce doppio buffering concetto e strutture di supporto di .NET Framework.  
  
 [Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Viene illustrato come utilizzare il valore predefinito il doppio buffer di supporto in .NET Framework.  
  
 [Procedura: Gestire manualmente le immagini memorizzate nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Viene illustrato come gestire il doppio buffer nelle applicazioni.  
  
 [Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Viene illustrato come eseguire il rendering di grafica a doppio buffer.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Metodo di controllo che attiva il doppio buffer.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Fornisce metodi per la creazione di buffer di grafica.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Fornisce l'accesso al contesto di grafica memorizzata nel buffer per un dominio applicazione.
