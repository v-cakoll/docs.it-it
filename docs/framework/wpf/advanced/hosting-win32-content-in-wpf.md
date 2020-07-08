---
title: Hosting di contenuto Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: c0c62f1999feaf591c512314515f01e83fa12591
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052091"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="cc601-102">Hosting di contenuto Win32 in WPF</span><span class="sxs-lookup"><span data-stu-id="cc601-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc601-103">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc601-103">Prerequisites</span></span>

<span data-ttu-id="cc601-104">Vedere l' [interoperatività di WPF e Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="cc601-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="cc601-105">Procedura dettagliata di Win32 all'interno di Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="cc601-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="cc601-106">Per riutilizzare il contenuto Win32 all'interno delle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni, utilizzare <xref:System.Windows.Interop.HwndHost> , che è un controllo che rende gli HWND simili al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc601-106">To reuse Win32 content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="cc601-107">Come <xref:System.Windows.Interop.HwndSource> , <xref:System.Windows.Interop.HwndHost> è facile da usare: derivare da <xref:System.Windows.Interop.HwndHost> e `BuildWindowCore` implementare `DestroyWindowCore` i metodi e, quindi creare un'istanza della <xref:System.Windows.Interop.HwndHost> classe derivata e inserirla all'interno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc601-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="cc601-108">Se la logica Win32 è già inclusa in un pacchetto come controllo, l' `BuildWindowCore` implementazione è poco più di una chiamata a `CreateWindow` .</span><span class="sxs-lookup"><span data-stu-id="cc601-108">If your Win32 logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="cc601-109">Ad esempio, per creare un controllo LISTBOX Win32 in C++:</span><span class="sxs-lookup"><span data-stu-id="cc601-109">For example, to create a Win32 LISTBOX control in C++:</span></span>

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

<span data-ttu-id="cc601-110">Ma si supponga che il codice Win32 non sia abbastanza indipendente?</span><span class="sxs-lookup"><span data-stu-id="cc601-110">But suppose the Win32 code is not quite so self-contained?</span></span> <span data-ttu-id="cc601-111">In tal caso, è possibile creare una finestra di dialogo Win32 e incorporarne il contenuto in un'applicazione di dimensioni maggiori [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc601-111">If so, you can create a Win32 dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cc601-112">Questo esempio viene illustrato in Visual Studio e C++, anche se è possibile eseguire questa operazione in un linguaggio diverso o nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cc601-112">The sample shows this in Visual Studio and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="cc601-113">Iniziare con una semplice finestra di dialogo, compilata in un progetto DLL C++.</span><span class="sxs-lookup"><span data-stu-id="cc601-113">Start with a simple dialog, which is compiled into a C++ DLL project.</span></span>

<span data-ttu-id="cc601-114">Successivamente, introdurre la finestra di dialogo nell' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione più grande:</span><span class="sxs-lookup"><span data-stu-id="cc601-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="cc601-115">Compila la DLL come gestita ( `/clr` )</span><span class="sxs-lookup"><span data-stu-id="cc601-115">Compile the DLL as managed (`/clr`)</span></span>

- <span data-ttu-id="cc601-116">Trasformare la finestra di dialogo in un controllo</span><span class="sxs-lookup"><span data-stu-id="cc601-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="cc601-117">Definire la classe derivata di <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` i `DestroyWindowCore` metodi e</span><span class="sxs-lookup"><span data-stu-id="cc601-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="cc601-118">`TranslateAccelerator`Metodo di override per gestire le chiavi di dialogo</span><span class="sxs-lookup"><span data-stu-id="cc601-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="cc601-119">`TabInto`Metodo di override per supportare la tabulazione</span><span class="sxs-lookup"><span data-stu-id="cc601-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="cc601-120">`OnMnemonic`Metodo di override per supportare i tasti di scelta</span><span class="sxs-lookup"><span data-stu-id="cc601-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="cc601-121">Creare un'istanza della <xref:System.Windows.Interop.HwndHost> sottoclasse e inserirla nell'elemento a destra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc601-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="cc601-122">Trasformare la finestra di dialogo in un controllo</span><span class="sxs-lookup"><span data-stu-id="cc601-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="cc601-123">È possibile trasformare una finestra di dialogo in un HWND figlio utilizzando gli stili WS_CHILD e DS_CONTROL.</span><span class="sxs-lookup"><span data-stu-id="cc601-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="cc601-124">Passare al file di risorse (. RC) in cui è definita la finestra di dialogo e trovare l'inizio della definizione della finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="cc601-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="cc601-125">Modificare la seconda riga in:</span><span class="sxs-lookup"><span data-stu-id="cc601-125">Change the second line to:</span></span>

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="cc601-126">Questa azione non esegue completamente il pacchetto in un controllo indipendente; è comunque necessario chiamare in `IsDialogMessage()` modo che Win32 possa elaborare determinati messaggi, ma la modifica del controllo fornisce un modo semplice per inserire i controlli all'interno di un altro HWND.</span><span class="sxs-lookup"><span data-stu-id="cc601-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so Win32 can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="cc601-127">Classe HwndHost</span><span class="sxs-lookup"><span data-stu-id="cc601-127">Subclass HwndHost</span></span>

