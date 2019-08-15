---
title: 'Procedura: Nascondere le colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: d502a89913e108254848151e9058ac6ae83a9638
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039780"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Nascondere le colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione
A volte può essere necessario visualizzare solo alcune colonne tra quelle disponibili in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form. È possibile, ad esempio, visualizzare una colonna stipendio dipendente per gli utenti con credenziali di gestione e nasconderla da altri utenti. In alternativa, è possibile associare il controllo a un'origine dati che contiene molte colonne, solo alcune delle quali si desidera visualizzare. In questo caso, si rimuoveranno in genere le colonne di cui non si è interessati a visualizzare anziché nasconderle. Per altre informazioni, vedere [Procedura: Aggiungere e rimuovere colonne nel controllo Windows Forms DataGridView utilizzando la finestra di](add-and-remove-columns-in-the-datagrid-using-the-designer.md)progettazione.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-hide-a-column-using-the-designer"></a>Per nascondere una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell' <xref:System.Windows.Forms.DataGridView> angolo superiore destro del controllo, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> proprietà su `false`.

    > [!NOTE]
    >  È inoltre possibile nascondere una colonna quando viene aggiunta deselezionando la casella di controllo **visibile** nella finestra di dialogo **Aggiungi colonna** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Procedura: Aggiungere e rimuovere colonne nel controllo Windows Forms DataGridView utilizzando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
