---
title: Creare chiavi di accesso per i controlli
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731165"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Procedura: creare chiavi di accesso per controlli Windows Forms

Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante. Con una chiave di accesso, l'utente può fare clic su un pulsante premendo ALT insieme al tasto di accesso predefinito. Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la relativa proprietà `Text` è impostata su "stampa", aggiungendo una e commerciale prima della lettera "P", la lettera "P" sarà sottolineata nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P.

I controlli che non possono ricevere lo stato attivo non possono avere chiavi di accesso.

## <a name="programmatic"></a>A livello

Impostare la proprietà `Text` su una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> Per usare una e commerciale in una didascalia senza creare una chiave di accesso, includere due e commerciale (& &). Una singola e commerciale viene visualizzata nella didascalia e nessun carattere è sottolineato.

## <a name="designer"></a>Designer

Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** su una stringa che include una e commerciale (' &') prima della lettera che sarà il tasto di accesso. Ad esempio, per impostare la lettera "P" come chiave di accesso, immettere **& stampa**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Impostare il testo visualizzato da un controllo Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
