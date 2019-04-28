---
title: "Procedura: Modificare l'aspetto del testo e delle immagini ToolStrip in Windows Forms"
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
ms.openlocfilehash: 5c326c8f6a56c934d317305f85f4c88e95e75f8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781264"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="5da51-102">Procedura: Modificare l'aspetto del testo e delle immagini ToolStrip in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5da51-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="5da51-103">È possibile controllare se le immagini e testo vengono visualizzate in una <xref:System.Windows.Forms.ToolStripItem> e come siano allineati uno rispetto a altro e <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="5da51-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="5da51-104">Per definire cosa è visualizzato su un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5da51-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="5da51-105">Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="5da51-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="5da51-106">I valori possibili sono `Image`, `ImageAndText`, `None`, e `Text`.</span><span class="sxs-lookup"><span data-stu-id="5da51-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="5da51-107">Il valore predefinito è `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="5da51-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="5da51-108">Per allineare il testo su un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5da51-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="5da51-109">Impostare il <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="5da51-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="5da51-110">I valori possibili sono qualsiasi combinazione di alto, medio e basso a sinistra, centro e a destra.</span><span class="sxs-lookup"><span data-stu-id="5da51-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="5da51-111">Il valore predefinito è `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="5da51-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="5da51-112">Per allineare un'immagine in ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5da51-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="5da51-113">Impostare il <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="5da51-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="5da51-114">I valori possibili sono qualsiasi combinazione di alto, medio e basso a sinistra, centro e a destra.</span><span class="sxs-lookup"><span data-stu-id="5da51-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="5da51-115">Il valore predefinito è `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="5da51-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="5da51-116">Per definire la modalità di visualizzazione di immagini e testo ToolStripItem mettendone in relazione</span><span class="sxs-lookup"><span data-stu-id="5da51-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="5da51-117">Impostare il <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="5da51-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="5da51-118">I valori possibili sono `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, e `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="5da51-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="5da51-119">Il valore predefinito è `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="5da51-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5da51-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5da51-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="5da51-121">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5da51-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="5da51-122">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5da51-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="5da51-123">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5da51-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
