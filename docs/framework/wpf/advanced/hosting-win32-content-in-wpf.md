---
title: Hosting di contenuto Win32 in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: ee260d58cdb4dc971fc32ca5c889b459b6a48489
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484732"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="cb91e-102">Hosting di contenuto Win32 in WPF</span><span class="sxs-lookup"><span data-stu-id="cb91e-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb91e-103">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cb91e-103">Prerequisites</span></span>

<span data-ttu-id="cb91e-104">Vedere l'interoperatività [di WPF e Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="cb91e-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="cb91e-105">Procedura dettagliata di Win32 all'interno di Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="cb91e-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="cb91e-106">Per riutilizzare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto all'interno <xref:System.Windows.Interop.HwndHost>delle applicazioni, utilizzare, che è un controllo che rende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli HWND simili al contenuto.</span><span class="sxs-lookup"><span data-stu-id="cb91e-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="cb91e-107">Come <xref:System.Windows.Interop.HwndSource>, `BuildWindowCore` <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] `DestroyWindowCore` è facile da usare: derivare da e implementare i metodi e, quindi creare un'istanza della classe derivata e inserirla all'interno di <xref:System.Windows.Interop.HwndHost> applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb91e-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="cb91e-108">Se la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logica è già inclusa in un pacchetto come controllo, l' `BuildWindowCore` implementazione è poco più di una chiamata a `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="cb91e-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="cb91e-109">Ad esempio, per creare un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo ListBox in C++:</span><span class="sxs-lookup"><span data-stu-id="cb91e-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in C++:</span></span>

```cpp
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

<span data-ttu-id="cb91e-110">Ma si supponga [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] che il codice non sia abbastanza indipendente?</span><span class="sxs-lookup"><span data-stu-id="cb91e-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="cb91e-111">In tal caso, è possibile creare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] una finestra di dialogo e incorporarne il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un'applicazione di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="cb91e-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb91e-112">Nell'esempio viene illustrato questo [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] in C++e, sebbene sia anche possibile eseguire questa operazione in un linguaggio diverso o nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cb91e-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="cb91e-113">Iniziare con una semplice finestra di dialogo, compilata C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] in un progetto.</span><span class="sxs-lookup"><span data-stu-id="cb91e-113">Start with a simple dialog, which is compiled into a C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>

<span data-ttu-id="cb91e-114">Successivamente, introdurre la finestra di dialogo nell' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione più grande:</span><span class="sxs-lookup"><span data-stu-id="cb91e-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="cb91e-115">Compila come gestito (`/clr`) [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb91e-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>

- <span data-ttu-id="cb91e-116">Trasformare la finestra di dialogo in un controllo</span><span class="sxs-lookup"><span data-stu-id="cb91e-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="cb91e-117">Definire la classe derivata di <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` i `DestroyWindowCore` metodi e</span><span class="sxs-lookup"><span data-stu-id="cb91e-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="cb91e-118">Metodo `TranslateAccelerator` di override per gestire le chiavi di dialogo</span><span class="sxs-lookup"><span data-stu-id="cb91e-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="cb91e-119">Metodo `TabInto` di override per supportare la tabulazione</span><span class="sxs-lookup"><span data-stu-id="cb91e-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="cb91e-120">Metodo `OnMnemonic` di override per supportare i tasti di scelta</span><span class="sxs-lookup"><span data-stu-id="cb91e-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="cb91e-121">Creare un'istanza <xref:System.Windows.Interop.HwndHost> della sottoclasse e inserirla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'elemento a destra</span><span class="sxs-lookup"><span data-stu-id="cb91e-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="cb91e-122">Trasformare la finestra di dialogo in un controllo</span><span class="sxs-lookup"><span data-stu-id="cb91e-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="cb91e-123">È possibile trasformare una finestra di dialogo in un HWND figlio utilizzando gli stili WS_CHILD e DS_CONTROL.</span><span class="sxs-lookup"><span data-stu-id="cb91e-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="cb91e-124">Passare al file di risorse (. RC) in cui è definita la finestra di dialogo e trovare l'inizio della definizione della finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="cb91e-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="cb91e-125">Modificare la seconda riga in:</span><span class="sxs-lookup"><span data-stu-id="cb91e-125">Change the second line to:</span></span>

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="cb91e-126">Questa azione non esegue completamente il pacchetto in un controllo indipendente; è comunque necessario chiamare `IsDialogMessage()` in modo che sia in grado di elaborare determinati messaggi, ma la modifica del controllo fornisce un modo semplice per [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] inserire i controlli all'interno di un altro HWND.</span><span class="sxs-lookup"><span data-stu-id="cb91e-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="cb91e-127">Classe HwndHost</span><span class="sxs-lookup"><span data-stu-id="cb91e-127">Subclass HwndHost</span></span>

