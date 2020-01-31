---
title: Aggiunta di colonne al controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744578"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Procedura: Aggiungere colonne al controllo ListView di Windows Form
Nella visualizzazione dettagli il controllo <xref:System.Windows.Forms.ListView> può visualizzare più colonne per ogni elemento dell'elenco. È possibile utilizzare le colonne per visualizzare all'utente diversi tipi di informazioni su ogni elemento dell'elenco. Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, le dimensioni e la data dell'Ultima modifica del file. Per informazioni sul popolamento delle colonne dopo la creazione, vedere [procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Per aggiungere colonne a livello di codice  
  
1. Impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> del controllo su <xref:System.Windows.Forms.View.Details>.  
  
2. Usare il metodo <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> della proprietà <xref:System.Windows.Forms.ListView.Columns%2A> della visualizzazione elenco.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
