---
title: 'Procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione'
description: Informazioni su come impostare le descrizioni comandi per i controlli a livello di codice o nel Progettazione Windows Form in Visual Studio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618025"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione

È possibile impostare una <xref:System.Windows.Forms.ToolTip> stringa nel codice o nell'progettazione Windows Form in Visual Studio. Per ulteriori informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Impostare una descrizione comando a livello di codice

1. Aggiungere il controllo in cui viene visualizzata la descrizione comando.

2. Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo del <xref:System.Windows.Forms.ToolTip> componente.

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

1. In Visual Studio aggiungere un <xref:System.Windows.Forms.ToolTip> componente al modulo.

2. Consente di selezionare il controllo per la visualizzazione della descrizione comando oppure di aggiungerlo al form.

3. Nella finestra **Proprietà** impostare la **Descrizione comando sul valore ToolTip1 su** una stringa di testo appropriata.

### <a name="to-remove-a-tooltip-programmatically"></a>Per rimuovere una descrizione comando a livello di codice

1. Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo del <xref:System.Windows.Forms.ToolTip> componente.

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

1. In Visual Studio selezionare il controllo che visualizza la descrizione comando.

2. Nella finestra **Proprietà** eliminare il testo nella **Descrizione comando in ToolTip1**.

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Procedura: modificare il ritardo del componente ToolTip di Windows Form](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [Componente ToolTip](tooltip-component-windows-forms.md)
