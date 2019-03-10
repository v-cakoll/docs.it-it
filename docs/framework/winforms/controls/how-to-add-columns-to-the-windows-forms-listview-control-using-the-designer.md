---
title: 'Procedura: Aggiungere colonne al controllo ListView Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 725976e0d4b5903659cc264902890329bd13fcad
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717284"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Procedura: Aggiungere colonne al controllo ListView Windows Form usando la finestra di progettazione
I moduli di Windows <xref:System.Windows.Forms.ListView> controllo può visualizzare più colonne per ogni elenco di elementi nel **dettagli** visualizzazione. È possibile usare le colonne per visualizzare diversi tipi di informazioni su ogni elemento dell'elenco. Ad esempio, un elenco di file è stato possibile visualizzare il nome del file, tipo di file, le dimensioni e data che dell'ultima modifica apportata al file. Per informazioni sulla compilazione delle colonne dopo la creazione, vedere [come: Visualizzare elementi secondari nelle colonne con il Windows Form controllo ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-columns-in-the-designer"></a>Per aggiungere le colonne nella finestra di progettazione  
  
1.  Nel **delle proprietà** finestra, impostare il controllo <xref:System.Windows.Forms.ListView.View%2A> proprietà <xref:System.Windows.Forms.View.Details>.  
  
2.  Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** pulsante (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto a il <xref:System.Windows.Forms.ListView.Columns%2A> proprietà.  
  
     Il **Editor della raccolta ColumnHeader** viene visualizzata.  
  
3.  Usare la **Add** pulsante per aggiungere nuove colonne. È quindi possibile selezionare l'intestazione di colonna e impostare il testo (la didascalia della colonna), l'allineamento del testo e larghezza.  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare le icone per il controllo ListView di Windows Form](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
