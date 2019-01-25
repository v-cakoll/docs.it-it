---
title: Hosting di contenuto Win32 in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: fa0457cd44304084355f3882d9fc5c82b29c4827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725468"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="1d656-102">Hosting di contenuto Win32 in WPF</span><span class="sxs-lookup"><span data-stu-id="1d656-102">Hosting Win32 Content in WPF</span></span>
## <a name="prerequisites"></a><span data-ttu-id="1d656-103">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1d656-103">Prerequisites</span></span>  
 <span data-ttu-id="1d656-104">Visualizzare [interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="1d656-104">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="1d656-105">Una procedura dettagliata di Win32 all'interno di Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="1d656-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>  
 <span data-ttu-id="1d656-106">Per riutilizzare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenuti all'interno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , le applicazioni utilizzano <xref:System.Windows.Interop.HwndHost>, che è un controllo che conferisce un aspetto, ad esempio hwnds di tipo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.</span><span class="sxs-lookup"><span data-stu-id="1d656-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>  <span data-ttu-id="1d656-107">Ad esempio <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> è semplice da utilizzare: derivano da <xref:System.Windows.Interop.HwndHost> e implementare `BuildWindowCore` e `DestroyWindowCore` metodi, quindi creare un'istanza di <xref:System.Windows.Interop.HwndHost> classe derivata e inserirlo all'interno di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d656-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  
  
 <span data-ttu-id="1d656-108">Se il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] per la logica è già incluso nel pacchetto come un controllo, è possibile che il `BuildWindowCore` implementazione è leggermente più di una chiamata a `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="1d656-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span>  <span data-ttu-id="1d656-109">Ad esempio, per creare un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo LISTBOX in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1d656-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>  
  
```  
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
    HWND handle = CreateWindowEx(0, L"LISTBOX",   
    L"this is a Win32 listbox",  
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY  
    | WS_VSCROLL | WS_BORDER,  
    0, 0, // x, y  
    30, 70, // height, width  
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd  
    0, // hmenu  
    0, // hinstance  
    0); // lparam  
  
    return HandleRef(this, IntPtr(handle));  
}  
  
virtual void DestroyWindowCore(HandleRef hwnd) override {  
    // HwndHost will dispose the hwnd for us  
}  
```  
  
 <span data-ttu-id="1d656-110">Si supponga, tuttavia il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] codice non sia completamente autonomo?</span><span class="sxs-lookup"><span data-stu-id="1d656-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="1d656-111">Se, pertanto, è possibile creare un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra di dialogo casella e incorporare il contenuto in una più grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d656-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="1d656-112">Nell'esempio viene illustrato in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] e [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], anche se è anche possibile eseguire questa operazione in una lingua diversa o nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1d656-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>  
  
 <span data-ttu-id="1d656-113">Iniziare con una semplice finestra di dialogo, viene compilato in un [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="1d656-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>  
  
 <span data-ttu-id="1d656-114">Successivamente, inserire la finestra di dialogo nel maggiore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione:</span><span class="sxs-lookup"><span data-stu-id="1d656-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>  
  
-   <span data-ttu-id="1d656-115">Compilare il [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] come gestito (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="1d656-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>  
  
-   <span data-ttu-id="1d656-116">Trasforma la finestra di dialogo in un controllo</span><span class="sxs-lookup"><span data-stu-id="1d656-116">Turn the dialog into a control</span></span>  
  
-   <span data-ttu-id="1d656-117">Definire la classe derivata di <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` e `DestroyWindowCore` metodi</span><span class="sxs-lookup"><span data-stu-id="1d656-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>  
  
-   <span data-ttu-id="1d656-118">Eseguire l'override `TranslateAccelerator` metodo per gestire le chiavi di finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="1d656-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>  
  
-   <span data-ttu-id="1d656-119">Eseguire l'override `TabInto` per supportare la tabulazione (metodo)</span><span class="sxs-lookup"><span data-stu-id="1d656-119">Override `TabInto` method to support tabbing</span></span>  
  
-   <span data-ttu-id="1d656-120">Eseguire l'override `OnMnemonic` per supportare i tasti di scelta (metodo)</span><span class="sxs-lookup"><span data-stu-id="1d656-120">Override `OnMnemonic` method to support mnemonics</span></span>  
  
