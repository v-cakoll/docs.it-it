---
title: 'Procedura: Aggiungere i controlli ActiveX a Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011154"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="f016d-102">Procedura: Aggiungere i controlli ActiveX a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f016d-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="f016d-103">Mentre è con ottimizzazione per la finestra di progettazione Windows Form per ospitare i controlli Windows Form, è anche possibile inserire controlli ActiveX in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f016d-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f016d-104">Esistono limitazioni delle prestazioni per Windows Form quando i controlli ActiveX a essi aggiunti.</span><span class="sxs-lookup"><span data-stu-id="f016d-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="f016d-105">Prima di aggiungere i controlli ActiveX al form, è necessario aggiungerli nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f016d-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="f016d-106">Per altre informazioni, vedere [componenti COM, finestra di dialogo Personalizza casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f016d-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f016d-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f016d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f016d-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f016d-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f016d-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f016d-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="f016d-110">Per aggiungere un controllo ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="f016d-110">To add an ActiveX control to your Windows Form</span></span>  
  
- <span data-ttu-id="f016d-111">Fare doppio clic sul controllo della casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f016d-111">Double-click the control on the Toolbox.</span></span>  
  
     <span data-ttu-id="f016d-112">Visual Studio aggiunge tutti i riferimenti al controllo del progetto.</span><span class="sxs-lookup"><span data-stu-id="f016d-112">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="f016d-113">Per altre informazioni sugli aspetti da tenere presenti quando si usano controlli ActiveX in Windows Form, vedere [considerazioni sull'inserimento di controlli ActiveX in un Form Windows](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="f016d-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f016d-114">Il Windows Form Control Importer di ActiveX (AxImp.exe) crea argomenti dell'evento di tipo diverso da quanto previsto durante l'importazione di librerie a collegamento dinamico ActiveX.</span><span class="sxs-lookup"><span data-stu-id="f016d-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="f016d-115">Gli argomenti creati da AxImp.exe sono simili al seguente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` è previsto.</span><span class="sxs-lookup"><span data-stu-id="f016d-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="f016d-116">Tenere presente che questo irregolarità impedisce al codice funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="f016d-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="f016d-117">Per informazioni dettagliate, vedere [Windows Forms Control Importer di ActiveX (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="f016d-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f016d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f016d-118">See also</span></span>

- [<span data-ttu-id="f016d-119">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="f016d-119">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="f016d-120">[Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f016d-120">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="f016d-121">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="f016d-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="f016d-122">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f016d-122">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="f016d-123">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="f016d-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f016d-124">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f016d-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f016d-125">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="f016d-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
