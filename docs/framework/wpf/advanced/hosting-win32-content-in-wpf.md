---
title: Hosting di contenuto Win32 in WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c92e5b045b248337f1cb96c333ac38f1228dd90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-win32-content-in-wpf"></a>Hosting di contenuto Win32 in WPF
## <a name="prerequisites"></a>Prerequisiti  
 Vedere [interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Una procedura dettagliata di Win32 all'interno di Windows Presentation Framework (HwndHost)  
 Per riutilizzare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenuto all'interno di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni utilizzano <xref:System.Windows.Interop.HwndHost>, che è un controllo che rende HWND simile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.  Come <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> è facile da utilizzare: derivano da <xref:System.Windows.Interop.HwndHost> e implementare `BuildWindowCore` e `DestroyWindowCore` metodi, quindi creare un'istanza del <xref:System.Windows.Interop.HwndHost> classe derivata e inserirlo all'interno del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione.  
  
 Se il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logica è già compresso come un controllo, è possibile che il `BuildWindowCore` implementazione è poco più di una chiamata a `CreateWindow`.  Ad esempio, per creare un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo LISTBOX di [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
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
  
 Si supponga, tuttavia il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] codice non sia completamente autonomo? Se in tal caso, è possibile creare un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra di dialogo casella e incorporare il contenuto in un maggiore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.  Nell'esempio viene illustrato in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] e [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], sebbene sia possibile effettuare questa operazione in una lingua diversa o dalla riga di comando.  
  
 Iniziare con una semplice finestra di dialogo, viene compilato in un [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] progetto.  
  
 Successivamente, inserire la finestra di dialogo nel maggiore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione:  
  
-   Compilare il [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] come gestita (`/clr`)  
  
-   Attivare la finestra di dialogo in un controllo  
  
-   Definire la classe derivata di <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` e `DestroyWindowCore` metodi  
  
-   Eseguire l'override `TranslateAccelerator` metodo per gestire le chiavi di finestra di dialogo  
  
-   Eseguire l'override `TabInto` per supportare la tabulazione (metodo)  
  
-   Eseguire l'override `OnMnemonic` per supportare i tasti di scelta (metodo)  
  
-   Creare un'istanza di <xref:System.Windows.Interop.HwndHost> sottoclasse e inserirlo in destra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento  
  
### <a name="turn-the-dialog-into-a-control"></a>Attivare la finestra di dialogo in un controllo  
 È possibile attivare una finestra di dialogo in HWND usando gli stili WS_CHILD e DS_CONTROL figlio.  Andare nel file di risorsa (RC) in cui è definita la finestra di dialogo e trovare l'inizio della definizione della finestra di dialogo:  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 Modificare la seconda riga a:  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 Questa azione non completamente comprimerlo in un controllo autonomo. è necessario chiamare `IsDialogMessage()` in modo [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] determinati messaggi vengano elaborati, ma la modifica del controllo fornisce un modo semplice per inserire i controlli in un altro oggetto HWND.  
  
## <a name="subclass-hwndhost"></a>Sottoclasse HwndHost  
 Importare gli spazi dei nomi seguenti:  
  
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
  
 Quindi creare una classe derivata di <xref:System.Windows.Interop.HwndHost> ed eseguire l'override di `BuildWindowCore` e `DestroyWindowCore` metodi:  
  
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
  
 Questo caso si usa il `CreateDialog` per creare la finestra di dialogo che è realmente un controllo.  Poiché si tratta di uno dei primi metodi chiamati all'interno di [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], è inoltre necessario eseguire alcuni standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] inizializzazione richiamando una funzione che verrà definita in un secondo momento, chiamato `InitializeGlobals()`:  
  
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
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Eseguire l'override del metodo TranslateAccelerator per gestire le chiavi di finestra di dialogo  
 Se si esegue questo esempio a questo punto, si otterrebbe un controllo di finestra di dialogo che consente di visualizzare, ma in cui viene ignorata tutti della tastiera che consente l'elaborazione di una finestra di dialogo di una finestra di dialogo funzionale.  È necessario eseguire l'override di `TranslateAccelerator` implementazione (proveniente da `IKeyboardInputSink`, un'interfaccia che <xref:System.Windows.Interop.HwndHost> implementa).  Questo metodo viene chiamato quando l'applicazione riceve WM_KEYDOWN e WM_SYSKEYDOWN.  
  
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
  
 Si tratta di una grande quantità di codice in un dato specifico, pertanto è possibile usare alcune informazioni dettagliate sulle.  Prima di tutto, il codice utilizzando [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] e [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] ; le macro, è necessario tenere presente che è già presente una macro denominata `TranslateAccelerator`, definito in winuser. h:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 Assicurarsi quindi di definire un `TranslateAccelerator` (metodo) e non un `TranslateAcceleratorW` metodo.  
  
 Analogamente, è presente il winuser. h MSG non gestito e gestito `Microsoft::Win32::MSG` struct.  Per evitare ambiguità tra i due oggetti utilizzando il [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operatore.  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 Sia accodati hanno gli stessi dati, ma a volte risulta più facile lavorare con la definizione non gestita, pertanto in questo esempio è possibile definire la routine di conversione ovvia:  
  
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
  
 Torna alla `TranslateAccelerator`.  Il principio di base consiste nel chiamare il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] funzione `IsDialogMessage` per effettuare più operazioni possibili, ma `IsDialogMessage` non dispone dell'accesso a qualsiasi elemento esterno la finestra di dialogo. Durante l'esecuzione di una scheda di utente nella finestra di dialogo, quando la tabulazione oltre l'ultimo controllo nella finestra di dialogo, è necessario impostare lo stato attivo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte chiamando `IKeyboardInputSite::OnNoMoreStops`.  
  
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
  
 Infine, viene chiamato `IsDialogMessage`.  Ma una delle responsabilità di un `TranslateAccelerator` metodo impone [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se la sequenza di tasti è stata gestita o non. Se non viene gestita, l'evento di input può effettuare il tunneling e a bolle attraverso il resto dell'applicazione. In questo caso, si espone una particolarità della gestione dei messaggi della tastiera e la natura dell'architettura di input in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Purtroppo, `IsDialogMessage` non restituito in alcun modo se gestisce una particolare sequenza di tasti.  Peggio ancora, verrà chiamato `DispatchMessage()` su sequenze di tasti che non deve gestire!  Pertanto è necessario decodificare `IsDialogMessage`e lo chiama solo per gestiscono i tasti che:  
  
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
  
### <a name="override-tabinto-method-to-support-tabbing"></a>Eseguire l'override del metodo TabInto per supportare la tabulazione  
 Ora che è stato implementato `TranslateAccelerator`, un utente può spostarsi nella finestra di dialogo casella e uscirne tramite tab in maggiore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.  Ma un utente non è possibile scheda alla finestra di dialogo.  Per risolvere questo problema, si esegue l'override `TabInto`:  
  
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
  
 Il `TraversalRequest` parametro indica se l'azione della scheda è una scheda o MAIUSC.  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Eseguire l'override del metodo OnMnemonic per supportare i tasti di scelta  
 Gestione della tastiera è quasi completata, ma ne esiste uno cosa mancante: tasti di scelta non funzionano.  Se un utente preme alt + F, attivo non passa per il "nome:" casella di modifica. In tal caso, si esegue l'override di `OnMnemonic` metodo:  
  
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
  
 Non viene chiamato `IsDialogMessage` qui?  È necessario lo stesso problema come prima, ovvero è necessario essere in grado di informare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] codice se il codice gestito la sequenza di tasti oppure No, e `IsDialogMessage` non.  È inoltre disponibile un secondo problema, perché `IsDialogMessage` rifiuta di elaborare il tasto di scelta rapida se HWND con lo stato attivo non è presente all'interno della casella della finestra di dialogo.  
  
### <a name="instantiate-the-hwndhost-derived-class"></a>Creare un'istanza della classe HwndHost derivata  
 Infine, dopo che tutto il supporto di scheda e di chiave è presente, è possibile inserire il <xref:System.Windows.Interop.HwndHost> in più grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.  Se l'applicazione principale viene scritto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è il modo più semplice per inserirlo nella posizione corretta per lasciare vuota <xref:System.Windows.Controls.Border> elemento in cui si desidera inserire il <xref:System.Windows.Interop.HwndHost>.  Di seguito si crea un <xref:System.Windows.Controls.Border> denominato `insertHwndHostHere`:  
  
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
  
 Quindi è comunque per trovare un buon punto nella sequenza di codice per creare un'istanza di <xref:System.Windows.Interop.HwndHost> e connetterla al <xref:System.Windows.Controls.Border>.  In questo esempio, si verrà inserirlo all'interno del costruttore per la <xref:System.Windows.Window> classe derivata:  
  
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
  
 Che consente di:  
  
 ![Schermata dell'applicazione WPF](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
