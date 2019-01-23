---
title: 'Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: eccac1b3b02da41a34d47072be267f6c51a7d490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504561"
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater (Visual Studio)
Intestazione dell'elemento in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo fornisce un indicatore visivo quando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> sia selezionata. Quando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (impostazione predefinita), l'intestazione dell'elemento viene visualizzato a sinistra di ciascun elemento. Quando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, l'intestazione dell'elemento viene visualizzato nella parte superiore di ogni elemento.  
  
 Quando viene selezionato prima di tutto, l'intestazione dell'elemento viene visualizzato nel colore specificato da di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> proprietà e un'icona di freccia bianca viene visualizzata.  
  
> [!NOTE]
>  Se si imposta la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, il simbolo di selezione non saranno visibile quando l'elemento prima di tutto è selezionato.  
  
 Quando un campo del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ha lo stato attivo, il colore dell'elemento intestazione passa per la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> colore di sfondo e le modifiche sull'icona di freccia su nero. Se i dati viene modificati, viene visualizzato un simbolo a forma di matita nell'intestazione dell'elemento.  
  
 La larghezza predefinita (o dell'altezza quando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) dell'elemento intestazione è di 15 pixel. È possibile modificare la larghezza impostando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà.  
  
> [!NOTE]
>  Se il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà è impostata su un valore che è minore di 11, non verranno visualizzati i simboli di indicatore nell'intestazione dell'elemento.  
  
 È possibile nascondere le intestazioni degli elementi impostando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> proprietà **False**. Quando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> è impostata su **False**, la sola indicazione che è selezionato un elemento è una linea tratteggiata attorno al perimetro del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  È anche possibile fornire un indicatore di selezione mediante il monitoraggio di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> proprietà del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>Per modificare l'aspetto delle intestazioni elementi  
  
1.  Nella finestra di progettazione Windows Form, selezionare l'area inferiore del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare l'area inferiore del controllo. Se si seleziona l'area del modello di elemento, verrà visualizzato un diverso set di proprietà nella finestra Proprietà.  
  
2.  Nella finestra Proprietà, usare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> proprietà per modificare il colore delle intestazioni degli elementi.  
  
    > [!NOTE]
    >  Se si imposta la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, il simbolo di selezione non saranno visibile quando l'elemento prima di tutto è selezionato.  
  
3.  Usare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà da modificare la larghezza (o l'altezza) delle intestazioni degli elementi.  
  
    > [!NOTE]
    >  Se il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà è impostata su un valore che è minore di 11, non verranno visualizzati i simboli di indicatore nell'intestazione dell'elemento.  
  
### <a name="to-hide-item-headers"></a>Per nascondere le intestazioni degli elementi  
  
1.  Nella finestra di progettazione Windows Form, selezionare l'area inferiore del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare l'area inferiore del controllo. Se si seleziona l'area del modello di elemento, verrà visualizzato un diverso set di proprietà nella finestra Proprietà.  
  
2.  Nella finestra Proprietà impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> proprietà **False**.  
  
     Quando un elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è selezionata, l'unica indicazione sarà una linea tratteggiata attorno al perimetro del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Procedura: Modificare il Layout di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
