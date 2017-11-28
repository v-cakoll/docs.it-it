---
title: 'Procedura: visualizzare le intestazioni degli elementi in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da02f9374471a581a58131e26d618f91d7cbb7af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Procedura: visualizzare le intestazioni degli elementi in un controllo DataRepeater (Visual Studio)
Intestazione dell'elemento in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo agisce da indicatore visivo quando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> è selezionata. Quando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (impostazione predefinita), l'intestazione dell'elemento viene visualizzato a sinistra di ciascun elemento. Quando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, l'intestazione dell'elemento viene visualizzato nella parte superiore di ogni elemento.  
  
 Quando è selezionata prima, l'intestazione dell'elemento viene visualizzato il colore specificato da di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> , proprietà e un'icona di freccia bianca viene visualizzata.  
  
> [!NOTE]
>  Se si imposta la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, il simbolo di selezione non sarà visibile quando l'elemento è selezionato prima.  
  
 Quando un campo del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ha lo stato attivo, il colore dell'elemento intestazione passa per la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> colore e le modifiche di icona freccia su nero in background. Se i dati vengono modificati, viene visualizzato un simbolo di matita nell'intestazione dell'elemento.  
  
 La larghezza predefinita (o dell'altezza quando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) dell'elemento intestazione è di 15 pixel. È possibile modificare la larghezza impostando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà.  
  
> [!NOTE]
>  Se il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> è impostata su un valore che è minore di 11, non verranno visualizzati i simboli di indicatore nell'intestazione dell'elemento.  
  
 È possibile nascondere le intestazioni degli elementi impostando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> proprietà **False**. Quando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> è impostato su **False**, l'unica indicazione che è stato selezionato un elemento è una linea punteggiata attorno al perimetro di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  È anche possibile fornire un indicatore di selezione monitorando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> proprietà del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>Per modificare l'aspetto delle intestazioni degli elementi  
  
1.  In Progettazione Windows Form, selezionare l'area inferiore del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare l'area inferiore del controllo. Se si seleziona l'area del modello di elemento, verrà visualizzato un set di proprietà diverso nella finestra Proprietà.  
  
2.  Nella finestra Proprietà, utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> proprietà per modificare il colore delle intestazioni degli elementi.  
  
    > [!NOTE]
    >  Se si imposta la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, il simbolo di selezione non sarà visibile quando l'elemento è selezionato prima.  
  
3.  Utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà per modificare la larghezza (o dell'altezza) delle intestazioni degli elementi.  
  
    > [!NOTE]
    >  Se il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> è impostata su un valore che è minore di 11, non verranno visualizzati i simboli di indicatore nell'intestazione dell'elemento.  
  
### <a name="to-hide-item-headers"></a>Per nascondere le intestazioni degli elementi  
  
1.  In Progettazione Windows Form, selezionare l'area inferiore del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare l'area inferiore del controllo. Se si seleziona l'area del modello di elemento, verrà visualizzato un set di proprietà diverso nella finestra Proprietà.  
  
2.  Nella finestra Proprietà impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> proprietà **False**.  
  
     Quando un elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è selezionata, l'unica indicazione sarà intorno al perimetro di una linea punteggiata il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Procedura: Modificare il layout di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
