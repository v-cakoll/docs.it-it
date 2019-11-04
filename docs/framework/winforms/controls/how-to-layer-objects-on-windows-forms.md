---
title: 'Procedura: disporre oggetti su più livelli in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5b8f6c00e70df94ae3a82c2c195fa781f0840a53
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458361"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Procedura: eseguire il layer di oggetti su Windows Forms

Quando si crea un'interfaccia utente complessa o si utilizza un form con interfaccia a documenti multipli (MDI), spesso si desidera eseguire il layer di entrambi i controlli e i form figlio per creare interfacce utente (UI) più complesse. Per spostare e tenere traccia dei controlli e delle finestre all'interno del contesto di un gruppo, è possibile modificare l' *ordine z*. L'ordine z è il livello visivo dei controlli in un form lungo l'asse z del form (profondità). La finestra nella parte superiore dello z-order si sovrappone a tutte le altre finestre. Tutte le altre finestre si sovrappongono alla finestra nella parte inferiore dello z-order.

## <a name="to-layer-controls-at-design-time"></a>Per eseguire il livello di controlli in fase di progettazione

1. In Visual Studio selezionare un controllo che si desidera applicare al livello.

2. Scegliere **Order**dal menu **Format** , quindi selezionare **Bring to front** o **Send to back**.

## <a name="to-layer-controls-programmatically"></a>Per livelli di controlli a livello di codice

Usare i metodi <xref:System.Windows.Forms.Control.BringToFront%2A> e <xref:System.Windows.Forms.Control.SendToBack%2A> per modificare l'ordine z dei controlli.

Se, ad esempio, un controllo <xref:System.Windows.Forms.TextBox>, `txtFirstName`, è sotto un altro controllo e si desidera utilizzarlo in primo piano, utilizzare il codice seguente:

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> Windows Forms supporta il *contenimento del controllo*. Il contenimento dei controlli comporta l'inserimento di un numero di controlli all'interno di un controllo contenitore, ad esempio un numero di controlli <xref:System.Windows.Forms.RadioButton> all'interno di un controllo <xref:System.Windows.Forms.GroupBox>. È quindi possibile sovrapporre i controlli all'interno del controllo che lo contiene. Spostando la casella di gruppo si spostano anche i controlli, perché sono contenuti al suo interno.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
