---
title: 'Procedura: Spostare ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039806"
---
# <a name="how-to-move-toolstripmenuitems"></a>Procedura: Spostare ToolStripMenuItems
In fase di progettazione è possibile spostare interi menu di primo livello e le voci di menu in una posizione diversa <xref:System.Windows.Forms.MenuStrip>in. È anche possibile spostare singole voci di menu tra i menu di primo livello o modificare la posizione delle voci di menu all'interno di un menu.

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Per spostare un menu di primo livello e le voci di menu in un'altra posizione di primo livello

1. Fare clic e tenendo premuto il pulsante sinistro del mouse sul menu che si desidera spostare.

2. Trascinare il punto di inserimento nel menu di primo livello che precede la nuova posizione desiderata e rilasciare il pulsante sinistro del mouse.

     Il menu selezionato si sposta a destra del punto di inserimento.

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Per spostare un menu di primo livello e le voci di menu in un percorso a discesa

1. Fare clic sul menu che si desidera spostare e premere CTRL + X oppure fare clic con il pulsante destro del mouse sul menu e scegliere **taglia** dal menu di scelta rapida.

2. Nel menu di primo livello di destinazione, fare clic sulla voce di menu sopra la nuova posizione desiderata e premere CTRL + V oppure fare clic con il pulsante destro del mouse sulla voce di menu sopra la nuova posizione desiderata e scegliere **Incolla** dal menu di scelta rapida.

     Il menu tagliato viene inserito dopo la voce di menu selezionata.

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Per spostare una voce di menu all'interno di un menu mediante l'editor della raccolta Items

1. Fare clic con il pulsante destro del mouse sul menu che contiene la voce di menu che si desidera spostare.

2. Dal menu di scelta rapida scegliere **Modifica DropDownItems**.

3. Nell' **Editor della raccolta Items**, fare clic sulla voce di menu che si desidera spostare.

4. Fare clic sui tasti freccia su e giù per spostare la voce di menu nel menu.

5. Fare clic su **OK**.

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Per spostare una voce di menu all'interno di un menu utilizzando la tastiera

1. Premere e tenere premuto il tasto ALT.

2. Fare clic e tenendo premuto il pulsante sinistro del mouse sulla voce di menu che si desidera spostare.

3. Trascinare la voce di menu nella nuova posizione e rilasciare il pulsante sinistro del mouse.

## <a name="to-move-a-menu-item-to-another-menu"></a>Per spostare una voce di menu in un altro menu

1. Fare clic sulla voce di menu che si desidera spostare e premere CTRL + X oppure fare clic con il pulsante destro del mouse sulla voce di menu e scegliere **taglia** dal menu di scelta rapida.

2. Fare clic sul menu che conterrà la voce di menu tagliata.

3. Fare clic sulla voce di menu che precede la nuova posizione desiderata e premere CTRL + V oppure fare clic con il pulsante destro del mouse sulla voce di menu che precede la nuova posizione desiderata e selezionare **Incolla** dal menu di scelta rapida.

     La voce di menu tagliata viene inserita dopo la voce di menu selezionata.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)
