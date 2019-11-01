---
title: 'Procedura: copiare e incollare un controllo ElementHost in fase di progettazione'
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
ms.openlocfilehash: 3d1887eb1161f714962c2c26d6fe618749b26c0f
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197474"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="89867-102">Procedura: copiare e incollare un controllo ElementHost</span><span class="sxs-lookup"><span data-stu-id="89867-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="89867-103">Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89867-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="89867-104">In Visual Studio aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF a un progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="89867-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="89867-105">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="89867-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="89867-106">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Forms in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="89867-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="89867-107">Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> di `UserControl1` su **200**.</span><span class="sxs-lookup"><span data-stu-id="89867-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="89867-108">Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su **blu**.</span><span class="sxs-lookup"><span data-stu-id="89867-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="89867-109">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="89867-109">Build the project.</span></span>

5. <span data-ttu-id="89867-110">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="89867-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="89867-111">Dalla **casella degli strumenti**trascinare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="89867-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="89867-112">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="89867-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="89867-113">Con `elementHost1` selezionato, premere **Ctrl**+**C** per copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="89867-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="89867-114">Premere **Ctrl**+**V** per incollare il controllo copiato nel form.</span><span class="sxs-lookup"><span data-stu-id="89867-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="89867-115">Nel form viene creato un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="89867-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="89867-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89867-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="89867-117">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="89867-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="89867-118">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="89867-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="89867-119">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89867-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
