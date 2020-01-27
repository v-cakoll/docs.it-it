---
title: Impedisci l'aggiunta e l'eliminazione di righe nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cc9aff0f15d1bd6de5c469ee7069a99f3360837a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728717"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>. Le nuove righe vengono immesse nella riga speciale per i nuovi record nella parte inferiore del controllo. Quando si disabilita l'aggiunta di righe, la riga per i nuovi record non viene visualizzata. È quindi possibile rendere il controllo interamente di sola lettura disabilitando l'eliminazione delle righe e la modifica delle celle.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-prevent-row-addition-and-deletion"></a>Per impedire l'aggiunta e l'eliminazione di righe

- Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi deselezionare le caselle di controllo **Consenti aggiunta** e **Abilita eliminazione** .

    > [!NOTE]
    > Per rendere il controllo interamente di sola lettura, deselezionare anche la casella di controllo **Abilita modifica** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Forms](how-to-add-controls-to-windows-forms.md)
