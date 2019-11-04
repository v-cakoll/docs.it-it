---
title: 'Procedura: specificare una bitmap nella casella degli strumenti per un controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 61f60aaeab904dff80408a1dc46c2882fb5e22b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458319"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="68f25-102">Procedura: specificare una bitmap nella casella degli strumenti per un controllo</span><span class="sxs-lookup"><span data-stu-id="68f25-102">How to: Provide a Toolbox Bitmap for a Control</span></span>

<span data-ttu-id="68f25-103">Se si vuole che venga visualizzata un'icona speciale per il controllo nella **casella degli strumenti** di Visual Studio, è possibile specificare una particolare immagine usando il <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="68f25-103">If you want to have a special icon for your control appear in the **Toolbox** of Visual Studio, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="68f25-104">Questa classe è un *attributo*, un tipo speciale di classe che è possibile allegare ad altre classi.</span><span class="sxs-lookup"><span data-stu-id="68f25-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="68f25-105">Per ulteriori informazioni sugli attributi, vedere [Cenni preliminari sugli attributi (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) per Visual Basic o [attributiC#()](../../../csharp/programming-guide/concepts/attributes/index.md) per. C#</span><span class="sxs-lookup"><span data-stu-id="68f25-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>

<span data-ttu-id="68f25-106">Utilizzando la <xref:System.Drawing.ToolboxBitmapAttribute>, è possibile specificare una stringa che indica il percorso e il nome del file per una bitmap di 16 per 16 pixel.</span><span class="sxs-lookup"><span data-stu-id="68f25-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="68f25-107">Questa bitmap viene quindi visualizzata accanto al controllo quando è aggiunta alla **Casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="68f25-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="68f25-108">È anche possibile specificare un <xref:System.Type>. in questo caso, viene caricata la bitmap associata a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="68f25-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="68f25-109">Se si specifica sia un <xref:System.Type> che una stringa, il controllo Cerca una risorsa immagine con il nome specificato dal parametro stringa nell'assembly contenente il tipo specificato dal parametro <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="68f25-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="68f25-110">Per specificare una bitmap della casella degli strumenti per il controllo</span><span class="sxs-lookup"><span data-stu-id="68f25-110">To specify a Toolbox bitmap for your control</span></span>

1. <span data-ttu-id="68f25-111">Aggiungere la <xref:System.Drawing.ToolboxBitmapAttribute> alla dichiarazione di classe del controllo prima della parola chiave `Class` per Visual Basic e sopra la dichiarazione di classe per Visual C#.</span><span class="sxs-lookup"><span data-stu-id="68f25-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. <span data-ttu-id="68f25-112">Ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="68f25-112">Rebuild the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68f25-113">La bitmap non viene visualizzata nella casella degli strumenti per i controlli e i componenti generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="68f25-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="68f25-114">Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="68f25-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="68f25-115">Per altre informazioni, vedere [Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="68f25-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68f25-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68f25-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="68f25-117">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="68f25-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="68f25-118">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="68f25-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="68f25-119">Panoramica degli attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68f25-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="68f25-120">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="68f25-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
