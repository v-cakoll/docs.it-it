---
title: 'Procedura: Specificare una Bitmap nella casella degli strumenti per un controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 9072f96bd6e3485e759ed72819229b3f0c33d641
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715958"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="f6f32-102">Procedura: Specificare una Bitmap nella casella degli strumenti per un controllo</span><span class="sxs-lookup"><span data-stu-id="f6f32-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="f6f32-103">Se si desidera avere un'icona speciale per il controllo vengono visualizzati nei **casella degli strumenti**, è possibile specificare una particolare immagine usando il <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f6f32-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="f6f32-104">Questa classe è un *attributo*, un tipo speciale di classe che è possibile allegare ad altre classi.</span><span class="sxs-lookup"><span data-stu-id="f6f32-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="f6f32-105">Per altre informazioni sugli attributi, vedere [Cenni preliminari sugli attributi (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) per Visual Basic o [attributi (c#)](../../../csharp/programming-guide/concepts/attributes/index.md) per c#.</span><span class="sxs-lookup"><span data-stu-id="f6f32-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>  
  
 <span data-ttu-id="f6f32-106">Uso di <xref:System.Drawing.ToolboxBitmapAttribute>, è possibile specificare una stringa che indica il percorso e il nome di una bitmap di 16x16 pixel.</span><span class="sxs-lookup"><span data-stu-id="f6f32-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="f6f32-107">Questa bitmap viene quindi visualizzata accanto al controllo quando è aggiunta alla **Casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f6f32-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="f6f32-108">È inoltre possibile specificare un <xref:System.Type>, nel qual caso viene caricata la bitmap associata a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="f6f32-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="f6f32-109">Se si specificano sia un <xref:System.Type> e con una stringa, il controllo ricerca una risorsa immagine con il nome specificato dal parametro della stringa nell'assembly che contiene il tipo specificato da di <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="f6f32-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="f6f32-110">Per specificare una bitmap della casella degli strumenti per il controllo</span><span class="sxs-lookup"><span data-stu-id="f6f32-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="f6f32-111">Aggiungere il <xref:System.Drawing.ToolboxBitmapAttribute> alla dichiarazione di classe del controllo prima di `Class` (parola chiave) per visual Basic e sopra la dichiarazione di classe per Visual c#.</span><span class="sxs-lookup"><span data-stu-id="f6f32-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>  
  
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
  
2.  <span data-ttu-id="f6f32-112">Ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="f6f32-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6f32-113">La bitmap non viene visualizzata nella casella degli strumenti per i controlli e i componenti generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6f32-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="f6f32-114">Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f6f32-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="f6f32-115">Per altre informazioni, vedere [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="f6f32-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f32-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6f32-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="f6f32-117">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="f6f32-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="f6f32-118">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f6f32-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="f6f32-119">Panoramica degli attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f32-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="f6f32-120">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="f6f32-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
