---
title: Utilizzo del doppio buffer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716279"
---
# <a name="using-double-buffering"></a>Utilizzo del doppio buffer
È possibile utilizzare grafica a doppio buffer per ridurre lo sfarfallio in applicazioni che prevedono operazioni complesse di disegno. .NET Framework include supporto predefinito per il doppio buffer oppure è possibile gestire ed eseguire il rendering della grafica manualmente.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Grafica a doppio buffer](double-buffered-graphics.md)  
 Introduce doppio buffering concetto e profili di supporto di .NET Framework.  
  
 [Procedura: Ridurre lo sfarfallio nella grafica con il doppio Buffering per form e controlli](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Viene illustrato come utilizzare l'impostazione predefinita il doppio buffer supporto in .NET Framework.  
  
 [Procedura: Gestire manualmente le immagini memorizzate nel buffer](how-to-manually-manage-buffered-graphics.md)  
 Viene illustrato come gestire il doppio buffer nelle applicazioni.  
  
 [Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer](how-to-manually-render-buffered-graphics.md)  
 Viene illustrato come eseguire il rendering di grafica a doppio buffer.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Metodo di controllo che abilita il buffering doppio.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Fornisce metodi per la creazione di buffer di grafica.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Fornisce l'accesso al contesto di grafica memorizzata nel buffer per un dominio dell'applicazione.
