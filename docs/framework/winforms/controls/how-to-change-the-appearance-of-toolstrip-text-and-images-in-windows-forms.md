---
title: "Procedura: modificare l'aspetto del testo e delle immagini di ToolStrip"
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
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746603"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="bbfa8-102">Procedura: Modificare l'aspetto del testo e delle immagini di una descrizione comandi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="bbfa8-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="bbfa8-103">È possibile controllare se le immagini e il testo vengono visualizzati in una <xref:System.Windows.Forms.ToolStripItem> e come sono allineati l'uno rispetto all'altro e la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="bbfa8-104">Per definire ciò che viene visualizzato in un oggetto ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="bbfa8-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="bbfa8-105">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="bbfa8-106">Le possibilità sono `Image`, `ImageAndText`, `None`e `Text`.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="bbfa8-107">Il valore predefinito è `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="bbfa8-108">Per allineare il testo in un oggetto ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="bbfa8-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="bbfa8-109">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="bbfa8-110">Le possibilità sono qualsiasi combinazione di Top, Middle e Bottom con Left, Center e Right.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="bbfa8-111">Il valore predefinito è `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="bbfa8-112">Per allineare un'immagine in un oggetto ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="bbfa8-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="bbfa8-113">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="bbfa8-114">Le possibilità sono qualsiasi combinazione di Top, Middle e Bottom con Left, Center e Right.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="bbfa8-115">Il valore predefinito è `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="bbfa8-116">Per definire la modalità di visualizzazione delle immagini e del testo di ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="bbfa8-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="bbfa8-117">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="bbfa8-118">I valori possibili sono `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` e `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="bbfa8-119">Il valore predefinito è `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="bbfa8-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bbfa8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfa8-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="bbfa8-121">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bbfa8-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="bbfa8-122">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bbfa8-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="bbfa8-123">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bbfa8-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