<span data-ttu-id="cb91e-128">Importare gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb91e-128">Import the following namespaces:</span></span>

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

<span data-ttu-id="cb91e-129">Creare quindi una classe derivata di <xref:System.Windows.Interop.HwndHost> ed eseguire l' `BuildWindowCore` override `DestroyWindowCore` dei metodi e:</span><span class="sxs-lookup"><span data-stu-id="cb91e-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

```cpp
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

<span data-ttu-id="cb91e-130">Qui viene usato `CreateDialog` per creare la finestra di dialogo che è effettivamente un controllo.</span><span class="sxs-lookup"><span data-stu-id="cb91e-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="cb91e-131">Poiché si tratta di uno dei primi metodi chiamati all'interno [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]di, è necessario eseguire anche un' [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] inizializzazione standard chiamando una funzione che verrà definita in seguito `InitializeGlobals()`, denominata:</span><span class="sxs-lookup"><span data-stu-id="cb91e-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

```cpp
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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="cb91e-132">Eseguire l'override del metodo TranslateAccelerator per gestire le chiavi di dialogo</span><span class="sxs-lookup"><span data-stu-id="cb91e-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="cb91e-133">Se è stato eseguito questo esempio, si otterrebbe un controllo finestra di dialogo che viene visualizzato, ma si ignorerà tutta l'elaborazione della tastiera che rende una finestra di dialogo funzionante.</span><span class="sxs-lookup"><span data-stu-id="cb91e-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="cb91e-134">A questo punto è necessario `TranslateAccelerator` eseguire l'override dell'implementazione `IKeyboardInputSink`(che deriva da <xref:System.Windows.Interop.HwndHost> , un'interfaccia che implementa).</span><span class="sxs-lookup"><span data-stu-id="cb91e-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="cb91e-135">Questo metodo viene chiamato quando l'applicazione riceve WM_KEYDOWN e WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="cb91e-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

```cpp
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

<span data-ttu-id="cb91e-136">Si tratta di una grande quantità di codice in un pezzo, quindi è possibile usare alcune spiegazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="cb91e-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="cb91e-137">Per prima cosa, il C++ codice C++ usa le macro e; è necessario tenere presente che esiste già una macro denominata `TranslateAccelerator`, definita in winuser. h:</span><span class="sxs-lookup"><span data-stu-id="cb91e-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="cb91e-138">Assicurarsi quindi di definire un `TranslateAccelerator` metodo e non un `TranslateAcceleratorW` metodo.</span><span class="sxs-lookup"><span data-stu-id="cb91e-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="cb91e-139">Analogamente, sono presenti sia il messaggio winuser. h non gestito che lo struct `Microsoft::Win32::MSG` gestito.</span><span class="sxs-lookup"><span data-stu-id="cb91e-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="cb91e-140">È possibile evitare ambiguità tra le due usando l' C++ `::` operatore.</span><span class="sxs-lookup"><span data-stu-id="cb91e-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
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

<span data-ttu-id="cb91e-141">Tornare a `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="cb91e-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="cb91e-142">Il principio di base consiste nel chiamare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] la `IsDialogMessage` funzione per eseguire il maggior lavoro possibile, ma `IsDialogMessage` non può accedere ad alcun elemento all'esterno della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cb91e-142">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="cb91e-143">Come scheda utente intorno alla finestra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] `IKeyboardInputSite::OnNoMoreStops`di dialogo, quando la tabulazione viene eseguita oltre l'ultimo controllo nella finestra di dialogo, è necessario impostare lo stato attivo sulla parte chiamando.</span><span class="sxs-lookup"><span data-stu-id="cb91e-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

