---
title: Bloccare le colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: af8e07d7b1b0524e33688fd9d879818aa13be041
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745675"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: bloccare le colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Quando gli utenti visualizzano i dati contenuti in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form, a volte devono fare spesso riferimento a una sola colonna o a un set di colonne. Ad esempio, quando si visualizza una tabella di informazioni sui clienti che contiene molte colonne, è utile visualizzare il nome del cliente in qualsiasi momento, pur consentendo ad altre colonne di scorrere al di fuori dell'area visibile.

 A tale scopo, è possibile bloccare le colonne nel controllo. Quando si blocca una colonna, vengono bloccate anche tutte le colonne alla sua sinistra (o alla sua destra, nelle lingue scritte da destra a sinistra). Le colonne bloccate rimangono ferme mentre tutte le altre colonne possono scorrere. Se viene abilitato il riordinamento delle colonne, le colonne bloccate vengono considerate come un gruppo distinto dalle colonne non bloccate. Gli utenti possono riposizionare le colonne in entrambi i gruppi, ma non possono spostare una colonna da un gruppo all'altro.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-freeze-a-column-using-the-designer"></a>Per bloccare una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> su `true`.

    > [!NOTE]
    > È inoltre possibile bloccare una colonna quando viene aggiunta selezionando la casella **bloccati** nella finestra di dialogo **Aggiungi colonna** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [Procedura: visualizzare il testo da destra a sinistra in Windows Forms per la globalizzazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Forms](how-to-add-controls-to-windows-forms.md)
