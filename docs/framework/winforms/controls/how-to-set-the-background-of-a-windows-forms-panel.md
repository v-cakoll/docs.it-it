---
title: 'Procedura: Impostare lo sfondo di un controllo Panel Windows Form'
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
ms.openlocfilehash: 9336be2aebb10e5c0bd0bf4648cae34a3b5fe7c3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300404"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="a5073-102">Procedura: Impostare lo sfondo di un controllo Panel Windows Form</span><span class="sxs-lookup"><span data-stu-id="a5073-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="a5073-103">Un controllo Windows Form <xref:System.Windows.Forms.Panel> controllo può visualizzare un colore di sfondo sia un'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="a5073-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="a5073-104">Il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli contenuti, ad esempio etichette e i pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="a5073-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="a5073-105">Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, il <xref:System.Windows.Forms.Control.BackColor%2A> selezione riempirà l'intero pannello.</span><span class="sxs-lookup"><span data-stu-id="a5073-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="a5073-106">Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, verrà visualizzata l'immagine dietro i controlli contenuti.</span><span class="sxs-lookup"><span data-stu-id="a5073-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="a5073-107">Per impostare lo sfondo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a5073-107">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="a5073-108">Impostare il pannello <xref:System.Windows.Forms.Control.BackColor%2A> la proprietà su un valore di tipo <xref:System.Drawing.Color?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5073-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="a5073-109">Impostare il pannello <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà usando la <xref:System.Drawing.Image.FromFile%2A> metodo del <xref:System.Drawing.Image?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="a5073-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5073-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5073-110">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="a5073-111">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="a5073-111">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="a5073-112">Panoramica del controllo Panel</span><span class="sxs-lookup"><span data-stu-id="a5073-112">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
