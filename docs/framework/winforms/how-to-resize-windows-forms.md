---
title: Ridimensiona form
description: Informazioni su come ridimensionare l'altezza e la larghezza del form impostando un nuovo valore per la proprietà Size oppure modificare singolarmente le proprietà Height o Width.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 0d6383e4d29d9407d3da97bf8b94761f06d99748
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903272"
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="38a23-103">Procedura: Ridimensionare Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38a23-103">How to: Resize Windows Forms</span></span>

<span data-ttu-id="38a23-104">È possibile specificare le dimensioni del Windows Form in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="38a23-104">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="38a23-105">È possibile modificare sia l'altezza che la larghezza del form a livello di codice impostando un nuovo valore per la proprietà <xref:System.Windows.Forms.Form.Size%2A> o modificare le singole proprietà <xref:System.Windows.Forms.Control.Height%2A> o <xref:System.Windows.Forms.Control.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="38a23-105">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="38a23-106">Se si usa Visual Studio, è possibile modificare le dimensioni usando il Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="38a23-106">If you're using Visual Studio, you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="38a23-107">Vedere anche [procedura: ridimensionare Windows Forms usando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="38a23-107">Also see [How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span></span>

## <a name="resize-a-form-programmatically"></a><span data-ttu-id="38a23-108">Ridimensionare un form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="38a23-108">Resize a form programmatically</span></span>

<span data-ttu-id="38a23-109">Definire le dimensioni di un form in fase di esecuzione impostando la proprietà <xref:System.Windows.Forms.Form.Size%2A> del form.</span><span class="sxs-lookup"><span data-stu-id="38a23-109">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>

<span data-ttu-id="38a23-110">Nell'esempio di codice riportato di seguito le dimensioni del form sono impostate su 100 × 100 pixel.</span><span class="sxs-lookup"><span data-stu-id="38a23-110">The following code example shows the form size set to 100 × 100 pixels.</span></span>

```vb
Form1.Size = New System.Drawing.Size(100, 100)
```

```csharp
Form1.Size = new System.Drawing.Size(100, 100);
```

```cpp
Form1->Size = System::Drawing::Size(100, 100);
```

## <a name="change-form-width-and-height-programmatically"></a><span data-ttu-id="38a23-111">Modificare la larghezza e l'altezza del modulo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="38a23-111">Change form width and height programmatically</span></span>

<span data-ttu-id="38a23-112">Una volta definita la proprietà <xref:System.Windows.Forms.Form.Size%2A>, è possibile modificare l'altezza o la larghezza del form usando la proprietà <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="38a23-112">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>

<span data-ttu-id="38a23-113">Nell'esempio di codice riportato di seguito viene illustrato come impostare la larghezza del form su 300 pixel dal bordo sinistro del form, mentre l'altezza rimane costante.</span><span class="sxs-lookup"><span data-stu-id="38a23-113">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>

```vb
Form1.Width = 300
```

```csharp
Form1.Width = 300;
```

```cpp
Form1->Width = 300;
```

<span data-ttu-id="38a23-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="38a23-114">-or-</span></span>

<span data-ttu-id="38a23-115">Modificare la proprietà <xref:System.Drawing.Size.Width%2A> o la proprietà <xref:System.Drawing.Size.Height%2A> impostando la proprietà <xref:System.Windows.Forms.Form.Size%2A>.</span><span class="sxs-lookup"><span data-stu-id="38a23-115">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>

<span data-ttu-id="38a23-116">Tuttavia, come illustrato nell'esempio di codice riportato di seguito, questo approccio risulta più complesso rispetto alla semplice impostazione delle proprietà <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="38a23-116">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>

```vb
Form1.Size = New Size(300, Form1.Size.Height)
```

```csharp
Form1.Size = new Size(300, Form1.Size.Height);
```

```cpp
Form1->Size = System::Drawing::Size(300, Form1->Size.Height);
```

## <a name="change-form-size-by-increments-programmatically"></a><span data-ttu-id="38a23-117">Modificare le dimensioni del modulo per incrementi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="38a23-117">Change form size by increments programmatically</span></span>

<span data-ttu-id="38a23-118">Per incrementare le dimensioni del form, impostare le proprietà <xref:System.Drawing.Size.Width%2A> o <xref:System.Drawing.Size.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="38a23-118">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>

<span data-ttu-id="38a23-119">Nell'esempio di codice riportato di seguito la larghezza del form viene aumentata di 200 pixel rispetto all'impostazione corrente.</span><span class="sxs-lookup"><span data-stu-id="38a23-119">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>

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
> <span data-ttu-id="38a23-120">Usare sempre la proprietà <xref:System.Drawing.Size.Height%2A> o la proprietà <xref:System.Drawing.Size.Width%2A> per modificare le dimensioni di un form, a meno che le dimensioni di altezza e larghezza non vengano impostate contemporaneamente mediante la proprietà <xref:System.Windows.Forms.Form.Size%2A> in una nuova struttura <xref:System.Drawing.Size>.</span><span class="sxs-lookup"><span data-stu-id="38a23-120">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="38a23-121">La proprietà <xref:System.Windows.Forms.Form.Size%2A> restituisce una struttura <xref:System.Drawing.Size>, che è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="38a23-121">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="38a23-122">Non è possibile assegnare un nuovo valore alla proprietà di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="38a23-122">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="38a23-123">Di conseguenza, l'esempio di codice riportato di seguito non verrà compilato.</span><span class="sxs-lookup"><span data-stu-id="38a23-123">Therefore, the following code example will not compile.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="38a23-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38a23-124">See also</span></span>

- [<span data-ttu-id="38a23-125">Introduzione con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38a23-125">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="38a23-126">Miglioramento delle applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="38a23-126">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