-   <span data-ttu-id="1d656-121">Creare un'istanza di <xref:System.Windows.Interop.HwndHost> sottoclasse e inserirlo sotto il diritto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento</span><span class="sxs-lookup"><span data-stu-id="1d656-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>  
  
### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="1d656-122">Trasforma la finestra di dialogo in un controllo</span><span class="sxs-lookup"><span data-stu-id="1d656-122">Turn the Dialog into a Control</span></span>  
 <span data-ttu-id="1d656-123">È possibile attivare una finestra di dialogo in utilizzando gli stili WS_CHILD e DS_CONTROL HWND figlio.</span><span class="sxs-lookup"><span data-stu-id="1d656-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span>  <span data-ttu-id="1d656-124">Analizzare il file di risorse (RC) in cui è definita la finestra di dialogo e trovare l'inizio della definizione della finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="1d656-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 <span data-ttu-id="1d656-125">Modificare la seconda riga a:</span><span class="sxs-lookup"><span data-stu-id="1d656-125">Change the second line to:</span></span>  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 <span data-ttu-id="1d656-126">Questa azione non completamente comprimerlo in un controllo indipendente. è comunque necessario chiamare `IsDialogMessage()` in modo [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] determinati messaggi vengano elaborati, ma la modifica del controllo forniscono un modo semplice per inserire i controlli all'interno di un altro oggetto HWND.</span><span class="sxs-lookup"><span data-stu-id="1d656-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>  
  
## <a name="subclass-hwndhost"></a><span data-ttu-id="1d656-127">Sottoclasse HwndHost</span><span class="sxs-lookup"><span data-stu-id="1d656-127">Subclass HwndHost</span></span>  
 <span data-ttu-id="1d656-128">Importare gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d656-128">Import the following namespaces:</span></span>  
  
```  
namespace ManagedCpp  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Input;  
    using namespace System::Windows::Media;  
    using namespace System::Runtime::InteropServices;  
```  
  
 <span data-ttu-id="1d656-129">Quindi creare una classe derivata di <xref:System.Windows.Interop.HwndHost> ed eseguire l'override di `BuildWindowCore` e `DestroyWindowCore` metodi:</span><span class="sxs-lookup"><span data-stu-id="1d656-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>  
  
```  
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {  
    private:  
        HWND dialog;  
  
    protected:   
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
            InitializeGlobals();   
            dialog = CreateDialog(hInstance,   
                MAKEINTRESOURCE(IDD_DIALOG1),   
                (HWND) hwndParent.Handle.ToPointer(),  
                (DLGPROC) About);   
            return HandleRef(this, IntPtr(dialog));  
        }  
  
        virtual void DestroyWindowCore(HandleRef hwnd) override {  
            // hwnd will be disposed for us  
        }  
```  
  
 <span data-ttu-id="1d656-130">Questo caso si usa il `CreateDialog` per creare la finestra di dialogo che in realtà un controllo.</span><span class="sxs-lookup"><span data-stu-id="1d656-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span>  <span data-ttu-id="1d656-131">Poiché si tratta di uno dei primi metodi chiamati all'interno di [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], è inoltre necessario eseguire alcuni standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] inizializzazione richiamando una funzione che verrà definita in un secondo momento, chiamato `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="1d656-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>  
  
```  
bool initialized = false;  
    void InitializeGlobals() {  
        if (initialized) return;  
        initialized = true;  
  
        // TODO: Place code here.  
        MSG msg;  
        HACCEL hAccelTable;  
  
        // Initialize global strings  
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);  
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);  
        MyRegisterClass(hInstance);  
```  
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="1d656-132">Eseguire l'override del metodo TranslateAccelerator per gestire le chiavi di finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="1d656-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>  
 <span data-ttu-id="1d656-133">Se si esegue questo esempio a questo punto, si otterrebbe un controllo di finestra di dialogo che consente di visualizzare, ma sarebbe Ignora tutto della tastiera di elaborazione che consente di una finestra di dialogo una finestra di dialogo funzionale.</span><span class="sxs-lookup"><span data-stu-id="1d656-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span>  <span data-ttu-id="1d656-134">È necessario eseguire l'override di `TranslateAccelerator` implementazione (che proviene `IKeyboardInputSink`, un'interfaccia che <xref:System.Windows.Interop.HwndHost> implementa).</span><span class="sxs-lookup"><span data-stu-id="1d656-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span>  <span data-ttu-id="1d656-135">Questo metodo viene chiamato quando l'applicazione riceve WM_KEYDOWN e WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="1d656-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>  
  
