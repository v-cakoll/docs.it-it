---
title: 'Procedura: ridimensionare Windows Form'
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
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc2e9f81094d16030dbe4595a8132569edab782a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="a8c8a-102">Procedura: ridimensionare Windows Form</span><span class="sxs-lookup"><span data-stu-id="a8c8a-102">How to: Resize Windows Forms</span></span>
<span data-ttu-id="a8c8a-103">È possibile specificare le dimensioni del Windows Form in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-103">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="a8c8a-104">È possibile modificare sia l'altezza che la larghezza del form a livello di codice impostando un nuovo valore per la proprietà <xref:System.Windows.Forms.Form.Size%2A> o modificare le singole proprietà <xref:System.Windows.Forms.Control.Height%2A> o <xref:System.Windows.Forms.Control.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-104">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="a8c8a-105">Se si usa [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], le dimensioni possono essere modificate usando Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-105">If you are using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="a8c8a-106">Vedere anche [procedura: ridimensionare Windows Form usando la finestra di progettazione](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="a8c8a-106">Also see [How to: Resize Windows Forms Using the Designer](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).</span></span>  
  
### <a name="to-resize-a-form-programmatically"></a><span data-ttu-id="a8c8a-107">Per ridimensionare un form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a8c8a-107">To resize a form programmatically</span></span>  
  
-   <span data-ttu-id="a8c8a-108">Definire le dimensioni di un form in fase di esecuzione impostando la proprietà <xref:System.Windows.Forms.Form.Size%2A> del form.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-108">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>  
  
     <span data-ttu-id="a8c8a-109">Nell'esempio di codice riportato di seguito le dimensioni del form sono impostate su 100 × 100 pixel.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-109">The following code example shows the form size set to 100 × 100 pixels.</span></span>  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a><span data-ttu-id="a8c8a-110">Per modificare larghezza e altezza di un form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a8c8a-110">To change form width and height programmatically</span></span>  
  
-   <span data-ttu-id="a8c8a-111">Una volta definita la proprietà <xref:System.Windows.Forms.Form.Size%2A>, è possibile modificare l'altezza o la larghezza del form usando la proprietà <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-111">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="a8c8a-112">Nell'esempio di codice riportato di seguito viene illustrato come impostare la larghezza del form su 300 pixel dal bordo sinistro del form, mentre l'altezza rimane costante.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-112">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     <span data-ttu-id="a8c8a-113">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a8c8a-113">-or-</span></span>  
  
     <span data-ttu-id="a8c8a-114">Modificare la proprietà <xref:System.Drawing.Size.Width%2A> o la proprietà <xref:System.Drawing.Size.Height%2A> impostando la proprietà <xref:System.Windows.Forms.Form.Size%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-114">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>  
  
     <span data-ttu-id="a8c8a-115">Tuttavia, come illustrato nell'esempio di codice riportato di seguito, questo approccio risulta più complesso rispetto alla semplice impostazione delle proprietà <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-115">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a><span data-ttu-id="a8c8a-116">Per modificare le dimensioni del form in modo incrementale a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a8c8a-116">To change form size by increments programmatically</span></span>  
  
-   <span data-ttu-id="a8c8a-117">Per incrementare le dimensioni del form, impostare le proprietà <xref:System.Drawing.Size.Width%2A> o <xref:System.Drawing.Size.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-117">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="a8c8a-118">Nell'esempio di codice riportato di seguito la larghezza del form viene aumentata di 200 pixel rispetto all'impostazione corrente.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-118">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="a8c8a-119">Usare sempre la proprietà <xref:System.Drawing.Size.Height%2A> o la proprietà <xref:System.Drawing.Size.Width%2A> per modificare le dimensioni di un form, a meno che le dimensioni di altezza e larghezza non vengano impostate contemporaneamente mediante la proprietà <xref:System.Windows.Forms.Form.Size%2A> in una nuova struttura <xref:System.Drawing.Size>.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-119">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="a8c8a-120">La proprietà <xref:System.Windows.Forms.Form.Size%2A> restituisce una struttura <xref:System.Drawing.Size>, che è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-120">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="a8c8a-121">Non è possibile assegnare un nuovo valore alla proprietà di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-121">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="a8c8a-122">Di conseguenza, l'esempio di codice riportato di seguito non verrà compilato.</span><span class="sxs-lookup"><span data-stu-id="a8c8a-122">Therefore, the following code example will not compile.</span></span>  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a8c8a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8c8a-123">See Also</span></span>  
 [<span data-ttu-id="a8c8a-124">Guida introduttiva a Windows Form</span><span class="sxs-lookup"><span data-stu-id="a8c8a-124">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="a8c8a-125">Miglioramento delle applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="a8c8a-125">Enhancing Windows Forms Applications</span></span>](../../../docs/framework/winforms/advanced/index.md)
