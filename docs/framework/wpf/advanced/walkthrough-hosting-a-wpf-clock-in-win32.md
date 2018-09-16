---
title: 'Procedura dettagliata: hosting di un oggetto Clock WPF in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: ce8209c89430988f57c211d388c6e73b2dc17004
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45674546"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Procedura dettagliata: hosting di un oggetto Clock WPF in Win32
Per inserire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , le applicazioni utilizzano <xref:System.Windows.Interop.HwndSource>, che fornisce HWND che contiene il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto. Prima di tutto si crea il <xref:System.Windows.Interop.HwndSource>, assegnare a esso parametri analoghi a CreateWindow.  Quindi, viene comunicato il <xref:System.Windows.Interop.HwndSource> sul [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto si desidera inserire.  Infine, ottenere l'oggetto HWND fuori il <xref:System.Windows.Interop.HwndSource>. Questa procedura dettagliata illustra come creare un misto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dell'applicazione che implementa nuovamente il sistema operativo **proprietà data e ora** finestra di dialogo.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Visualizzare [interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="how-to-use-this-tutorial"></a>Utilizzo dell'esercitazione  
 Questa esercitazione si concentra sui passaggi importanti per la produzione di un'applicazione di interoperatività. L'esercitazione è supportata da un campione [esempio di interoperatività Clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051), ma che riflette il prodotto finale. Questa esercitazione illustra i passaggi come se si parta da un oggetto esistente [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proprio progetto, ad esempio un progetto già esistente e si aggiunga un ambiente host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'applicazione. È possibile confrontare il prodotto finale con [esempio di interoperatività Clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Procedura dettagliata di Windows Presentation Framework in Win32 (HwndSource)  
 Il grafico seguente illustra il prodotto finale previsto di questa esercitazione:  
  
 ![Finestra di dialogo Proprietà data e ora](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")  
  
 È possibile ricreare questa finestra di dialogo mediante la creazione di C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e usando l'editor finestre per creare la seguente:  
  
 ![Finestra di dialogo Proprietà data e ora](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")  
  
 (Non è necessario usare [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] da utilizzare <xref:System.Windows.Interop.HwndSource>, e non è necessario usare C++ per scrivere [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programmi, ma questo è un modo comune per eseguire questa operazione e si presta bene a una spiegazione di un'esercitazione).  
  
 È necessario eseguire cinque passaggi secondari specifici per inserire un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio nella finestra di dialogo:  
  
1.  Abilitare il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto di chiamare codice gestito (**/clr**) modificando le impostazioni di progetto in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
2.  Creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> in una DLL separata.  
  
3.  Inserirlo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> all'interno di un <xref:System.Windows.Interop.HwndSource>.  
  
4.  Ottenere un oggetto HWND per tale <xref:System.Windows.Controls.Page> utilizzando il <xref:System.Windows.Interop.HwndSource.Handle%2A> proprietà.  
  
5.  Uso [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] deve decidere dove inserire l'oggetto HWND alla più ampia [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applicazione  
  
## <a name="clr"></a>/clr  
 Il primo passaggio consiste nel disattivare questa unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto in un unico che può chiamare codice gestito.  Si usa l'opzione del compilatore /clr che collega alle DLL necessarie che si vuole usare e modificare il metodo principale per l'uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Per consentire l'uso del codice gestito all'interno del progetto C++: pulsante destro del mouse sul progetto win32clock e scegliere **proprietà**.  Nel **generali** pagina delle proprietà (impostazione predefinita), impostare il supporto Common Language Runtime su `/clr`.  
  
 Successivamente, aggiungere i riferimenti alle DLL necessarie per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider e UIAutomationTypes. dll. (le istruzioni seguenti presuppongono che il sistema operativo sia installato nell'unità C:).  
  
1.  Fare clic sul progetto win32clock e scegliere **riferimenti...** e nella finestra di dialogo:  
  
2.  Fare clic sul progetto win32clock e scegliere **riferimenti...** .  
  
3.  Fare clic su **Aggiungi nuovo riferimento**, fare clic sulla scheda Sfoglia, immettere c:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll e fare clic su OK.  
  
4.  Ripetere l'operazione per PresentationFramework.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.  
  
5.  Ripetere l'operazione per WindowsBase.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.  
  
6.  Ripetere l'operazione per UIAutomationTypes.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.  
  
7.  Ripetere l'operazione per UIAutomationProvider.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.  
  
8.  Fare clic su **Aggiungi nuovo riferimento**, selezionare System. dll e fare clic su **OK**.  
  
9. Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per aggiungere riferimenti.  
  
 Infine, aggiungere il `STAThreadAttribute` per il `_tWinMain` metodo per l'uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Questo attributo indica il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] che quando inizializza [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], consigliabile usare un modello di apartment a thread singolo (STA), che è necessario per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).  
  
## <a name="create-a-windows-presentation-framework-page"></a>Creare una pagina di Windows Presentation Framework  
 Successivamente, si crea una DLL che definisce una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>. È spesso più semplice creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> come un'applicazione autonoma e scrittura e debug di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte in questo modo.  Al termine, tale progetto può essere trasformato in una DLL facendo clic con il progetto, fare clic su **proprietà**, accedendo all'applicazione e la modifica tipo di Output alla libreria di classi di Windows.  
  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto dll può quindi essere combinato con il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto (una soluzione contenente due progetti) del mouse sulla soluzione e scegliere **Aggiungi progetto esistente**.  
  
 Per usare tale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll dal [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto, è necessario aggiungere un riferimento:  
  
1.  Fare clic sul progetto win32clock e scegliere **riferimenti...** .  
  
2.  Fare clic su **Aggiungi nuovo riferimento**.  
  
3.  Fare clic sulla scheda **Progetti**.  Selezionare WPFClock e fare clic su OK.  
  
4.  Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per aggiungere riferimenti.  
  
## <a name="hwndsource"></a>HwndSource  
 Successivamente, utilizziamo <xref:System.Windows.Interop.HwndSource> per rendere il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> l'aspetto di un oggetto HWND.  Aggiungere questo blocco di codice a un file C++:  
  
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
  
 Poiché si tratta di una parte estesa di codice possono essere necessarie alcune spiegazioni.  La prima parte contiene varie clausole che evitano di specificare il nome completo di tutte le chiamate:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 Quindi definita una funzione che crea il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il contenuto, inserisce un <xref:System.Windows.Interop.HwndSource> intorno a esso e restituisce l'oggetto HWND:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 Prima di tutto si crea un <xref:System.Windows.Interop.HwndSource>, i cui parametri sono analoghi a CreateWindow:  
  
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
  
 Quindi, creiamo il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classe contenuto chiamando il relativo costruttore:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 È quindi connettere la pagina per il <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 E nella riga finale, restituire l'oggetto HWND per il <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a>Posizionamento dell'oggetto HWND  
 Ora che avete un HWND che contiene il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio, è necessario inserire tale oggetto HWND all'interno di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra di dialogo.  Se si conosce la posizione in cui inserire l'oggetto HWND, è sufficiente passare le dimensioni e il percorso in cui il `GetHwnd` funzione definita in precedenza.  Tuttavia, si è usato un file di risorse per definire la finestra di dialogo perciò non si conosce esattamente la posizione degli oggetti HWND.  È possibile usare la [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor finestre per inserire un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] statico controllo in cui si desidera che l'orologio ("Insert clock here") e usarlo per posizionare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio.  
  
 Dove si gestisce WM_INITDIALOG, si utilizza `GetDlgItem` per recuperare l'oggetto HWND per il segnaposto STATIC:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 Vengono quindi calcolate le dimensioni e la posizione di tale segnaposto STATIC, così è possibile inserire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in tale posizione:  
  
 Rettangolo RECT;  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 Dopodiché si nasconde il segnaposto STATIC:  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 E creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in tale posizione:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Per rendere interessante l'esercitazione e per produrre un vero [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio, è necessario creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock a questo punto di controllo. È possibile eseguire questa operazione principalmente nel markup, con solo alcuni gestori eventi in code-behind. Poiché questa esercitazione sull'interoperatività e non sulla progettazione di controlli, il codice completo per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio viene fornito come un blocco di codice, senza istruzioni separate per la compilazione né significato di ciascuna parte. Modificare questo codice per variare l'aspetto o le funzionalità del controllo.  
  
 Questo è il markup:  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 Questo è il code-behind associato:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 Il risultato finale è il seguente:  
  
 ![Finestra di dialogo Proprietà data e ora](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")  
  
 Per confrontare il risultato finale al codice che ha generato questa schermata, vedere [esempio di interoperatività Clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.HwndSource>  
 [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Esempio di interoperatività con l'orologio Win32](https://go.microsoft.com/fwlink/?LinkID=160051)