```  
#undef TranslateAccelerator  
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
            ModifierKeys modifiers) override   
        {  
            ::MSG m = ConvertMessage(msg);  
  
            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know   
            // what to do when it reaches the last tab stop  
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
                TraversalRequest^ request = nullptr;  
  
                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
                    // this code should work, but there’s a bug with interop shift-tab in current builds                      
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
                }  
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {  
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
                }  
  
                if (request != nullptr)  
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
  
            }  
  
            // Only call IsDialogMessage for keys it will do something with.  
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
                switch (m.wParam) {  
                    case VK_TAB:  
                    case VK_LEFT:  
                    case VK_UP:  
                    case VK_RIGHT:  
                    case VK_DOWN:  
                    case VK_EXECUTE:  
                    case VK_RETURN:  
                    case VK_ESCAPE:  
                    case VK_CANCEL:  
                        IsDialogMessage(dialog, &m);  
                        // IsDialogMessage should be called ProcessDialogMessage --  
                        // it processes messages without ever really telling you  
                        // if it handled a specific message or not  
                        return true;  
                }  
            }  
  
            return false; // not a key we handled  
        }  
```  
  
 <span data-ttu-id="1d656-136">Si tratta di una grande quantità di codice complesso, pertanto potrebbe usare alcune spiegazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="1d656-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span>  <span data-ttu-id="1d656-137">Prima di tutto il codice usando [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] e [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macro; è necessario tenere presente che è già presente una macro denominata `TranslateAccelerator`, definito in winuser. h:</span><span class="sxs-lookup"><span data-stu-id="1d656-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 <span data-ttu-id="1d656-138">Pertanto, assicurarsi di definire un `TranslateAccelerator` metodo e non un `TranslateAcceleratorW` (metodo).</span><span class="sxs-lookup"><span data-stu-id="1d656-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>  
  
 <span data-ttu-id="1d656-139">Analogamente, non c'è gestita sia il winuser. h non gestito MSG `Microsoft::Win32::MSG` struct.</span><span class="sxs-lookup"><span data-stu-id="1d656-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span>  <span data-ttu-id="1d656-140">È possibile risolvere l'ambiguità tra i due oggetti tramite il [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operatore.</span><span class="sxs-lookup"><span data-stu-id="1d656-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 <span data-ttu-id="1d656-141">Entrambi accodati abbiano gli stessi dati, ma a volte è più facile lavorare con la definizione non gestita, in modo che in questo esempio è possibile definire la routine di conversione ovvio:</span><span class="sxs-lookup"><span data-stu-id="1d656-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>  
  
```  
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {  
    ::MSG m;  
    m.hwnd = (HWND) msg.hwnd.ToPointer();  
    m.lParam = (LPARAM) msg.lParam.ToPointer();  
    m.message = msg.message;  
    m.wParam = (WPARAM) msg.wParam.ToPointer();  
  
    m.time = msg.time;  
  
    POINT pt;  
    pt.x = msg.pt_x;  
    pt.y = msg.pt_y;  
    m.pt = pt;  
  
    return m;  
}  
```  
  
 <span data-ttu-id="1d656-142">Tornare a `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="1d656-142">Back to `TranslateAccelerator`.</span></span>  <span data-ttu-id="1d656-143">Il principio di base consiste nel chiamare il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] funzione `IsDialogMessage` per effettuare più operazioni possibili, ma `IsDialogMessage` non dispone dell'accesso a qualsiasi elemento all'esterno della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1d656-143">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="1d656-144">Mentre una scheda di utente nella finestra di dialogo, quando la tabulazione in esecuzione oltre l'ultimo controllo nella finestra di dialogo, è necessario impostare lo stato attivo il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte chiamando `IKeyboardInputSite::OnNoMoreStops`.</span><span class="sxs-lookup"><span data-stu-id="1d656-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>  
  
```  
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know   
// what to do when it reaches the last tab stop  
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
    TraversalRequest^ request = nullptr;  
  
    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
    }  
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
    }  
  
    if (request != nullptr)  
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
}  
```  
  
 <span data-ttu-id="1d656-145">Infine, viene chiamato `IsDialogMessage`.</span><span class="sxs-lookup"><span data-stu-id="1d656-145">Finally, call `IsDialogMessage`.</span></span>  <span data-ttu-id="1d656-146">Ma una delle responsabilità di un `TranslateAccelerator` metodo segnala [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se è gestita la sequenza di tasti o meno.</span><span class="sxs-lookup"><span data-stu-id="1d656-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="1d656-147">Se non si ha gestito, l'evento di input può effettuare il tunneling e bubbling attraverso il resto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d656-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="1d656-148">In questo caso, si esporrà una particolarità della gestione dei messaggi della tastiera e la natura dell'architettura di input in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d656-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="1d656-149">Sfortunatamente, `IsDialogMessage` non restituito in alcun modo se gestisce una particolare sequenza di tasti.</span><span class="sxs-lookup"><span data-stu-id="1d656-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span>  <span data-ttu-id="1d656-150">Peggio ancora, verrà chiamato `DispatchMessage()` su sequenze di tasti che non deve gestire.</span><span class="sxs-lookup"><span data-stu-id="1d656-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="1d656-151">Pertanto è necessario decodificare `IsDialogMessage`e chiamarlo soltanto per le chiavi si conosce lo gestirà:</span><span class="sxs-lookup"><span data-stu-id="1d656-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>  
  
```  
// Only call IsDialogMessage for keys it will do something with.  
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
    switch (m.wParam) {  
        case VK_TAB:  
        case VK_LEFT:  
        case VK_UP:  
        case VK_RIGHT:  
        case VK_DOWN:  
        case VK_EXECUTE:  
        case VK_RETURN:  
        case VK_ESCAPE:  
        case VK_CANCEL:  
            IsDialogMessage(dialog, &m);  
            // IsDialogMessage should be called ProcessDialogMessage --  
            // it processes messages without ever really telling you  
            // if it handled a specific message or not  
            return true;  
    }  
