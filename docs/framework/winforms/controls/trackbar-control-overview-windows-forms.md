---
title: Cenni preliminari sul controllo TrackBar
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741464"
---
# <a name="trackbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo TrackBar (Windows Form)
Il controllo Windows Forms <xref:System.Windows.Forms.TrackBar> (anche noto anche come controllo "slider") viene usato per spostarsi tra una grande quantità di informazioni o per modificare visivamente un'impostazione numerica. Il controllo <xref:System.Windows.Forms.TrackBar> è costituito da due parti: il cursore, noto anche come dispositivo di scorrimento, e i segni di graduazione. Il pollice è la parte che può essere regolata. La posizione corrisponde alla proprietà <xref:System.Windows.Forms.TrackBar.Value%2A>. I segni di graduazione sono indicatori visivi spaziati a intervalli regolari. Il controllo TrackBar si sposta in incrementi specificati e può essere allineato orizzontalmente o verticalmente. Ad esempio, è possibile usare l'indicatore di avanzamento per controllare la velocità del cursore o la velocità del mouse per un sistema.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà chiave del controllo <xref:System.Windows.Forms.TrackBar> sono <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>e <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> è la spaziatura dei cicli. <xref:System.Windows.Forms.TrackBar.Minimum%2A> e <xref:System.Windows.Forms.TrackBar.Maximum%2A> sono i valori più piccoli e più grandi che possono essere rappresentati sull'indicatore di avanzamento.  
  
 Altre due proprietà importanti sono <xref:System.Windows.Forms.TrackBar.SmallChange%2A> e <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Il valore della proprietà <xref:System.Windows.Forms.TrackBar.SmallChange%2A> è il numero di posizioni in cui il cursore si sposta in risposta alla pressione del tasto freccia sinistra o destra. Il valore della proprietà <xref:System.Windows.Forms.TrackBar.LargeChange%2A> è il numero di posizioni in cui il cursore si sposta in risposta alla pressione della pagina o del tasto PGGIÙ oppure in risposta ai clic del mouse sulla barra di avanzamento su entrambi i lati del cursore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TrackBar>
- [Controllo TrackBar](trackbar-control-windows-forms.md)
