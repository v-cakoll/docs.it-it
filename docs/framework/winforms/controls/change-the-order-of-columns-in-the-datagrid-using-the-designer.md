---
title: "Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: bf77cf3705a470bbe00be383f6a5cb2d28bda34d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039627"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione

Quando si associa un controllo <xref:System.Windows.Forms.DataGridView> Windows Forms a un'origine dati, l'ordine di visualizzazione delle colonne generate automaticamente è determinato dall'origine dati. Se l'ordine non è quello desiderato, è possibile modificare l'ordine delle colonne utilizzando la finestra di progettazione. È anche possibile aggiungere colonne non vincolate al controllo e modificarne l'ordine di visualizzazione. Per informazioni su come modificare l'ordine delle colonne a livello di codice [, vedere Procedura: Modificare l'ordine delle colonne nel controllo](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-change-the-column-order-using-the-designer"></a>Per modificare l'ordine delle colonne utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell' <xref:System.Windows.Forms.DataGridView> angolo superiore destro del controllo, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Fare clic sulla freccia in su o in giù a destra dell'elenco **colonne selezionate** fino a quando la colonna selezionata non si trova nella posizione desiderata.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Procedura: Aggiungere e rimuovere colonne nel controllo Windows Forms DataGridView utilizzando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
