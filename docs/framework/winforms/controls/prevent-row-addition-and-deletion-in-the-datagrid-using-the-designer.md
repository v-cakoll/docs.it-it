---
title: "Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: f47eb29bf9ae077555f352d10c667bac4ade9373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968328"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms usando la finestra di progettazione
Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>. Le nuove righe vengono immesse nella riga speciale per i nuovi record nella parte inferiore del controllo. Quando si disabilita l'aggiunta di righe, la riga per i nuovi record non viene visualizzata. È quindi possibile rendere il controllo interamente di sola lettura disabilitando l'eliminazione delle righe e la modifica delle celle.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-prevent-row-addition-and-deletion"></a>Per impedire l'aggiunta e l'eliminazione di righe

- Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell' <xref:System.Windows.Forms.DataGridView> angolo superiore destro del controllo, quindi deselezionare le caselle di controllo **Consenti aggiunta** e **Abilita eliminazione** .

    > [!NOTE]
    > Per rendere il controllo interamente di sola lettura, deselezionare anche la casella di controllo **Abilita modifica** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
