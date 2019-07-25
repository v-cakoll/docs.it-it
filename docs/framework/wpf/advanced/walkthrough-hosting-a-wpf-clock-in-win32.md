---
title: 'Procedura dettagliata: Hosting di un orologio WPF in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 27e1a2e88beeacf8c2cd98f61b11542ee2341e8f
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433969"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Procedura dettagliata: Hosting di un orologio WPF in Win32

Per inserire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all' [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] interno delle applicazioni <xref:System.Windows.Interop.HwndSource>, usare, che fornisce l'HWND che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contiene il contenuto. Innanzitutto si crea <xref:System.Windows.Interop.HwndSource>, assegnando parametri simili a CreateWindow. Si indica quindi al <xref:System.Windows.Interop.HwndSource> contenuto che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si desidera al suo interno. Infine, si ottiene l'elemento HWND da <xref:System.Windows.Interop.HwndSource>. In questa procedura dettagliata viene illustrato come creare un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] mista all'interno che reimplementa la finestra di dialogo **Proprietà data e ora** del sistema operativo.

## <a name="prerequisites"></a>Prerequisiti

Vedere l'interoperatività [di WPF e Win32](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Utilizzo dell'esercitazione

Questa esercitazione si concentra sui passaggi importanti per la produzione di un'applicazione di interoperatività. L'esercitazione è supportata da un esempio di interoperatività con [Clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051), ma tale esempio riflette il prodotto finale. Questa esercitazione illustra i passaggi come se si iniziasse con un progetto [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] esistente, ad esempio un progetto preesistente e si stesse aggiungendo un host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'applicazione. È possibile confrontare il prodotto finale con l'esempio di interoperatività con [Clock Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Procedura dettagliata di Windows Presentation Framework in Win32 (HwndSource)

Il grafico seguente illustra il prodotto finale previsto di questa esercitazione:

![Screenshot che mostra la finestra di dialogo Proprietà data e ora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Per ricreare questa finestra di dialogo è possibile C++ creare un progetto Win32 in Visual Studio e utilizzare l'editor finestre per creare gli elementi seguenti:

![Finestra di dialogo Proprietà data e ora ricreate](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

Non [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] è necessario usare per usare <xref:System.Windows.Interop.HwndSource>e non è necessario usare C++ per scrivere [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programmi, ma si tratta di un modo piuttosto comune per eseguire questa operazione e si presta bene a una spiegazione graduale dell'esercitazione.

È necessario eseguire cinque passaggi specifici per inserire un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio nella finestra di dialogo:

1. Consentire al [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]progetto di chiamare codice gestito (/CLR) modificando le impostazioni del progetto in. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]

2. Creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto <xref:System.Windows.Controls.Page> in una DLL separata.

3. Inserire l'oggetto <xref:System.Windows.Interop.HwndSource>all'interno di un oggetto. <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

4. Ottenere un HWND per <xref:System.Windows.Controls.Page> l'oggetto utilizzando la <xref:System.Windows.Interop.HwndSource.Handle%2A> proprietà.

5. Usare [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] per decidere dove posizionare il HWND all'interno dell'applicazione [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] più grande

## <a name="clr"></a>/clr

Il primo passaggio consiste nel trasformare questo [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] progetto non gestito in uno in grado di chiamare codice gestito. Si usa l'opzione del compilatore/CLR, che consente di collegare le DLL necessarie da usare e di modificare il metodo Main per l'uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Per abilitare l'utilizzo del codice gestito all'interno C++ del progetto: Fare clic con il pulsante destro del mouse sul progetto win32clock e scegliere **Proprietà**. Nella pagina delle proprietà **generale** (impostazione predefinita) modificare il supporto Common Language Runtime in `/clr`.

Aggiungere quindi i riferimenti alle DLL necessarie per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll e UIAutomationTypes. dll. (le istruzioni seguenti presuppongono che il sistema operativo sia installato nell'unità C:).

1. Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** e all'interno di tale finestra di dialogo:

2. Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** .

3. Fare clic su **Aggiungi nuovo riferimento**, fare clic sulla scheda Sfoglia, immettere C:\program files\reference assemblies\microsoft\framework\v3.0\PresentationCore.dll e fare clic su OK.

4. Ripeti per PresentationFramework. dll: C:\Programmi\Microsoft Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Ripeti per WindowsBase. dll: C:\Programmi\Microsoft Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Ripeti per UIAutomationTypes. dll: C:\Programmi\Microsoft Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Ripeti per UIAutomationProvider. dll: C:\Programmi\Microsoft Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Fare clic su **Aggiungi nuovo riferimento**, selezionare System. dll e fare clic su **OK**.

9. Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.

 Aggiungere `STAThreadAttribute` infine al metodo per l' `_tWinMain` uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Questo attributo indica al Common Language Runtime (CLR) che, quando inizializza Component Object Model (com), deve usare un modello di Apartment a thread singolo (sta), che è necessario per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).

## <a name="create-a-windows-presentation-framework-page"></a>Creare una pagina di Windows Presentation Framework

Successivamente, si crea una DLL che definisce un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]oggetto <xref:System.Windows.Controls.Page>. Spesso è più semplice creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> come applicazione autonoma e scrivere ed eseguire il debug della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte in questo modo. Al termine, il progetto può essere trasformato in una DLL facendo clic con il pulsante destro del mouse sul progetto, facendo clic su **Proprietà**, passando all'applicazione e modificando il tipo di output in libreria di classi di Windows.

Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto di dll può quindi essere combinato con [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] il progetto (una soluzione che contiene due progetti): fare clic con il pulsante destro del mouse sulla soluzione e scegliere **progetto Add\Existing**.

Per usare tale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dal progetto, è necessario aggiungere un riferimento:

1. Fare clic con il pulsante destro del mouse su progetto win32clock e selezionare **riferimenti...** .

2. Fare clic su **Aggiungi nuovo riferimento**.

3. Fare clic sulla scheda **Progetti**. Selezionare WPFClock e fare clic su OK.

4. Fare clic su **OK** per chiudere le pagine delle proprietà di win32clock per l'aggiunta di riferimenti.

## <a name="hwndsource"></a>HwndSource

A questo punto, <xref:System.Windows.Interop.HwndSource> usare per rendere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l' <xref:System.Windows.Controls.Page> aspetto di un HWND. Aggiungere questo blocco di codice a un file C++:

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

 Si definisce quindi una funzione che crea il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto, ne inserisce <xref:System.Windows.Interop.HwndSource> una e restituisce HWND:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Innanzitutto si crea un <xref:System.Windows.Interop.HwndSource>oggetto, i cui parametri sono simili a CreateWindow:

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

Si crea quindi la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classe Content chiamando il relativo costruttore:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

Si connette quindi la pagina al <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 Nella riga finale, restituire HWND per <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Posizionamento dell'oggetto HWND

Ora che è presente un HWND che contiene l' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] orologio, è necessario inserire tale HWND [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] nella finestra di dialogo. Se si conosce solo la posizione in cui inserire HWND, è sufficiente passare le dimensioni e la `GetHwnd` posizione alla funzione definita in precedenza. Tuttavia, si è usato un file di risorse per definire la finestra di dialogo perciò non si conosce esattamente la posizione degli oggetti HWND. È possibile utilizzare l' [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor finestre per inserire un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo statico nel punto in cui si desidera che il clock venga spostato ("Inserisci orologio") e utilizzarlo per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] posizionare il clock.

Quando si gestisce WM_INITDIALOG, si usa `GetDlgItem` per recuperare HWND per il segnaposto static:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

Quindi si calcolano le dimensioni e la posizione del segnaposto statico, in modo che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sia possibile inserire l'orologio in tale posizione:

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

E creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock HWND in tale percorso:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Per rendere interessante l'esercitazione e per produrre un Clock reale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , è necessario creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo clock a questo punto. È possibile eseguire questa operazione principalmente nel markup, con solo alcuni gestori eventi in code-behind. Poiché questa esercitazione riguarda l'interoperatività e non la progettazione dei controlli, il codice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] completo per l'orologio viene fornito qui come blocco di codice, senza istruzioni discrete per la compilazione o il significato di ogni parte. Modificare questo codice per variare l'aspetto o le funzionalità del controllo.

Questo è il markup:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

Questo è il code-behind associato:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

Il risultato finale è il seguente:

![Finestra di dialogo Proprietà data e ora risultato finale](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Per confrontare il risultato finale con il codice che ha prodotto questa schermata, vedere esempio di interoperatività di [Win32 Clock](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Esempio di interoperatività con l'orologio Win32](https://go.microsoft.com/fwlink/?LinkID=160051)