```cpp
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

<span data-ttu-id="cb91e-144">Infine, viene chiamato `IsDialogMessage`.</span><span class="sxs-lookup"><span data-stu-id="cb91e-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="cb91e-145">Tuttavia, una delle responsabilità di un `TranslateAccelerator` metodo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è determinare se la sequenza di tasti è stata gestita o meno.</span><span class="sxs-lookup"><span data-stu-id="cb91e-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="cb91e-146">Se non è stato gestito, l'evento di input può eseguire il tunneling e la bolla nel resto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb91e-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="cb91e-147">In questo caso, si esporrà una peculiarità della gestione questo caso della tastiera e della natura dell' [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]architettura di input in.</span><span class="sxs-lookup"><span data-stu-id="cb91e-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="cb91e-148">Sfortunatamente, `IsDialogMessage` non restituisce alcun modo se gestisce una particolare sequenza di tasti.</span><span class="sxs-lookup"><span data-stu-id="cb91e-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="cb91e-149">Ancora peggiori, chiamerà `DispatchMessage()` le sequenze di tasti che non devono essere gestite.</span><span class="sxs-lookup"><span data-stu-id="cb91e-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="cb91e-150">Sarà quindi necessario decompilare `IsDialogMessage`il computer e chiamarlo solo per le chiavi note che gestirà:</span><span class="sxs-lookup"><span data-stu-id="cb91e-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

```cpp
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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="cb91e-151">Eseguire l'override del metodo TabInto per supportare la tabulazione</span><span class="sxs-lookup"><span data-stu-id="cb91e-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="cb91e-152">Ora che è stata implementata `TranslateAccelerator`, un utente può spostarsi all'interno della finestra di dialogo e visualizzarne la tabulazione nell'applicazione più grande. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb91e-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb91e-153">Tuttavia, un utente non può riportare la scheda nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cb91e-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="cb91e-154">Per risolvere il problemi, eseguire `TabInto`l'override di:</span><span class="sxs-lookup"><span data-stu-id="cb91e-154">To solve that, you override `TabInto`:</span></span>

```cpp
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

<span data-ttu-id="cb91e-155">Il `TraversalRequest` parametro indica se l'azione della scheda è una scheda o una scheda di spostamento.</span><span class="sxs-lookup"><span data-stu-id="cb91e-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="cb91e-156">Eseguire l'override del metodo onmnemonico per supportare i tasti di scelta</span><span class="sxs-lookup"><span data-stu-id="cb91e-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="cb91e-157">La gestione della tastiera è quasi completa, ma manca un elemento: i tasti di scelta non funzionano.</span><span class="sxs-lookup"><span data-stu-id="cb91e-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="cb91e-158">Se un utente preme ALT + F, lo stato attivo non passa alla casella di modifica "First Name:".</span><span class="sxs-lookup"><span data-stu-id="cb91e-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="cb91e-159">Quindi, si esegue l' `OnMnemonic` override del metodo:</span><span class="sxs-lookup"><span data-stu-id="cb91e-159">So, you override the `OnMnemonic` method:</span></span>

```cpp
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

<span data-ttu-id="cb91e-160">Perché non chiamare `IsDialogMessage` qui?</span><span class="sxs-lookup"><span data-stu-id="cb91e-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="cb91e-161">Si ha lo stesso problema di prima: è necessario essere in grado di informare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il codice se il codice ha gestito o meno `IsDialogMessage` la sequenza di tasti.</span><span class="sxs-lookup"><span data-stu-id="cb91e-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="cb91e-162">Esiste anche un secondo problema, perché `IsDialogMessage` rifiuta di elaborare il tasto di scelta se l'HWND con stato attivo non si trova all'interno della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cb91e-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="cb91e-163">Creare un'istanza della classe derivata HwndHost</span><span class="sxs-lookup"><span data-stu-id="cb91e-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="cb91e-164">Infine, ora che tutto il supporto per chiavi e schede è disponibile, è possibile inserire <xref:System.Windows.Interop.HwndHost> nell'applicazione più grande. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb91e-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb91e-165">Se l'applicazione principale viene scritta in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], il modo più semplice per inserirlo nella posizione corretta consiste nel lasciare un <xref:System.Windows.Controls.Border> elemento vuoto in cui <xref:System.Windows.Interop.HwndHost>si vuole inserire.</span><span class="sxs-lookup"><span data-stu-id="cb91e-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="cb91e-166">Qui viene creato un <xref:System.Windows.Controls.Border> oggetto `insertHwndHostHere`denominato:</span><span class="sxs-lookup"><span data-stu-id="cb91e-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

```xaml
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

<span data-ttu-id="cb91e-167">Quindi <xref:System.Windows.Interop.HwndHost> , tutto ciò che rimane è trovare un posto valido nella sequenza di codice per creare un'istanza di e connetterlo <xref:System.Windows.Controls.Border>a.</span><span class="sxs-lookup"><span data-stu-id="cb91e-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="cb91e-168">In questo esempio, verrà inserito nel costruttore per la <xref:System.Windows.Window> classe derivata:</span><span class="sxs-lookup"><span data-stu-id="cb91e-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

<span data-ttu-id="cb91e-169">Che offre:</span><span class="sxs-lookup"><span data-stu-id="cb91e-169">Which gives you:</span></span>

![Screenshot dell'app WPF in esecuzione.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="cb91e-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb91e-171">See also</span></span>

- [<span data-ttu-id="cb91e-172">Interoperatività di WPF e Win32</span><span class="sxs-lookup"><span data-stu-id="cb91e-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
