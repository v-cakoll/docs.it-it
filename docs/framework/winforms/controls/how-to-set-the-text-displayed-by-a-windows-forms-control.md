---
title: Imposta il testo visualizzato da un controllo
description: Informazioni su come impostare il testo visualizzato da un controllo Windows Forms. Impostare o restituire il testo utilizzando la proprietà Text oppure modificare il tipo di carattere utilizzando la proprietà font.
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 35bae5830bfee8ab91f7b6c7b9dcc6d6b8db00ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622848"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Procedura: impostare il testo visualizzato da un controllo Windows Forms

I controlli Windows Forms in genere visualizzano testo correlato alla funzione primaria del controllo. Un controllo, ad esempio, <xref:System.Windows.Forms.Button> Visualizza in genere una didascalia che indica l'azione che verrà eseguita se si fa clic sul pulsante. Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>. È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.

È anche possibile impostare il testo usando la [finestra di progettazione](#designer).

## <a name="programmatic"></a>Programmatica

1. Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.

   Per creare una chiave di accesso sottolineata, include una e commerciale (&) prima della lettera che sarà il tasto di accesso.

2. Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu. La riga di codice seguente, ad esempio, imposta il testo della voce di menu in modo da leggere "& ora per qualcosa di completamente diverso":

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a>Finestra di progettazione

1. Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** del controllo su una stringa appropriata.

   Per creare un tasto di scelta rapida sottolineato, include una e commerciale (&) prima della lettera che sarà il tasto di scelta rapida.

2. Nella finestra **Proprietà** selezionare il pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio ](./media/visual-studio-ellipsis-button.png) ) accanto alla proprietà **font** .

   Nella finestra di dialogo tipo di carattere standard selezionare il tipo di carattere, lo stile del carattere, le dimensioni, gli effetti (ad esempio, l'attacco o la sottolineatura) e lo script desiderato.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Procedura: creare tasti di scelta per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md)
- [Procedura: rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
