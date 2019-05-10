---
title: 'Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211692"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione

È possibile impostare un <xref:System.Windows.Forms.ToolTip> stringa nel codice o nella finestra di progettazione Windows Form in Visual Studio. Per altre informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Impostare una descrizione comandi a livello di codice

1. Aggiungere il controllo che verrà visualizzata la descrizione comando.

2. Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a>Impostare una descrizione comando nella finestra di progettazione

1. In Visual Studio, aggiungere un <xref:System.Windows.Forms.ToolTip> componente al form.

2. Selezionare il controllo che consente di visualizzare la descrizione comando o aggiungerlo al form.

3. Nel **proprietà** impostare nella finestra di **descrizione comando su ToolTip1** valore da una stringa di testo appropriata.

### <a name="to-remove-a-tooltip-programmatically"></a>Per rimuovere una descrizione comandi a livello di codice

1. Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a>Rimuovere una descrizione comando nella finestra di progettazione

1. In Visual Studio, selezionare il controllo che visualizza la descrizione comando.

2. Nel **delle proprietà** finestra, eliminare il testo nel **descrizione comando su ToolTip1**.

## <a name="see-also"></a>Vedere anche

- [Panoramica sul componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Procedura: Modifica del ritardo del componente di descrizione comando di Windows Form](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [Componente ToolTip](tooltip-component-windows-forms.md)
