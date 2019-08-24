---
title: 'Procedura: Aggiungere i controlli ActiveX a Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 8c4c6c3f96c49401b032e360314794cc800c0551
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987064"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="0997c-102">Procedura: Aggiungere i controlli ActiveX a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0997c-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="0997c-103">Sebbene il Progettazione Windows Form in Visual Studio sia ottimizzato per ospitare controlli Windows Forms, è anche possibile inserire controlli ActiveX in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0997c-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="0997c-104">Esistono limitazioni delle prestazioni per Windows Forms quando vengono aggiunti i controlli ActiveX.</span><span class="sxs-lookup"><span data-stu-id="0997c-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="0997c-105">Prima di aggiungere i controlli ActiveX al form, è necessario aggiungerli alla casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0997c-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="0997c-106">Per ulteriori informazioni, vedere [componenti com, finestra di dialogo Personalizza casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0997c-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="0997c-107">Aggiungere un controllo ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="0997c-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="0997c-108">Per aggiungere un controllo ActiveX a Windows Form, fare doppio clic sul controllo nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0997c-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="0997c-109">Visual Studio aggiunge tutti i riferimenti al controllo nel progetto.</span><span class="sxs-lookup"><span data-stu-id="0997c-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="0997c-110">Per ulteriori informazioni sugli aspetti da tenere presenti quando si utilizzano i controlli ActiveX in Windows Forms, vedere [considerazioni sull'hosting di un controllo ActiveX in un Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="0997c-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0997c-111">L'utilità di importazione di controlli ActiveX Windows Forms (AxImp. exe) crea argomenti di tipo diverso rispetto al previsto durante l'importazione di librerie di collegamento dinamico ActiveX.</span><span class="sxs-lookup"><span data-stu-id="0997c-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="0997c-112">Gli argomenti creati da AxImp. exe sono simili ai seguenti: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` è previsto.</span><span class="sxs-lookup"><span data-stu-id="0997c-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="0997c-113">Tenere presente che questa irregolarità non impedisce il corretto funzionamento del codice.</span><span class="sxs-lookup"><span data-stu-id="0997c-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="0997c-114">Per informazioni dettagliate, vedere [Windows Forms l'utilità di importazione del controllo ActiveX (Aximp. exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="0997c-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0997c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0997c-115">See also</span></span>

- [<span data-ttu-id="0997c-116">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="0997c-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="0997c-117">[Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0997c-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="0997c-118">Procedura: Aggiungere controlli a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0997c-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="0997c-119">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="0997c-119">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="0997c-120">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0997c-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="0997c-121">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="0997c-121">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
