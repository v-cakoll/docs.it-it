---
title: Impostare lo sfondo di un controllo Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182100"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Procedura: impostare lo sfondo di un controllo Panel Windows Form
Un controllo <xref:System.Windows.Forms.Panel> Windows Form può visualizzare sia un colore di sfondo che un'immagine di sfondo. La <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli contenuti, ad esempio etichette e pulsanti di opzione. Se <xref:System.Windows.Forms.Control.BackgroundImage%2A> la proprietà non <xref:System.Windows.Forms.Control.BackColor%2A> è impostata, la selezione riempirà l'intero pannello. Se <xref:System.Windows.Forms.Control.BackgroundImage%2A> la proprietà è impostata, l'immagine verrà visualizzata dietro i controlli contenuti.  
  
### <a name="to-set-the-background-programmatically"></a>Per impostare lo sfondo a livello di codiceTo set the background programmatically  
  
1. Impostare la <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del pannello <xref:System.Drawing.Color?displayProperty=nameWithType>su un valore di tipo .  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Impostare la <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà del <xref:System.Drawing.Image.FromFile%2A> pannello <xref:System.Drawing.Image?displayProperty=nameWithType> utilizzando il metodo della classe .  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Controllo Panel](panel-control-windows-forms.md)
- [Panoramica del controllo Panel](panel-control-overview-windows-forms.md)
