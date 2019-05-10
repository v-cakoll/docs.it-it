---
title: 'Procedura: Aggiungere i controlli ActiveX a Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210383"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="f27ea-102">Procedura: Aggiungere i controlli ActiveX a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f27ea-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="f27ea-103">Mentre Progettazione Windows Form in Visual Studio è ottimizzato per ospitare i controlli Windows Form, è anche possibile inserire controlli ActiveX in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f27ea-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="f27ea-104">Esistono limitazioni delle prestazioni per Windows Form quando i controlli ActiveX a essi aggiunti.</span><span class="sxs-lookup"><span data-stu-id="f27ea-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="f27ea-105">Prima di aggiungere i controlli ActiveX al form, è necessario aggiungerli nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f27ea-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="f27ea-106">Per altre informazioni, vedere [componenti COM, finestra di dialogo Personalizza casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f27ea-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="f27ea-107">Aggiungere un controllo ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27ea-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="f27ea-108">Per aggiungere un controllo ActiveX a Windows Form, fare doppio clic sul controllo della casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f27ea-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="f27ea-109">Visual Studio aggiunge tutti i riferimenti al controllo del progetto.</span><span class="sxs-lookup"><span data-stu-id="f27ea-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="f27ea-110">Per altre informazioni sugli aspetti da tenere presenti quando si usano controlli ActiveX in Windows Form, vedere [considerazioni sull'inserimento di controlli ActiveX in un Form Windows](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="f27ea-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f27ea-111">Il Windows Form Control Importer di ActiveX (AxImp.exe) crea argomenti dell'evento di tipo diverso da quanto previsto durante l'importazione di librerie a collegamento dinamico ActiveX.</span><span class="sxs-lookup"><span data-stu-id="f27ea-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="f27ea-112">Gli argomenti creati da AxImp.exe sono simili al seguente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` è previsto.</span><span class="sxs-lookup"><span data-stu-id="f27ea-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="f27ea-113">Tenere presente che questo irregolarità impedisce al codice funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="f27ea-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="f27ea-114">Per informazioni dettagliate, vedere [Windows Forms Control Importer di ActiveX (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="f27ea-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f27ea-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f27ea-115">See also</span></span>

- [<span data-ttu-id="f27ea-116">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27ea-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="f27ea-117">[Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f27ea-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="f27ea-118">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27ea-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="f27ea-119">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27ea-119">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="f27ea-120">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="f27ea-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f27ea-121">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27ea-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f27ea-122">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="f27ea-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
