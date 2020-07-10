---
title: Aggiunta di colonne al controllo ListView
description: Informazioni su come aggiungere colonne al controllo Windows Forms ListView per visualizzare diversi tipi di informazioni su ogni elemento dell'elenco.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 7ca4e86ca3a9679876f2525c49596534f175096a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174562"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Procedura: aggiungere colonne al controllo ListView di Windows Form
Nella visualizzazione dettagli, il <xref:System.Windows.Forms.ListView> controllo può visualizzare più colonne per ogni elemento dell'elenco. È possibile utilizzare le colonne per visualizzare all'utente diversi tipi di informazioni su ogni elemento dell'elenco. Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, le dimensioni e la data dell'Ultima modifica del file. Per informazioni sul popolamento delle colonne dopo la creazione, vedere [procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Per aggiungere colonne a livello di codice  
  
1. Impostare la proprietà del controllo <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Details> .  
  
2. Usare il <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> metodo della proprietà della visualizzazione elenco <xref:System.Windows.Forms.ListView.Columns%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Cenni preliminari sul controllo ListView](listview-control-overview-windows-forms.md)
