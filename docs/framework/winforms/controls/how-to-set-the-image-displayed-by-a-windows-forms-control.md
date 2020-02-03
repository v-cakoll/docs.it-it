---
title: Imposta l'immagine visualizzata da un controllo
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
ms.openlocfilehash: 5df0068c8462bbaab0cb0135de1dd1b91ababe06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746867"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Procedura: impostare l'immagine visualizzata da un controllo Windows Forms

Diversi controlli Windows Forms possono visualizzare immagini. Queste immagini possono essere icone che chiariscono lo scopo del controllo, ad esempio un'icona a forma di dischetto in un pulsante che indica il comando Salva. In alternativa, le icone possono essere immagini di sfondo per dare al controllo l'aspetto e il comportamento desiderati.

## <a name="programmatic"></a>Programmatica

Impostare la proprietà `Image` o `BackgroundImage` del controllo su un oggetto di tipo <xref:System.Drawing.Image>. In genere, è possibile caricare l'immagine da un file usando il metodo <xref:System.Drawing.Image.FromFile%2A>.

Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **Immagini personali** . La maggior parte dei computer che eseguono il sistema operativo Windows include questa directory. Consente inoltre agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro. Nell'esempio di codice seguente è necessario avere già un modulo con un controllo <xref:System.Windows.Forms.PictureBox> aggiunto.

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

1. Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Image** o **BackgroundImage** del controllo, quindi fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione in Visual Studio](./media/visual-studio-ellipsis-button.png)) per visualizzare la finestra di dialogo **Seleziona risorsa** .

2. Selezionare l'immagine che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
