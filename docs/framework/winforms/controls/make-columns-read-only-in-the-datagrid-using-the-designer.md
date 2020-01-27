---
title: Rendere le colonne di sola lettura nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 51d9488ef83f7d2c1c01c9ffd756edf8944d738d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744971"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: rendere le colonne di sola lettura nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Per impostazione predefinita, gli utenti possono modificare il testo e i dati numerici visualizzati nell'Windows Forms controllo <xref:System.Windows.Forms.DataGridView>. Se si desidera visualizzare dati non destinati alla modifica, è necessario rendere le colonne che contengono i dati di sola lettura. Per informazioni su come rendere il controllo interamente di sola lettura, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView mediante la finestra di progettazione](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>Per rendere una colonna di sola lettura tramite la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> su `true`.

    > [!NOTE]
    > È inoltre possibile rendere una colonna di sola lettura quando viene aggiunta selezionando la casella di controllo **sola lettura** nella finestra di dialogo **Aggiungi colonna** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Form usando la finestra di progettazione](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Forms](how-to-add-controls-to-windows-forms.md)