<span data-ttu-id="cc601-128">Importare gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc601-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="cc601-129">Creare quindi una classe derivata di <xref:System.Windows.Interop.HwndHost> ed eseguire l'override dei `BuildWindowCore` `DestroyWindowCore` metodi e:</span><span class="sxs-lookup"><span data-stu-id="cc601-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="cc601-130">Qui viene usato `CreateDialog` per creare la finestra di dialogo che è effettivamente un controllo.</span><span class="sxs-lookup"><span data-stu-id="cc601-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="cc601-131">Poiché si tratta di uno dei primi metodi chiamati all'interno della DLL, è necessario eseguire anche un'inizializzazione Win32 standard chiamando una funzione che verrà definita in seguito, denominata `InitializeGlobals()` :</span><span class="sxs-lookup"><span data-stu-id="cc601-131">Since this is one of the first methods called inside the DLL, you should also do some standard Win32 initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="cc601-132">Eseguire l'override del metodo TranslateAccelerator per gestire le chiavi di dialogo</span><span class="sxs-lookup"><span data-stu-id="cc601-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="cc601-133">Se è stato eseguito questo esempio, si otterrebbe un controllo finestra di dialogo che viene visualizzato, ma si ignorerà tutta l'elaborazione della tastiera che rende una finestra di dialogo funzionante.</span><span class="sxs-lookup"><span data-stu-id="cc601-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="cc601-134">A questo punto è necessario eseguire l'override dell' `TranslateAccelerator` implementazione (che deriva da `IKeyboardInputSink` , un'interfaccia che <xref:System.Windows.Interop.HwndHost> implementa).</span><span class="sxs-lookup"><span data-stu-id="cc601-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="cc601-135">Questo metodo viene chiamato quando l'applicazione riceve WM_KEYDOWN e WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="cc601-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="cc601-136">Si tratta di una grande quantità di codice in un pezzo, quindi è possibile usare alcune spiegazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="cc601-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="cc601-137">Per prima cosa, il codice usa le macro C++ e C++; è necessario tenere presente che esiste già una macro denominata `TranslateAccelerator` , definita in winuser. h:</span><span class="sxs-lookup"><span data-stu-id="cc601-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="cc601-138">Assicurarsi quindi di definire un `TranslateAccelerator` metodo e non un `TranslateAcceleratorW` metodo.</span><span class="sxs-lookup"><span data-stu-id="cc601-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="cc601-139">Analogamente, sono presenti sia il messaggio winuser. h non gestito che lo `Microsoft::Win32::MSG` struct gestito.</span><span class="sxs-lookup"><span data-stu-id="cc601-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="cc601-140">È possibile evitare ambiguità tra le due usando l' `::` operatore C++.</span><span class="sxs-lookup"><span data-stu-id="cc601-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}
```

<span data-ttu-id="cc601-141">Entrambi i messaggi hanno gli stessi dati, ma a volte è più facile lavorare con la definizione non gestita, quindi in questo esempio è possibile definire la routine di conversione ovvia:</span><span class="sxs-lookup"><span data-stu-id="cc601-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>

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

<span data-ttu-id="cc601-142">Tornare a `TranslateAccelerator` .</span><span class="sxs-lookup"><span data-stu-id="cc601-142">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="cc601-143">Il principio di base consiste nel chiamare la funzione Win32 `IsDialogMessage` per eseguire il maggior lavoro possibile, ma `IsDialogMessage` non ha accesso ad alcun elemento all'esterno della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cc601-143">The basic principle is to call the Win32 function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="cc601-144">Come scheda utente intorno alla finestra di dialogo, quando la tabulazione viene eseguita oltre l'ultimo controllo nella finestra di dialogo, è necessario impostare lo stato attivo sulla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte chiamando `IKeyboardInputSite::OnNoMoreStops` .</span><span class="sxs-lookup"><span data-stu-id="cc601-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="cc601-145">Infine, viene chiamato `IsDialogMessage`.</span><span class="sxs-lookup"><span data-stu-id="cc601-145">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="cc601-146">Tuttavia, una delle responsabilità di un `TranslateAccelerator` metodo è [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] determinare se la sequenza di tasti è stata gestita o meno.</span><span class="sxs-lookup"><span data-stu-id="cc601-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="cc601-147">Se non è stato gestito, l'evento di input può eseguire il tunneling e la bolla nel resto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc601-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="cc601-148">In questo caso si esporrà una peculiarità della gestione questo caso della tastiera e della natura dell'architettura di input in Win32.</span><span class="sxs-lookup"><span data-stu-id="cc601-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in Win32.</span></span> <span data-ttu-id="cc601-149">Sfortunatamente, non `IsDialogMessage` restituisce alcun modo se gestisce una particolare sequenza di tasti.</span><span class="sxs-lookup"><span data-stu-id="cc601-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="cc601-150">Ancora peggiori, chiamerà le `DispatchMessage()` sequenze di tasti che non devono essere gestite.</span><span class="sxs-lookup"><span data-stu-id="cc601-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="cc601-151">Sarà quindi necessario decompilare `IsDialogMessage` il computer e chiamarlo solo per le chiavi note che gestirà:</span><span class="sxs-lookup"><span data-stu-id="cc601-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="cc601-152">Eseguire l'override del metodo TabInto per supportare la tabulazione</span><span class="sxs-lookup"><span data-stu-id="cc601-152">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="cc601-153">Ora che è stata implementata `TranslateAccelerator` , un utente può spostarsi all'interno della finestra di dialogo e visualizzarne la tabulazione nell'applicazione più grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc601-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cc601-154">Tuttavia, un utente non può riportare la scheda nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cc601-154">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="cc601-155">Per risolvere il problemi, eseguire l'override di `TabInto` :</span><span class="sxs-lookup"><span data-stu-id="cc601-155">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="cc601-156">Il `TraversalRequest` parametro indica se l'azione della scheda è una scheda o una scheda di spostamento.</span><span class="sxs-lookup"><span data-stu-id="cc601-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="cc601-157">Eseguire l'override del metodo onmnemonico per supportare i tasti di scelta</span><span class="sxs-lookup"><span data-stu-id="cc601-157">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="cc601-158">La gestione della tastiera è quasi completa, ma manca un elemento: i tasti di scelta non funzionano.</span><span class="sxs-lookup"><span data-stu-id="cc601-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="cc601-159">Se un utente preme ALT + F, lo stato attivo non passa alla casella di modifica "First Name:".</span><span class="sxs-lookup"><span data-stu-id="cc601-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="cc601-160">Quindi, si esegue l'override del `OnMnemonic` Metodo:</span><span class="sxs-lookup"><span data-stu-id="cc601-160">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="cc601-161">Perché non chiamare `IsDialogMessage` qui?</span><span class="sxs-lookup"><span data-stu-id="cc601-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="cc601-162">Si ha lo stesso problema di prima: è necessario essere in grado di informare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] codice se il codice ha gestito o meno la sequenza di tasti `IsDialogMessage` .</span><span class="sxs-lookup"><span data-stu-id="cc601-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="cc601-163">Esiste anche un secondo problema, perché `IsDialogMessage` rifiuta di elaborare il tasto di scelta se l'HWND con stato attivo non si trova all'interno della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cc601-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="cc601-164">Creare un'istanza della classe derivata HwndHost</span><span class="sxs-lookup"><span data-stu-id="cc601-164">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="cc601-165">Infine, ora che tutto il supporto per chiavi e schede è disponibile, è possibile inserire nell' <xref:System.Windows.Interop.HwndHost> applicazione più grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc601-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cc601-166">Se l'applicazione principale viene scritta in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , il modo più semplice per inserirlo nella posizione corretta consiste nel lasciare un <xref:System.Windows.Controls.Border> elemento vuoto in cui si vuole inserire <xref:System.Windows.Interop.HwndHost> .</span><span class="sxs-lookup"><span data-stu-id="cc601-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="cc601-167">Qui viene creato un oggetto <xref:System.Windows.Controls.Border> denominato `insertHwndHostHere` :</span><span class="sxs-lookup"><span data-stu-id="cc601-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="cc601-168">Quindi, tutto ciò che rimane è trovare un posto valido nella sequenza di codice per creare un'istanza di <xref:System.Windows.Interop.HwndHost> e connetterlo a <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="cc601-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="cc601-169">In questo esempio, verrà inserito nel costruttore per la <xref:System.Windows.Window> classe derivata:</span><span class="sxs-lookup"><span data-stu-id="cc601-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="cc601-170">Che offre:</span><span class="sxs-lookup"><span data-stu-id="cc601-170">Which gives you:</span></span>

![Screenshot dell'app WPF in esecuzione.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="cc601-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc601-172">See also</span></span>

- [<span data-ttu-id="cc601-173">Interoperatività di WPF e Win32</span><span class="sxs-lookup"><span data-stu-id="cc601-173">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
