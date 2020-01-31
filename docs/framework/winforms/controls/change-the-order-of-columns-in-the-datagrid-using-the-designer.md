---
title: Modificare l'ordine delle colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: be4f67ca6530b74fc90cb50a10463b2378edb933
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743151"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: modificare l'ordine delle colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione

Quando si associa un controllo Windows Forms <xref:System.Windows.Forms.DataGridView> a un'origine dati, l'ordine di visualizzazione delle colonne generate automaticamente è determinato dall'origine dati. Se l'ordine non è quello desiderato, è possibile modificare l'ordine delle colonne utilizzando la finestra di progettazione. È anche possibile aggiungere colonne non vincolate al controllo e modificarne l'ordine di visualizzazione. Per informazioni su come modificare l'ordine delle colonne a livello di codice, vedere [procedura: modificare l'ordine delle colonne nel controllo Windows Forms DataGridView](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-change-the-column-order-using-the-designer"></a>Per modificare l'ordine delle colonne utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Fare clic sulla freccia in su o in giù a destra dell'elenco **colonne selezionate** fino a quando la colonna selezionata non si trova nella posizione desiderata.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Forms](how-to-add-controls-to-windows-forms.md)