```  
  
### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="1d656-152">Eseguire l'override del metodo TabInto per supportare la tabulazione</span><span class="sxs-lookup"><span data-stu-id="1d656-152">Override TabInto Method to Support Tabbing</span></span>  
 <span data-ttu-id="1d656-153">Ora che è stata implementata `TranslateAccelerator`, un utente può spostarsi all'interno della finestra di dialogo casella e uscirne tramite tab in maggiore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d656-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="1d656-154">Ma un utente non è possibile spostarsi nuovamente nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1d656-154">But a user cannot tab back into the dialog box.</span></span>  <span data-ttu-id="1d656-155">Per risolvere questo problema, si esegue l'override `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="1d656-155">To solve that, you override `TabInto`:</span></span>  
  
```  
public:   
    virtual bool TabInto(TraversalRequest^ request) override {  
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {  
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
            SetFocus(lastTabStop);  
        }  
        else {  
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
            SetFocus(firstTabStop);  
        }  
        return true;  
    }  
```  
  
 <span data-ttu-id="1d656-156">Il `TraversalRequest` parametro indica se l'azione di tab è una scheda o MAIUSC.</span><span class="sxs-lookup"><span data-stu-id="1d656-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="1d656-157">Eseguire l'override del metodo OnMnemonic per supportare i tasti di scelta</span><span class="sxs-lookup"><span data-stu-id="1d656-157">Override OnMnemonic Method to Support Mnemonics</span></span>  
 <span data-ttu-id="1d656-158">Gestione della tastiera è quasi completata, ma è presente un elemento mancante: i tasti di scelta non funzionano.</span><span class="sxs-lookup"><span data-stu-id="1d656-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span>  <span data-ttu-id="1d656-159">Se un utente preme alt + F, attivo non passa per la "First name:" finestra di modifica.</span><span class="sxs-lookup"><span data-stu-id="1d656-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="1d656-160">Pertanto, si esegue l'override di `OnMnemonic` metodo:</span><span class="sxs-lookup"><span data-stu-id="1d656-160">So, you override the `OnMnemonic` method:</span></span>  
  
