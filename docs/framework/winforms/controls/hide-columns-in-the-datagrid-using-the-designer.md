---
title: Nascondere le colonne nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738662"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: nascondere le colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione
A volte può essere necessario visualizzare solo alcune colonne tra quelle disponibili in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form. È possibile, ad esempio, visualizzare una colonna stipendio dipendente per gli utenti con credenziali di gestione e nasconderla da altri utenti. In alternativa, è possibile associare il controllo a un'origine dati che contiene molte colonne, solo alcune delle quali si desidera visualizzare. In questo caso, si rimuoveranno in genere le colonne di cui non si è interessati a visualizzare anziché nasconderle. Per altre informazioni, vedere [procedura: aggiungere e rimuovere colonne nel controllo DataGridView Windows Forms usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md).

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-hide-a-column-using-the-designer"></a>Per nascondere una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> su `false`.

    > [!NOTE]
    > È inoltre possibile nascondere una colonna quando viene aggiunta deselezionando la casella di controllo **visibile** nella finestra di dialogo **Aggiungi colonna** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Forms](how-to-add-controls-to-windows-forms.md)
