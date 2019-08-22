---
title: 'Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666173"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="cb1ca-102">Procedura: Copiare e incollare un controllo ElementHost</span><span class="sxs-lookup"><span data-stu-id="cb1ca-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="cb1ca-103">Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="cb1ca-104">In Visual Studio aggiungere un nuovo WPF <xref:System.Windows.Controls.UserControl> a un progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="cb1ca-105">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="cb1ca-106">Per altre informazioni, vedere [Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Forms in fase](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="cb1ca-107">Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> di `UserControl1` su **200**.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="cb1ca-108">Impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà su **blu**.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="cb1ca-109">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-109">Build the project.</span></span>

5. <span data-ttu-id="cb1ca-110">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="cb1ca-111">Dalla **casella degli strumenti**trascinare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="cb1ca-112">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="cb1ca-113">Con `elementHost1` selezionata, premere **CTRL**+**C** per copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="cb1ca-114">Premere **CTRL**+**V** per incollare il controllo copiato nel form.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="cb1ca-115">Nel form <xref:System.Windows.Forms.Integration.ElementHost> viene creato `elementHost2` un nuovo controllo denominato.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb1ca-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb1ca-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="cb1ca-117">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cb1ca-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="cb1ca-118">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="cb1ca-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="cb1ca-119">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb1ca-119">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
