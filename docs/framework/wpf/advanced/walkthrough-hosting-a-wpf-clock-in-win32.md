---
title: 'Procedura dettagliata: hosting di un oggetto Clock WPF in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 8d1f376a2c5b3f31407af0100d9a4417f7cff34e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740247"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="f048b-102">Procedura dettagliata: hosting di un oggetto Clock WPF in Win32</span><span class="sxs-lookup"><span data-stu-id="f048b-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="f048b-103">Per inserire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno delle applicazioni Win32, utilizzare <xref:System.Windows.Interop.HwndSource>, che fornisce l'HWND che contiene il contenuto di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f048b-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="f048b-104">Innanzitutto si crea il <xref:System.Windows.Interop.HwndSource>, fornendo parametri simili a CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="f048b-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="f048b-105">Si dirà quindi al <xref:System.Windows.Interop.HwndSource> sul contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che si vuole al suo interno.</span><span class="sxs-lookup"><span data-stu-id="f048b-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="f048b-106">Infine, si ottiene il HWND dal <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="f048b-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="f048b-107">In questa procedura dettagliata viene illustrato come creare una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mista all'interno di un'applicazione Win32 che implementa nuovamente la finestra di dialogo **Proprietà data e ora** del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f048b-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f048b-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f048b-108">Prerequisites</span></span>

<span data-ttu-id="f048b-109">Vedere l' [interoperatività di WPF e Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="f048b-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="f048b-110">Come usare questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="f048b-110">How to Use This Tutorial</span></span>

<span data-ttu-id="f048b-111">Questa esercitazione si concentra sui passaggi importanti per la produzione di un'applicazione di interoperatività.</span><span class="sxs-lookup"><span data-stu-id="f048b-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="f048b-112">L'esercitazione è supportata da un esempio di [interoperatività con clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051), ma tale esempio riflette il prodotto finale.</span><span class="sxs-lookup"><span data-stu-id="f048b-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="f048b-113">Questa esercitazione illustra i passaggi come se si iniziasse con un progetto Win32 esistente, ad esempio un progetto preesistente e si stesse aggiungendo una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitata all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f048b-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="f048b-114">È possibile confrontare il prodotto finale con l' [esempio di interoperatività con clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="f048b-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="f048b-115">Procedura dettagliata di Windows Presentation Framework in Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="f048b-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="f048b-116">Il grafico seguente illustra il prodotto finale previsto di questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="f048b-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Screenshot che mostra la finestra di dialogo Proprietà data e ora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="f048b-118">Per ricreare questa finestra di dialogo è possibile C++ creare un progetto Win32 in Visual Studio e utilizzare l'editor finestre per creare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f048b-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Finestra di dialogo Proprietà data e ora ricreate](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="f048b-120">Non è necessario usare Visual Studio per usare <xref:System.Windows.Interop.HwndSource>e non è necessario usare C++ per scrivere programmi Win32, ma si tratta di un modo piuttosto comune per eseguire questa operazione e si presta bene a una spiegazione graduale dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f048b-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="f048b-121">Per inserire un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock nella finestra di dialogo, è necessario eseguire cinque passaggi specifici:</span><span class="sxs-lookup"><span data-stu-id="f048b-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="f048b-122">Abilitare il progetto Win32 per chiamare il codice gestito ( **/CLR**) modificando le impostazioni del progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f048b-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="f048b-123">Creare una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in una DLL separata.</span><span class="sxs-lookup"><span data-stu-id="f048b-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="f048b-124">Inserire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> all'interno di un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="f048b-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="f048b-125">Ottenere un HWND per tale <xref:System.Windows.Controls.Page> utilizzando la proprietà <xref:System.Windows.Interop.HwndSource.Handle%2A>.</span><span class="sxs-lookup"><span data-stu-id="f048b-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="f048b-126">Utilizzare Win32 per decidere dove posizionare il HWND all'interno dell'applicazione Win32 di dimensioni maggiori</span><span class="sxs-lookup"><span data-stu-id="f048b-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="f048b-127">/clr</span><span class="sxs-lookup"><span data-stu-id="f048b-127">/clr</span></span>

