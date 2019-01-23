---
title: 'Procedura: Creare testo di dimensioni variabili in un controllo ComboBox'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: 2a9f6e8a1c96c2a9bf9e56c1c6acefc4181a18dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526990"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="727f2-102">Procedura: Creare testo di dimensioni variabili in un controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="727f2-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="727f2-103">Questo esempio viene illustrato il disegno personalizzato di testo in un <xref:System.Windows.Forms.ComboBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="727f2-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="727f2-104">Quando un elemento soddisfa determinati criteri, viene creato un tipo di carattere più grande e colore rosso.</span><span class="sxs-lookup"><span data-stu-id="727f2-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="727f2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="727f2-105">Example</span></span>  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="727f2-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="727f2-106">Compiling the Code</span></span>  
 <span data-ttu-id="727f2-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="727f2-107">This example requires:</span></span>  
  
-   <span data-ttu-id="727f2-108">Un modulo di Windows.</span><span class="sxs-lookup"><span data-stu-id="727f2-108">A Windows form.</span></span>  
  
-   <span data-ttu-id="727f2-109">Oggetto <xref:System.Windows.Forms.ComboBox> controllo denominato `ListBox1` con tre elementi di <xref:System.Windows.Forms.ComboBox.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="727f2-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="727f2-110">In questo esempio, i tre elementi sono denominati `"One", Two", and Three"`.</span><span class="sxs-lookup"><span data-stu-id="727f2-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="727f2-111">Il <xref:System.Windows.Forms.ComboBox.DrawMode%2A> proprietà di `ComboBox1` deve essere impostata su <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span><span class="sxs-lookup"><span data-stu-id="727f2-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="727f2-112">Questa tecnica è applicabile anche al <xref:System.Windows.Forms.ListBox> controllo, è possibile sostituirlo con un <xref:System.Windows.Forms.ListBox> per il <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="727f2-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>  
  
-   <span data-ttu-id="727f2-113">Riferimenti agli spazi dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="727f2-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727f2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="727f2-114">See also</span></span>
- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [<span data-ttu-id="727f2-115">Controlli con supporto predefinito per il disegno da parte del proprietario</span><span class="sxs-lookup"><span data-stu-id="727f2-115">Controls with Built-In Owner-Drawing Support</span></span>](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="727f2-116">Controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="727f2-116">ListBox Control</span></span>](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)
- [<span data-ttu-id="727f2-117">Controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="727f2-117">ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)
