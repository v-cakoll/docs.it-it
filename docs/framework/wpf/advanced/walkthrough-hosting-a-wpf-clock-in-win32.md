---
title: 'Procedura dettagliata: hosting di un oggetto Clock WPF in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 58e4b1dd311ccd6e1bbab79f4c4dda2207f96eaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549698"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="0c382-102">Procedura dettagliata: hosting di un oggetto Clock WPF in Win32</span><span class="sxs-lookup"><span data-stu-id="0c382-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="0c382-103">Per inserire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] le applicazioni utilizzano <xref:System.Windows.Interop.HwndSource>, che fornisce HWND che contiene il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.</span><span class="sxs-lookup"><span data-stu-id="0c382-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="0c382-104">È innanzitutto necessario creare il <xref:System.Windows.Interop.HwndSource>, parametri simili a CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="0c382-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="0c382-105">Quindi, viene comunicato il <xref:System.Windows.Interop.HwndSource> sul [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto si desidera inserire.</span><span class="sxs-lookup"><span data-stu-id="0c382-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="0c382-106">Infine, si HWND fuori il <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="0c382-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="0c382-107">Questa procedura dettagliata viene illustrato come creare un misto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applicazione che implementa nuovamente il sistema operativo **proprietà data e ora** finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0c382-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c382-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0c382-108">Prerequisites</span></span>  
 <span data-ttu-id="0c382-109">Vedere [interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="0c382-109">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="0c382-110">Utilizzo dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="0c382-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="0c382-111">Questa esercitazione si concentra sui passaggi importanti per la produzione di un'applicazione di interoperatività.</span><span class="sxs-lookup"><span data-stu-id="0c382-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="0c382-112">L'esercitazione è supportata da un esempio, [Win32 Clock interoperabilità Sample](http://go.microsoft.com/fwlink/?LinkID=160051), ma che riflette il prodotto finale.</span><span class="sxs-lookup"><span data-stu-id="0c382-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="0c382-113">In questa esercitazione sono descritti i passaggi come se partire da un oggetto esistente [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto, ad esempio un progetto esistente e si stesse aggiungendo ospitato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c382-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="0c382-114">È possibile confrontare il prodotto finale con [Win32 Clock interoperabilità Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="0c382-114">You can compare your end product with [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="0c382-115">Procedura dettagliata di Windows Presentation Framework in Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="0c382-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="0c382-116">Il grafico seguente illustra il prodotto finale previsto di questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="0c382-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="0c382-117">![Finestra di dialogo Proprietà data e ora](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="0c382-117">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="0c382-118">È possibile ricreare questa finestra di dialogo mediante la creazione di C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] nel progetto [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e l'utilizzo dell'editor finestre per creare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c382-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="0c382-119">![Finestra di dialogo Proprietà data e ora](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="0c382-119">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="0c382-120">(Non è necessario utilizzare [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] utilizzare <xref:System.Windows.Interop.HwndSource>, e non è necessario utilizzare C++ per scrivere [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programmi, ma questo è un modo tipico a tale scopo e si presta per una spiegazione di un'esercitazione).</span><span class="sxs-lookup"><span data-stu-id="0c382-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="0c382-121">È necessario eseguire cinque passaggi particolare per inserire un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock nella finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="0c382-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="0c382-122">Abilitare il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] chiamata di codice gestito (**/clr**) modificando le impostazioni di progetto in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c382-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c382-123">Creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> in una DLL separata.</span><span class="sxs-lookup"><span data-stu-id="0c382-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="0c382-124">PUT che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> all'interno di un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="0c382-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="0c382-125">Ottenere un HWND che <xref:System.Windows.Controls.Page> utilizzando il <xref:System.Windows.Interop.HwndSource.Handle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c382-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="0c382-126">Utilizzare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] decidere dove posizionare HWND all'interno di dimensioni maggiori [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applicazione</span><span class="sxs-lookup"><span data-stu-id="0c382-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="0c382-127">/clr</span><span class="sxs-lookup"><span data-stu-id="0c382-127">/clr</span></span>  
 <span data-ttu-id="0c382-128">Il primo passaggio consiste nel disattivare questa non gestita [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] in un progetto in è possibile chiamare codice gestito.</span><span class="sxs-lookup"><span data-stu-id="0c382-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="0c382-129">Utilizzare l'opzione del compilatore /clr, che consente di collegare le DLL necessarie che si desidera utilizzare e modificare il metodo principale per l'utilizzo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c382-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="0c382-130">Per consentire l'utilizzo del codice gestito all'interno del progetto C++: destro del mouse sul progetto win32clock e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0c382-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="0c382-131">Nel **generale** (impostazione predefinita), pagina delle proprietà modificare il supporto Common Language Runtime per `/clr`.</span><span class="sxs-lookup"><span data-stu-id="0c382-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="0c382-132">Successivamente, aggiungere i riferimenti alle DLL necessaria per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework, System.dll, WindowsBase, UIAutomationProvider.dll e UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="0c382-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="0c382-133">(le istruzioni seguenti presuppongono che il sistema operativo sia installato nell'unità C:).</span><span class="sxs-lookup"><span data-stu-id="0c382-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="0c382-134">Fare clic sul progetto win32clock e selezionare **riferimenti...** e nella finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="0c382-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="0c382-135">Fare clic sul progetto win32clock e selezionare **riferimenti...** .</span><span class="sxs-lookup"><span data-stu-id="0c382-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="0c382-136">Fare clic su **Aggiungi nuovo riferimento**, fare clic sulla scheda Sfoglia, immettere C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0c382-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="0c382-137">Ripetere l'operazione per PresentationFramework.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="0c382-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="0c382-138">Ripetere l'operazione per WindowsBase.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="0c382-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="0c382-139">Ripetere l'operazione per UIAutomationTypes.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="0c382-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="0c382-140">Ripetere l'operazione per UIAutomationProvider.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="0c382-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="0c382-141">Fare clic su **Aggiungi nuovo riferimento**, selezionare System.dll e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c382-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="0c382-142">Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0c382-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="0c382-143">Aggiungere infine il `STAThreadAttribute` per il `_tWinMain` metodo per l'utilizzo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0c382-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="0c382-144">Questo attributo indica il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] che quando inizializza [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], deve utilizzare un modello di apartment a thread singolo (STA), che è necessario per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0c382-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="0c382-145">Creare una pagina di Windows Presentation Framework</span><span class="sxs-lookup"><span data-stu-id="0c382-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="0c382-146">Successivamente, si crea una DLL che definisce un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="0c382-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="0c382-147">È spesso più semplice creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> come applicazione autonoma e scrittura e debug di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte in questo modo.</span><span class="sxs-lookup"><span data-stu-id="0c382-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="0c382-148">Al termine, è possibile convertire in una DLL progetto facendo clic con il progetto, fare clic sul **proprietà**, passare all'applicazione e la modifica tipo di Output alla libreria di classi di Windows.</span><span class="sxs-lookup"><span data-stu-id="0c382-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="0c382-149">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto dll può quindi essere combinato con il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] pulsante destro del mouse sulla soluzione e seleziona di progetto (una soluzione che contiene due progetti) **Add\Existing progetto**.</span><span class="sxs-lookup"><span data-stu-id="0c382-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="0c382-150">Utilizzare tale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll dal [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto, è necessario aggiungere un riferimento:</span><span class="sxs-lookup"><span data-stu-id="0c382-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="0c382-151">Fare clic sul progetto win32clock e selezionare **riferimenti...** .</span><span class="sxs-lookup"><span data-stu-id="0c382-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="0c382-152">Fare clic su **Aggiungi nuovo riferimento**.</span><span class="sxs-lookup"><span data-stu-id="0c382-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="0c382-153">Fare clic sulla scheda **Progetti**.  Selezionare WPFClock e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0c382-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="0c382-154">Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0c382-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="0c382-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="0c382-155">HwndSource</span></span>  
 <span data-ttu-id="0c382-156">Successivamente, si utilizza <xref:System.Windows.Interop.HwndSource> per rendere il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> aspetto di HWND.</span><span class="sxs-lookup"><span data-stu-id="0c382-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="0c382-157">Aggiungere questo blocco di codice a un file C++:</span><span class="sxs-lookup"><span data-stu-id="0c382-157">You add this block of code to a C++ file:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 <span data-ttu-id="0c382-158">Poiché si tratta di una parte estesa di codice possono essere necessarie alcune spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="0c382-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="0c382-159">La prima parte contiene varie clausole che evitano di specificare il nome completo di tutte le chiamate:</span><span class="sxs-lookup"><span data-stu-id="0c382-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="0c382-160">Quindi definita una funzione che crea il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il contenuto, inserisce un <xref:System.Windows.Interop.HwndSource> e restituisce l'HWND:</span><span class="sxs-lookup"><span data-stu-id="0c382-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="0c382-161">È innanzitutto necessario creare un <xref:System.Windows.Interop.HwndSource>, i cui parametri sono simili a CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="0c382-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="0c382-162">Quindi si crea la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classe contenuto chiamando il relativo costruttore:</span><span class="sxs-lookup"><span data-stu-id="0c382-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="0c382-163">È quindi connettere la pagina per il <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="0c382-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="0c382-164">Nella riga finale, viene restituito HWND per il <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="0c382-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="0c382-165">Posizionamento dell'oggetto HWND</span><span class="sxs-lookup"><span data-stu-id="0c382-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="0c382-166">Ora che si dispone di un HWND che contiene il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio, è necessario inserirlo che il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0c382-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="0c382-167">Se si conosce la posizione in cui inserire HWND, è sufficiente passare tale dimensioni e posizione per il `GetHwnd` funzione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0c382-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="0c382-168">Tuttavia, si è usato un file di risorse per definire la finestra di dialogo perciò non si conosce esattamente la posizione degli oggetti HWND.</span><span class="sxs-lookup"><span data-stu-id="0c382-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="0c382-169">È possibile utilizzare il [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor finestre per inserire un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] statico controllare dove l'orologio per passare ("inserimento clock qui") da utilizzare per posizionare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio.</span><span class="sxs-lookup"><span data-stu-id="0c382-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="0c382-170">Gestione di WM_INITDIALOG, utilizzare `GetDlgItem` per recuperare HWND per il segnaposto STATIC:</span><span class="sxs-lookup"><span data-stu-id="0c382-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="0c382-171">Vengono quindi calcolate le dimensioni e la posizione del segnaposto STATIC, è possibile inserire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in tale punto:</span><span class="sxs-lookup"><span data-stu-id="0c382-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="0c382-172">Rettangolo RECT;</span><span class="sxs-lookup"><span data-stu-id="0c382-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="0c382-173">Dopodiché si nasconde il segnaposto STATIC:</span><span class="sxs-lookup"><span data-stu-id="0c382-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="0c382-174">E creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in tale percorso:</span><span class="sxs-lookup"><span data-stu-id="0c382-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="0c382-175">Per rendere interessante esercitazione e realizzare un vero [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio, sarà necessario creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock a questo punto di controllo.</span><span class="sxs-lookup"><span data-stu-id="0c382-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="0c382-176">È possibile eseguire questa operazione principalmente nel markup, con solo alcuni gestori eventi in code-behind.</span><span class="sxs-lookup"><span data-stu-id="0c382-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="0c382-177">Poiché in questa esercitazione sull'interoperabilità e non alla progettazione dei controlli, il codice completo per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio viene fornito come un blocco di codice, senza istruzioni specifiche per la compilazione, né il significato di ogni parte.</span><span class="sxs-lookup"><span data-stu-id="0c382-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="0c382-178">Modificare questo codice per variare l'aspetto o le funzionalità del controllo.</span><span class="sxs-lookup"><span data-stu-id="0c382-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="0c382-179">Questo è il markup:</span><span class="sxs-lookup"><span data-stu-id="0c382-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="0c382-180">Questo è il code-behind associato:</span><span class="sxs-lookup"><span data-stu-id="0c382-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="0c382-181">Il risultato finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0c382-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="0c382-182">![Finestra di dialogo Proprietà data e ora](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="0c382-182">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="0c382-183">Per confrontare il risultato finale al codice che ha generato questo screenshot, vedere [Win32 Clock interoperabilità Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="0c382-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c382-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c382-184">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="0c382-185">Interoperatività di WPF e Win32</span><span class="sxs-lookup"><span data-stu-id="0c382-185">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [<span data-ttu-id="0c382-186">Esempio di interoperatività con l'orologio Win32</span><span class="sxs-lookup"><span data-stu-id="0c382-186">Win32 Clock Interoperation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160051)
