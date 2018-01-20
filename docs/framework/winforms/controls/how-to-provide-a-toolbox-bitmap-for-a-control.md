---
title: 'Procedura: specificare una bitmap nella casella degli strumenti per un controllo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 446e0f830e916e7f4118a7374c66f238a60fda02
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="6cbac-102">Procedura: specificare una bitmap nella casella degli strumenti per un controllo</span><span class="sxs-lookup"><span data-stu-id="6cbac-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="6cbac-103">Se si desidera disporre è visualizzata un'icona speciale per il controllo di **della casella degli strumenti**, è possibile specificare una particolare immagine utilizzando il <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6cbac-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="6cbac-104">Questa classe è un *attributo*, un tipo speciale di classe che è possibile allegare ad altre classi.</span><span class="sxs-lookup"><span data-stu-id="6cbac-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="6cbac-105">Per altre informazioni sugli attributi, vedere [NOT IN BUILD: Panoramica sugli attributi in Visual Basic](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f) per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] e [Attributi](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) per [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cbac-105">For more information about attributes, see [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f) for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] and [Attributes](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
 <span data-ttu-id="6cbac-106">Utilizzo di <xref:System.Drawing.ToolboxBitmapAttribute>, è possibile specificare una stringa che indica il percorso e il nome di una bitmap di 16x16 pixel.</span><span class="sxs-lookup"><span data-stu-id="6cbac-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="6cbac-107">Questa bitmap viene quindi visualizzata accanto al controllo quando è aggiunta alla **Casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="6cbac-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="6cbac-108">È inoltre possibile specificare un <xref:System.Type>, nel qual caso la bitmap associata a tale tipo viene caricata.</span><span class="sxs-lookup"><span data-stu-id="6cbac-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="6cbac-109">Se si specificano sia un <xref:System.Type> e una stringa, il controllo ricerca per una risorsa immagine con il nome specificato dal parametro di stringa dell'assembly contenente il tipo specificato per il <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="6cbac-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="6cbac-110">Per specificare una bitmap della casella degli strumenti per il controllo</span><span class="sxs-lookup"><span data-stu-id="6cbac-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="6cbac-111">Aggiungere il <xref:System.Drawing.ToolboxBitmapAttribute> alla dichiarazione di classe del controllo prima di `Class` parola chiave per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]e sopra la dichiarazione di classe per [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cbac-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], and above the class declaration for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
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
  
2.  <span data-ttu-id="6cbac-112">Ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="6cbac-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6cbac-113">La bitmap non viene visualizzata nella casella degli strumenti per i controlli e i componenti generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6cbac-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="6cbac-114">Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="6cbac-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="6cbac-115">Per altre informazioni, vedere [Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="6cbac-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cbac-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cbac-116">See Also</span></span>  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [<span data-ttu-id="6cbac-117">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6cbac-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="6cbac-118">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6cbac-118">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="6cbac-119">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cbac-119">Attributes (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="6cbac-120">Attributi</span><span class="sxs-lookup"><span data-stu-id="6cbac-120">Attributes</span></span>](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
