---
title: Aggiungere e rimuovere colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 717a0074f0750352a23b90a9b6e5eab1dc6c925a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732356"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form utilizzando Progettazione Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> Windows Forms deve contenere colonne per visualizzare i dati. Se si prevede di popolare il controllo manualmente, è necessario aggiungere manualmente le colonne. In alternativa, è possibile associare il controllo a un'origine dati che genera e popola automaticamente le colonne. Se l'origine dati contiene più colonne di quelle che si desidera visualizzare, è possibile rimuovere le colonne indesiderate.

 Per le procedure riportate di seguito è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-add-a-column-using-the-designer"></a>Per aggiungere una colonna utilizzando la finestra di progettazione

1. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **Aggiungi colonna**.

2. Nella finestra di dialogo **Aggiungi colonna** scegliere l'opzione **colonna con binding** a dati e selezionare una colonna dall'origine dati oppure scegliere l'opzione **colonna non associata** e definire la colonna utilizzando i campi specificati.

3. Fare clic sul pulsante **Aggiungi** per aggiungere la colonna, facendo in modo che venga visualizzata nella finestra di progettazione se le colonne esistenti non riempiono ancora l'area di visualizzazione del controllo.

    > [!NOTE]
    > È possibile modificare le proprietà delle colonne nella finestra di dialogo **modifica colonne** , a cui è possibile accedere dallo smart tag del controllo.

## <a name="to-remove-a-column-using-the-designer"></a>Per rimuovere una colonna utilizzando la finestra di progettazione

1. Scegliere **modifica colonne** dallo smart tag del controllo.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Fare clic sul pulsante **Rimuovi** per eliminare la colonna, causando la scomparsa dalla finestra di progettazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Forms](how-to-add-controls-to-windows-forms.md)
