---
title: 'Procedura: abilitare la visualizzazione affiancata in un controllo ListView Windows Form mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36b20f4ee5bed6f81c42225f35083d51fb2a6308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: abilitare la visualizzazione affiancata in un controllo ListView Windows Form mediante la finestra di progettazione
La funzionalità di visualizzazione del riquadro di <xref:System.Windows.Forms.ListView> controllo consente di fornire un equilibrio visivo tra informazioni grafiche e testuali. Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli. La visualizzazione affiancata agisce in combinazione con l'inserimento o di raggruppamento contrassegnare le funzionalità di <xref:System.Windows.Forms.ListView> controllo.  
  
 La visualizzazione affiancata Usa un'icona di 32 x 32 e alcune righe di testo, come illustrato nella figura seguente.  
  
 ![Visualizzazione affiancata in un controllo ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Il riquadro proprietà e metodi consentono di specificare i campi colonna da visualizzare per ogni elemento e di controllare le dimensioni e l'aspetto di tutti gli elementi all'interno di una finestra di visualizzazione del riquadro di visualizzazione. Per maggiore chiarezza, la prima riga di testo in un riquadro è sempre il nome dell'elemento; non può essere modificata.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  La visualizzazione affiancata è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Nei sistemi operativi precedenti, qualsiasi codice correlato alla visualizzazione affiancata non ha alcun effetto e il controllo <xref:System.Windows.Forms.ListView> viene visualizzato nella visualizzazione Icone grandi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Per impostare la visualizzazione affiancata nella finestra di progettazione  
  
1.  Selezionare il <xref:System.Windows.Forms.ListView> controllo sul form.  
  
2.  Nel **proprietà** finestra, seleziona il <xref:System.Windows.Forms.ListView.View%2A> proprietà e scegliere **riquadro**.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Funzionalità di Windows XP e controlli di Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
