---
title: 'Procedura: aggiungere colonne al controllo ListView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 4c284e9d2798a1992e3152a85eca47c8d33bfde8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528284"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Procedura: aggiungere colonne al controllo ListView di Windows Form
Nella visualizzazione dei dettagli, il <xref:System.Windows.Forms.ListView> controllo può visualizzare più colonne per ogni elemento nell'elenco. È possibile utilizzare le colonne da visualizzare all'utente di vari tipi di informazioni su ogni elemento di elenco. Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, dimensioni e data che dell'ultima modifica il file. Per informazioni sulla compilazione delle colonne dopo averli creati, vedere [procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Per aggiungere colonne a livello di codice  
  
1.  Impostare il controllo <xref:System.Windows.Forms.ListView.View%2A> proprietà <xref:System.Windows.Forms.View.Details>.  
  
2.  Utilizzare il <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> metodo per la visualizzazione elenco <xref:System.Windows.Forms.ListView.Columns%2A> proprietà.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
