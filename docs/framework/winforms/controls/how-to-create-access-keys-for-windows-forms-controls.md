---
title: 'Procedura: Creare tasti di scelta per i controlli Windows Forms'
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
ms.openlocfilehash: ccec8bba9e01cbaa7bfef841af68a0fcaa720b90
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658385"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Procedura: Creare chiavi di accesso per i controlli Windows Forms

Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante. Con una chiave di accesso, l'utente può fare clic su un pulsante premendo ALT insieme al tasto di accesso predefinito. Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la `Text` relativa proprietà è impostata su "stampa", l'aggiunta di una e commerciale prima della lettera "p" causa la sottolineatura della lettera "p" nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P.

I controlli che non possono ricevere lo stato attivo non possono avere chiavi di accesso.

## <a name="programmatic"></a>A livello

Impostare la `Text` proprietà su una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.

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
- [Procedura: Rispondi a Windows Forms clic sui pulsanti](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Imposta il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
