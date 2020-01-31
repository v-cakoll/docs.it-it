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
ms.openlocfilehash: ba2619354403793aea7ca15d43649da9637079a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744739"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Procedura: impostare lo sfondo di un controllo Panel Windows Form
Un controllo Windows Forms <xref:System.Windows.Forms.Panel> può visualizzare sia un colore di sfondo che un'immagine di sfondo. La proprietà <xref:System.Windows.Forms.Control.BackColor%2A> imposta il colore di sfondo per i controlli contenuti, ad esempio etichette e pulsanti di opzione. Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, la selezione <xref:System.Windows.Forms.Control.BackColor%2A> compilerà l'intero pannello. Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, l'immagine verrà visualizzata dietro i controlli contenuti.  
  
### <a name="to-set-the-background-programmatically"></a>Per impostare lo sfondo a livello di codice  
  
1. Impostare la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> del pannello su un valore di tipo <xref:System.Drawing.Color?displayProperty=nameWithType>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Impostare la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> del pannello usando il metodo <xref:System.Drawing.Image.FromFile%2A> della classe <xref:System.Drawing.Image?displayProperty=nameWithType>.  
  
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
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
