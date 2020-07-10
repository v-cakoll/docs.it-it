---
title: Impostare lo sfondo di un controllo Panel
description: Informazioni su come impostare il colore di sfondo e l'immagine di sfondo di un pannello di Windows Forms usando la finestra di progettazione.
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
ms.openlocfilehash: 109ff6184de9c79d1576207bbeb29ad939670b6f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173380"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Procedura: impostare lo sfondo di un controllo Panel Windows Form
Un <xref:System.Windows.Forms.Panel> controllo Windows Forms può visualizzare sia un colore di sfondo che un'immagine di sfondo. La <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli contenuti, ad esempio etichette e pulsanti di opzione. Se la <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà non è impostata, la <xref:System.Windows.Forms.Control.BackColor%2A> selezione compilerà l'intero pannello. Se la <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà è impostata, l'immagine verrà visualizzata dietro i controlli contenuti.  
  
### <a name="to-set-the-background-programmatically"></a>Per impostare lo sfondo a livello di codice  
  
1. Impostare la proprietà del pannello <xref:System.Windows.Forms.Control.BackColor%2A> su un valore di tipo <xref:System.Drawing.Color?displayProperty=nameWithType> .  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Impostare la proprietà del pannello <xref:System.Windows.Forms.Control.BackgroundImage%2A> usando il <xref:System.Drawing.Image.FromFile%2A> metodo della <xref:System.Drawing.Image?displayProperty=nameWithType> classe.  
  
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
