---
title: "Procedura: Impostare l'immagine visualizzata da un controllo di Windows Forms"
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666194"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Procedura: Imposta l'immagine visualizzata da un controllo Windows Forms

Diversi controlli Windows Forms possono visualizzare immagini. Queste immagini possono essere icone che chiariscono lo scopo del controllo, ad esempio un'icona a forma di dischetto in un pulsante che indica il comando Salva. In alternativa, le icone possono essere immagini di sfondo per dare al controllo l'aspetto e il comportamento desiderati.

## <a name="programmatic"></a>A livello

Impostare la proprietà `Image` o `BackgroundImage` del controllo su un oggetto di tipo <xref:System.Drawing.Image>. In genere, è possibile caricare l'immagine da un file usando il <xref:System.Drawing.Image.FromFile%2A> metodo.

Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **Immagini personali** . La maggior parte dei computer che eseguono il sistema operativo Windows include questa directory. Consente inoltre agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro. Nell'esempio di codice seguente è necessario avere già un modulo con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a>Designer

1. Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Image** o **BackgroundImage** del controllo, quindi selezionare i puntini di sospensione (![pulsante con i puntini di sospensione in Visual Studio](./media/visual-studio-ellipsis-button.png)) per visualizzare la **selezione** Finestra di dialogo risorsa.

2. Selezionare l'immagine che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
