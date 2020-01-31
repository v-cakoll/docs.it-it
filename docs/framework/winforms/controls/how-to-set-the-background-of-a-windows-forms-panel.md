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
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="f35ea-102">Procedura: impostare lo sfondo di un controllo Panel Windows Form</span><span class="sxs-lookup"><span data-stu-id="f35ea-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="f35ea-103">Un controllo Windows Forms <xref:System.Windows.Forms.Panel> può visualizzare sia un colore di sfondo che un'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="f35ea-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="f35ea-104">La proprietà <xref:System.Windows.Forms.Control.BackColor%2A> imposta il colore di sfondo per i controlli contenuti, ad esempio etichette e pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="f35ea-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="f35ea-105">Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, la selezione <xref:System.Windows.Forms.Control.BackColor%2A> compilerà l'intero pannello.</span><span class="sxs-lookup"><span data-stu-id="f35ea-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="f35ea-106">Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, l'immagine verrà visualizzata dietro i controlli contenuti.</span><span class="sxs-lookup"><span data-stu-id="f35ea-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="f35ea-107">Per impostare lo sfondo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f35ea-107">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="f35ea-108">Impostare la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> del pannello su un valore di tipo <xref:System.Drawing.Color?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f35ea-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="f35ea-109">Impostare la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> del pannello usando il metodo <xref:System.Drawing.Image.FromFile%2A> della classe <xref:System.Drawing.Image?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f35ea-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f35ea-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f35ea-110">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="f35ea-111">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="f35ea-111">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="f35ea-112">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="f35ea-112">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
