---
title: "Procedura: modificare l'aspetto del testo e delle immagini di una descrizione comandi in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: d3f53291e24d6a57e798725b716a7fd56eb661b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530530"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="516f6-102">Procedura: modificare l'aspetto del testo e delle immagini di una descrizione comandi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="516f6-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="516f6-103">È possibile controllare se vengono visualizzate testo e immagini in un <xref:System.Windows.Forms.ToolStripItem> e la modalità di allineamento uno rispetto a altro e <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="516f6-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="516f6-104">Per definire gli elementi visualizzati in un controllo ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="516f6-104">To define what is displayed on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="516f6-105">Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="516f6-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="516f6-106">I valori possibili sono `Image`, `ImageAndText`, `None`, e `Text`.</span><span class="sxs-lookup"><span data-stu-id="516f6-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="516f6-107">Il valore predefinito è `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="516f6-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="516f6-108">Per allineare il testo in un controllo ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="516f6-108">To align text on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="516f6-109">Impostare il <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="516f6-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="516f6-110">I valori possibili sono qualsiasi combinazione di superiore, centrale e inferiore con left, center e right.</span><span class="sxs-lookup"><span data-stu-id="516f6-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="516f6-111">Il valore predefinito è `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="516f6-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="516f6-112">Per allineare un'immagine in un controllo ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="516f6-112">To align an image on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="516f6-113">Impostare il <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="516f6-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="516f6-114">I valori possibili sono qualsiasi combinazione di superiore, centrale e inferiore con left, center e right.</span><span class="sxs-lookup"><span data-stu-id="516f6-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="516f6-115">Il valore predefinito è `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="516f6-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="516f6-116">Per definire la modalità di visualizzazione di immagini e testo ToolStripItem reciprocamente</span><span class="sxs-lookup"><span data-stu-id="516f6-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
-   <span data-ttu-id="516f6-117">Impostare il <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="516f6-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="516f6-118">I valori possibili sono `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, e `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="516f6-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="516f6-119">Il valore predefinito è `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="516f6-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="516f6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="516f6-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="516f6-121">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="516f6-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="516f6-122">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="516f6-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="516f6-123">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="516f6-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
