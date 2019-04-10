---
title: 'Procedura: Dividere una finestra orizzontalmente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: a43d632a82678f362a1cdf6b3ee4486a8db5adde
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321081"
---
# <a name="how-to-split-a-window-horizontally"></a>Procedura: Dividere una finestra orizzontalmente
Esempio di codice seguente effettua il divisore che divide il <xref:System.Windows.Forms.SplitContainer> controllo orizzontale.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo determina la direzione della barra di divisione, non del controllo stesso.  
  
### <a name="to-split-a-window-horizontally"></a>Per suddividere una finestra orizzontalmente  
  
1. All'interno di una procedura, impostare il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
