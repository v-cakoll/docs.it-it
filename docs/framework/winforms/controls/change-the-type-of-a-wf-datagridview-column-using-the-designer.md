---
title: 'Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e0b0b01a3c6da0680a3ec5fcd591344e04658a37
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917615"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione
In alcuni casi è necessario modificare il tipo di una colonna che è già stata aggiunta a un controllo <xref:System.Windows.Forms.DataGridView> Windows Forms. È ad esempio possibile che si desideri modificare i tipi di alcune colonne generate automaticamente quando si associa il controllo a un'origine dati. Questa operazione è utile quando nella tabella visualizzata sono presenti colonne contenenti chiavi esterne alle righe di una tabella correlata. In questo caso, è possibile sostituire le colonne della casella di testo in cui vengono visualizzate le chiavi esterne con le colonne della casella combinata che visualizzano valori più significativi della tabella correlata.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Per modificare il tipo di una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell' <xref:System.Windows.Forms.DataGridView> angolo superiore destro del controllo, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** impostare la `ColumnType` proprietà sul nuovo tipo di colonna.

    > [!NOTE]
    > La `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna. Non si tratta di una proprietà effettiva definita in una classe Column.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