```  
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {  
    ::MSG m = ConvertMessage(msg);  
  
    // If it's one of our mnemonics, set focus to the appropriate hwnd  
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {  
        int dialogitem = 9999;  
        switch (m.wParam) {  
            case 's': dialogitem = IDOK; break;  
            case 'c': dialogitem = IDCANCEL; break;  
            case 'f': dialogitem = IDC_EDIT1; break;  
            case 'l': dialogitem = IDC_EDIT2; break;  
            case 'p': dialogitem = IDC_EDIT3; break;  
            case 'a': dialogitem = IDC_EDIT4; break;  
            case 'i': dialogitem = IDC_EDIT5; break;  
            case 't': dialogitem = IDC_EDIT6; break;  
            case 'z': dialogitem = IDC_EDIT7; break;  
        }  
        if (dialogitem != 9999) {  
            HWND hwnd = GetDlgItem(dialog, dialogitem);  
            SetFocus(hwnd);  
            return true;  
        }  
    }  
    return false; // key unhandled  
};  
```  
  
 <span data-ttu-id="1d656-161">Perché non chiamare `IsDialogMessage` qui?</span><span class="sxs-lookup"><span data-stu-id="1d656-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="1d656-162">È necessario lo stesso problema come prima, ovvero è necessario essere in grado di informare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se il codice gestito la sequenza di tasti oppure No, di codice e `IsDialogMessage` non è possibile.</span><span class="sxs-lookup"><span data-stu-id="1d656-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span>  <span data-ttu-id="1d656-163">È inoltre disponibile un problema del secondo, in quanto `IsDialogMessage` rifiuta di elaborare il tasto di scelta rapida se l'oggetto HWND con lo stato attivo non è presente all'interno della casella di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1d656-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>  
  
### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="1d656-164">Creare un'istanza della classe HwndHost derivata</span><span class="sxs-lookup"><span data-stu-id="1d656-164">Instantiate the HwndHost Derived Class</span></span>  
 <span data-ttu-id="1d656-165">Infine, ora che tutto il supporto di scheda e chiave è in uso, è possibile inserire le <xref:System.Windows.Interop.HwndHost> in più grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d656-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="1d656-166">Se l'applicazione principale viene scritto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è il modo più semplice per inserirlo nel posto giusto per lasciare vuota <xref:System.Windows.Controls.Border> elemento in cui si desidera inserire il <xref:System.Windows.Interop.HwndHost>.</span><span class="sxs-lookup"><span data-stu-id="1d656-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span>  <span data-ttu-id="1d656-167">Di seguito si crea una <xref:System.Windows.Controls.Border> denominato `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="1d656-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>  
  
```  
<Window x:Class="WPFApplication1.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Windows Presentation Framework Application"  
    Loaded="Window1_Loaded"  
    >  
    <StackPanel>  
        <Button Content="WPF button"/>  
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>  
        <Button Content="WPF button"/>  
    </StackPanel>  
</Window>  
```  
  
 <span data-ttu-id="1d656-168">Quindi questo punto, è trovare un buon punto nella sequenza di codice per creare un'istanza di <xref:System.Windows.Interop.HwndHost> e connetterla al <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="1d656-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span>  <span data-ttu-id="1d656-169">In questo esempio, si verrà inserirlo all'interno del costruttore per il <xref:System.Windows.Window> classe derivata:</span><span class="sxs-lookup"><span data-stu-id="1d656-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>  
  
```  
public partial class Window1 : Window {  
    public Window1() {  
    }  
  
    void Window1_Loaded(object sender, RoutedEventArgs e) {  
        HwndHost host = new ManagedCpp.MyHwndHost();  
        insertHwndHostHere.Child = host;  
    }  
}  
```  
  
 <span data-ttu-id="1d656-170">Che offre:</span><span class="sxs-lookup"><span data-stu-id="1d656-170">Which gives you:</span></span>  
  
 <span data-ttu-id="1d656-171">![Schermata dell'applicazione WPF](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")</span><span class="sxs-lookup"><span data-stu-id="1d656-171">![WPF application screen shot](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d656-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d656-172">See also</span></span>
- [<span data-ttu-id="1d656-173">Interoperatività di WPF e Win32</span><span class="sxs-lookup"><span data-stu-id="1d656-173">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
