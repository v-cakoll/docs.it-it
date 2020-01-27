---
title: 'Procedura dettagliata: ospitare un Clock WPF in Win32'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 79f79e42652ca51c409fabb12a572485ad734b35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744893"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a>Procedura dettagliata: ospitare un Clock WPF in Win32

Per inserire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno delle applicazioni Win32, utilizzare <xref:System.Windows.Interop.HwndSource>, che fornisce l'HWND che contiene il contenuto di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Innanzitutto si crea il <xref:System.Windows.Interop.HwndSource>, fornendo parametri simili a CreateWindow. Si dirà quindi al <xref:System.Windows.Interop.HwndSource> sul contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che si vuole al suo interno. Infine, si ottiene il HWND dal <xref:System.Windows.Interop.HwndSource>. In questa procedura dettagliata viene illustrato come creare una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mista all'interno di un'applicazione Win32 che implementa nuovamente la finestra di dialogo **Proprietà data e ora** del sistema operativo.

## <a name="prerequisites"></a>Prerequisiti

Vedere l' [interoperatività di WPF e Win32](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Come usare questa esercitazione

Questa esercitazione si concentra sui passaggi importanti per la produzione di un'applicazione di interoperatività. L'esercitazione è supportata da un esempio di [interoperatività con clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051), ma tale esempio riflette il prodotto finale. Questa esercitazione illustra i passaggi come se si iniziasse con un progetto Win32 esistente, ad esempio un progetto preesistente e si stesse aggiungendo una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitata all'applicazione. È possibile confrontare il prodotto finale con l' [esempio di interoperatività con clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Procedura dettagliata di Windows Presentation Framework in Win32 (HwndSource)

Il grafico seguente illustra il prodotto finale previsto di questa esercitazione:

![Screenshot che mostra la finestra di dialogo Proprietà data e ora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Per ricreare questa finestra di dialogo è possibile C++ creare un progetto Win32 in Visual Studio e utilizzare l'editor finestre per creare gli elementi seguenti:

![Finestra di dialogo Proprietà data e ora ricreate](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

Non è necessario usare Visual Studio per usare <xref:System.Windows.Interop.HwndSource>e non è necessario usare C++ per scrivere programmi Win32, ma si tratta di un modo piuttosto comune per eseguire questa operazione e si presta bene a una spiegazione graduale dell'esercitazione.

Per inserire un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock nella finestra di dialogo, è necessario eseguire cinque passaggi specifici:

1. Abilitare il progetto Win32 per chiamare il codice gestito ( **/CLR**) modificando le impostazioni del progetto in Visual Studio.

2. Creare una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in una DLL separata.

3. Inserire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> all'interno di un <xref:System.Windows.Interop.HwndSource>.

4. Ottenere un HWND per tale <xref:System.Windows.Controls.Page> utilizzando la proprietà <xref:System.Windows.Interop.HwndSource.Handle%2A>.

5. Utilizzare Win32 per decidere dove posizionare il HWND all'interno dell'applicazione Win32 di dimensioni maggiori

## <a name="clr"></a>/clr

Il primo passaggio consiste nel trasformare questo progetto Win32 non gestito in uno in grado di chiamare codice gestito. Si usa l'opzione del compilatore/CLR, che consente di collegare le DLL necessarie da usare e di modificare il metodo Main per l'uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Per abilitare l'uso del codice gestito all'interno C++ del progetto: fare clic con il pulsante destro del mouse sul progetto win32clock e scegliere **Proprietà**. Nella pagina delle proprietà **generale** (impostazione predefinita) modificare il supporto Common Language Runtime in `/clr`.

Aggiungere quindi i riferimenti alle DLL necessarie per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll e UIAutomationTypes. dll. (le istruzioni seguenti presuppongono che il sistema operativo sia installato nell'unità C:).

1. Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** e all'interno di tale finestra di dialogo:

2. Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** .

3. Fare clic su **Aggiungi nuovo riferimento**, fare clic sulla scheda Sfoglia, immettere C:\program files\reference assemblies\microsoft\framework\v3.0\PresentationCore.dll e fare clic su OK.

4. Ripetere l'operazione per PresentationFramework.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Ripetere l'operazione per WindowsBase.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Ripetere l'operazione per UIAutomationTypes.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Ripetere l'operazione per UIAutomationProvider.dll: C:\Programmi\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Fare clic su **Aggiungi nuovo riferimento**, selezionare System. dll e fare clic su **OK**.

9. Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.

 Infine, aggiungere il `STAThreadAttribute` al metodo `_tWinMain` per l'utilizzo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Questo attributo indica al Common Language Runtime (CLR) che, quando inizializza Component Object Model (COM), deve usare un modello di Apartment a thread singolo (STA), che è necessario per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).

## <a name="create-a-windows-presentation-framework-page"></a>Creare una pagina di Windows Presentation Framework

Successivamente, si crea una DLL che definisce una <xref:System.Windows.Controls.Page>di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Spesso è più semplice creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> come applicazione autonoma e scrivere ed eseguire il debug della parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in questo modo. Al termine, il progetto può essere trasformato in una DLL facendo clic con il pulsante destro del mouse sul progetto, facendo clic su **Proprietà**, passando all'applicazione e modificando il tipo di output in libreria di classi di Windows.

Il progetto di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll può quindi essere combinato con il progetto Win32 (una soluzione che contiene due progetti): fare clic con il pulsante destro del mouse sulla soluzione e selezionare **progetto Add\Existing**.

Per utilizzare tale DLL [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dal progetto Win32, è necessario aggiungere un riferimento:

1. Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** .

2. Fare clic su **Aggiungi nuovo riferimento**.

3. Fare clic sulla scheda **progetti** . Selezionare WPFClock, quindi fare clic su OK.

4. Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.

## <a name="hwndsource"></a>HwndSource

Usare quindi <xref:System.Windows.Interop.HwndSource> per rendere il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> simile a un HWND. Aggiungere questo blocco di codice a un file C++:

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

 Poiché si tratta di una parte estesa di codice possono essere necessarie alcune spiegazioni. La prima parte contiene varie clausole che evitano di specificare il nome completo di tutte le chiamate:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 Si definisce quindi una funzione che crea il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ne inserisce una <xref:System.Windows.Interop.HwndSource> e restituisce HWND:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Prima di tutto si crea un <xref:System.Windows.Interop.HwndSource>, i cui parametri sono simili a CreateWindow:

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

Si crea quindi la classe di contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiamando il relativo costruttore:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

Si connette quindi la pagina alla <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 Nella riga finale, restituire HWND per la <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Posizionamento dell'oggetto HWND

Ora che è presente un HWND che contiene il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, è necessario inserire tale HWND nella finestra di dialogo Win32. Se si conoscesse solo la posizione in cui inserire HWND, è sufficiente passare le dimensioni e la posizione alla funzione `GetHwnd` definita in precedenza. Tuttavia, si è usato un file di risorse per definire la finestra di dialogo perciò non si conosce esattamente la posizione degli oggetti HWND. È possibile usare l'editor finestre di Visual Studio per inserire un controllo statico Win32 in cui si vuole che l'orologio venga usato ("Inserisci orologio") e lo usi per posizionare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock.

Quando si gestiscono WM_INITDIALOG, si utilizza `GetDlgItem` per recuperare HWND per il segnaposto STATIC:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

Quindi si calcolano le dimensioni e la posizione del segnaposto statico, in modo che sia possibile inserire il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in tale posizione:

Rettangolo RECT;

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

Dopodiché si nasconde il segnaposto STATIC:

```cpp
ShowWindow(placeholder, SW_HIDE);
```

E creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND clock in tale percorso:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Per rendere interessante l'esercitazione e per produrre un vero e proprio [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, è necessario creare un controllo del clock [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a questo punto. È possibile eseguire questa operazione principalmente nel markup, con solo alcuni gestori eventi in code-behind. Poiché questa esercitazione riguarda l'interoperatività e non la progettazione dei controlli, il codice completo per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock viene fornito qui come blocco di codice, senza istruzioni discrete per la compilazione o il significato di ogni parte. Modificare questo codice per variare l'aspetto o le funzionalità del controllo.

Questo è il markup:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

Questo è il code-behind associato:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

Il risultato finale è il seguente:

![Finestra di dialogo Proprietà data e ora risultato finale](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Per confrontare il risultato finale con il codice che ha prodotto questa schermata, vedere [esempio di interoperatività di Win32 Clock](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Esempio di interoperatività con l'orologio Win32](https://go.microsoft.com/fwlink/?LinkID=160051)
