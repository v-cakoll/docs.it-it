---
title: 'Procedura: Impostare le colonne come di sola lettura nel controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 6bdd561c863a461f43a5a7aac025fead1f971bb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039814"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Impostare le colonne come di sola lettura nel controllo DataGridView di Windows Forms usando la finestra di progettazione
Per impostazione predefinita, gli utenti possono modificare il testo e i dati numerici <xref:System.Windows.Forms.DataGridView> visualizzati nel controllo Windows Forms. Se si desidera visualizzare dati non destinati alla modifica, è necessario rendere le colonne che contengono i dati di sola lettura. Per informazioni su come rendere il controllo interamente di sola lettura, vedere [How to: Impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView utilizzando](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)la finestra di progettazione.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>Per rendere una colonna di sola lettura tramite la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell' <xref:System.Windows.Forms.DataGridView> angolo superiore destro del controllo, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> proprietà su `true`.

    > [!NOTE]
    >  È inoltre possibile rendere una colonna di sola lettura quando viene aggiunta selezionando la casella di controllo **sola lettura** nella finestra di dialogo **Aggiungi colonna** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Procedura: Aggiungere e rimuovere colonne nel controllo Windows Forms DataGridView utilizzando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Impedisci l'aggiunta e l'eliminazione di righe nel controllo DataGridView Windows Forms usando la finestra di progettazione](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