<span data-ttu-id="f048b-128">Il primo passaggio consiste nel trasformare questo progetto Win32 non gestito in uno in grado di chiamare codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f048b-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="f048b-129">Si usa l'opzione del compilatore/CLR, che consente di collegare le DLL necessarie da usare e di modificare il metodo Main per l'uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f048b-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="f048b-130">Per abilitare l'uso del codice gestito all'interno C++ del progetto: fare clic con il pulsante destro del mouse sul progetto win32clock e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f048b-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="f048b-131">Nella pagina delle proprietà **generale** (impostazione predefinita) modificare il supporto Common Language Runtime in `/clr`.</span><span class="sxs-lookup"><span data-stu-id="f048b-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="f048b-132">Aggiungere quindi i riferimenti alle DLL necessarie per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll e UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="f048b-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="f048b-133">(le istruzioni seguenti presuppongono che il sistema operativo sia installato nell'unità C:).</span><span class="sxs-lookup"><span data-stu-id="f048b-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="f048b-134">Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** e all'interno di tale finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="f048b-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="f048b-135">Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** .</span><span class="sxs-lookup"><span data-stu-id="f048b-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="f048b-136">Fare clic su **Aggiungi nuovo riferimento**, fare clic sulla scheda Sfoglia, immettere C:\program files\reference assemblies\microsoft\framework\v3.0\PresentationCore.dll e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f048b-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="f048b-137">Ripetere l'operazione per PresentationFramework.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="f048b-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="f048b-138">Ripetere l'operazione per WindowsBase.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="f048b-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="f048b-139">Ripetere l'operazione per UIAutomationTypes.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="f048b-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="f048b-140">Ripetere l'operazione per UIAutomationProvider.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="f048b-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="f048b-141">Fare clic su **Aggiungi nuovo riferimento**, selezionare System. dll e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f048b-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="f048b-142">Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.</span><span class="sxs-lookup"><span data-stu-id="f048b-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="f048b-143">Infine, aggiungere il `STAThreadAttribute` al metodo `_tWinMain` per l'utilizzo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f048b-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="f048b-144">Questo attributo indica al Common Language Runtime (CLR) che, quando inizializza Component Object Model (COM), deve usare un modello di Apartment a thread singolo (STA), che è necessario per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="f048b-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="f048b-145">Creare una pagina di Windows Presentation Framework</span><span class="sxs-lookup"><span data-stu-id="f048b-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="f048b-146">Successivamente, si crea una DLL che definisce una <xref:System.Windows.Controls.Page>di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f048b-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="f048b-147">Spesso è più semplice creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> come applicazione autonoma e scrivere ed eseguire il debug della parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in questo modo.</span><span class="sxs-lookup"><span data-stu-id="f048b-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="f048b-148">Al termine, il progetto può essere trasformato in una DLL facendo clic con il pulsante destro del mouse sul progetto, facendo clic su **Proprietà**, passando all'applicazione e modificando il tipo di output in libreria di classi di Windows.</span><span class="sxs-lookup"><span data-stu-id="f048b-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="f048b-149">Il progetto di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll può quindi essere combinato con il progetto Win32 (una soluzione che contiene due progetti): fare clic con il pulsante destro del mouse sulla soluzione e selezionare **progetto Add\Existing**.</span><span class="sxs-lookup"><span data-stu-id="f048b-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="f048b-150">Per utilizzare tale DLL [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dal progetto Win32, è necessario aggiungere un riferimento:</span><span class="sxs-lookup"><span data-stu-id="f048b-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="f048b-151">Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** .</span><span class="sxs-lookup"><span data-stu-id="f048b-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="f048b-152">Fare clic su **Aggiungi nuovo riferimento**.</span><span class="sxs-lookup"><span data-stu-id="f048b-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="f048b-153">Fare clic sulla scheda **progetti** . Selezionare WPFClock, quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f048b-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="f048b-154">Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.</span><span class="sxs-lookup"><span data-stu-id="f048b-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="f048b-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="f048b-155">HwndSource</span></span>

<span data-ttu-id="f048b-156">Usare quindi <xref:System.Windows.Interop.HwndSource> per rendere il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> simile a un HWND.</span><span class="sxs-lookup"><span data-stu-id="f048b-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="f048b-157">Aggiungere questo blocco di codice a un file C++:</span><span class="sxs-lookup"><span data-stu-id="f048b-157">You add this block of code to a C++ file:</span></span>

```cpp
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

 <span data-ttu-id="f048b-158">Poiché si tratta di una parte estesa di codice possono essere necessarie alcune spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="f048b-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="f048b-159">La prima parte contiene varie clausole che evitano di specificare il nome completo di tutte le chiamate:</span><span class="sxs-lookup"><span data-stu-id="f048b-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="f048b-160">Si definisce quindi una funzione che crea il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ne inserisce una <xref:System.Windows.Interop.HwndSource> e restituisce HWND:</span><span class="sxs-lookup"><span data-stu-id="f048b-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="f048b-161">Prima di tutto si crea un <xref:System.Windows.Interop.HwndSource>, i cui parametri sono simili a CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="f048b-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="f048b-162">Si crea quindi la classe di contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiamando il relativo costruttore:</span><span class="sxs-lookup"><span data-stu-id="f048b-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="f048b-163">Si connette quindi la pagina alla <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="f048b-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="f048b-164">Nella riga finale, restituire HWND per la <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="f048b-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="f048b-165">Posizionamento dell'oggetto HWND</span><span class="sxs-lookup"><span data-stu-id="f048b-165">Positioning the Hwnd</span></span>

<span data-ttu-id="f048b-166">Ora che è presente un HWND che contiene il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, è necessario inserire tale HWND nella finestra di dialogo Win32.</span><span class="sxs-lookup"><span data-stu-id="f048b-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="f048b-167">Se si conoscesse solo la posizione in cui inserire HWND, è sufficiente passare le dimensioni e la posizione alla funzione `GetHwnd` definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f048b-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="f048b-168">Tuttavia, si è usato un file di risorse per definire la finestra di dialogo perciò non si conosce esattamente la posizione degli oggetti HWND.</span><span class="sxs-lookup"><span data-stu-id="f048b-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="f048b-169">È possibile usare l'editor finestre di Visual Studio per inserire un controllo statico Win32 in cui si vuole che l'orologio venga usato ("Inserisci orologio") e lo usi per posizionare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock.</span><span class="sxs-lookup"><span data-stu-id="f048b-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="f048b-170">Quando si gestiscono WM_INITDIALOG, si utilizza `GetDlgItem` per recuperare HWND per il segnaposto STATIC:</span><span class="sxs-lookup"><span data-stu-id="f048b-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="f048b-171">Quindi si calcolano le dimensioni e la posizione del segnaposto statico, in modo che sia possibile inserire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in tale posizione:</span><span class="sxs-lookup"><span data-stu-id="f048b-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="f048b-172">Rettangolo RECT;</span><span class="sxs-lookup"><span data-stu-id="f048b-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="f048b-173">Dopodiché si nasconde il segnaposto STATIC:</span><span class="sxs-lookup"><span data-stu-id="f048b-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="f048b-174">E creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND clock in tale percorso:</span><span class="sxs-lookup"><span data-stu-id="f048b-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="f048b-175">Per rendere interessante l'esercitazione e per produrre un vero e proprio [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, è necessario creare un controllo del clock [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a questo punto.</span><span class="sxs-lookup"><span data-stu-id="f048b-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="f048b-176">È possibile eseguire questa operazione principalmente nel markup, con solo alcuni gestori eventi in code-behind.</span><span class="sxs-lookup"><span data-stu-id="f048b-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="f048b-177">Poiché questa esercitazione riguarda l'interoperatività e non la progettazione dei controlli, il codice completo per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock viene fornito qui come blocco di codice, senza istruzioni discrete per la compilazione o il significato di ogni parte.</span><span class="sxs-lookup"><span data-stu-id="f048b-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="f048b-178">Modificare questo codice per variare l'aspetto o le funzionalità del controllo.</span><span class="sxs-lookup"><span data-stu-id="f048b-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="f048b-179">Questo è il markup:</span><span class="sxs-lookup"><span data-stu-id="f048b-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="f048b-180">Questo è il code-behind associato:</span><span class="sxs-lookup"><span data-stu-id="f048b-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="f048b-181">Il risultato finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f048b-181">The final result looks like:</span></span>

![Finestra di dialogo Proprietà data e ora risultato finale](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="f048b-183">Per confrontare il risultato finale con il codice che ha prodotto questa schermata, vedere [esempio di interoperatività di Win32 Clock](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="f048b-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="f048b-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f048b-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="f048b-185">Interoperatività di WPF e Win32</span><span class="sxs-lookup"><span data-stu-id="f048b-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="f048b-186">Esempio di interoperatività con l'orologio Win32</span><span class="sxs-lookup"><span data-stu-id="f048b-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
