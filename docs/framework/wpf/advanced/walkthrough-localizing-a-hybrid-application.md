---
title: "Procedura dettagliata: Localizzazione di un'applicazione ibrida"
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 01530d4ae9779934948bbaff60fbbd392de6e701
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329297"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Procedura dettagliata: Localizzazione di un'applicazione ibrida

Questa procedura dettagliata mostra come localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi in un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-basato su un'applicazione ibrida.

Le attività illustrate nella procedura dettagliata sono le seguenti:

-   Creazione di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] progetto host.

-   Aggiunta di contenuto localizzabile.

-   Abilitazione della localizzazione.

-   Assegnazione di identificatori di risorsa.

-   Utilizzo dello strumento LocBaml per produrre un assembly satellite.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [localizzazione di un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=160015).

Al termine, sarà disponibile un'applicazione ibrida localizzata.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

-   Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Creazione del progetto host Windows Form

Il primo passaggio consiste nel creare il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicazione del progetto e aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento con contenuto da localizzare.

### <a name="to-create-the-host-project"></a>Per creare il progetto host

1. Creare un **applicazione WPF** progetto denominato `LocalizingWpfInWf`.  (**File** > **nuova** > **progetto** > **Visual C#** o **Visual Basic**   >  **Desktop classico** > **applicazione WPF**).

2. Aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> elemento denominato `SimpleControl` al progetto.

3. Usare la <xref:System.Windows.Forms.Integration.ElementHost> controllo di posizionarsi un `SimpleControl` elemento nel form. Per altre informazioni, vedere [Procedura dettagliata: Hosting di controlli compositi 3D di WPF in Windows Form](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).

## <a name="adding-localizable-content"></a>Aggiunta di contenuto localizzabile

Successivamente, si aggiungerà un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo etichetta e impostare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto dell'elemento in una stringa localizzabile.

### <a name="to-add-localizable-content"></a>Per aggiungere contenuto localizzabile

1. Nella **Esplora soluzioni**, fare doppio clic su **SimpleControl** aprirla nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

2. Impostare il contenuto del <xref:System.Windows.Controls.Button> controllo usando il codice seguente.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. Nelle **Esplora soluzioni**, fare doppio clic su **Form1** per aprirlo in Progettazione Windows Form.

4. Aprire il **casella degli strumenti** e fare doppio clic su **etichetta** per aggiungere un controllo etichetta al form. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hello"`.

5. Premere **F5** per compilare ed eseguire l'applicazione.

     Entrambi i `SimpleControl` elemento e il controllo etichetta il testo viene visualizzato **"Hello"**.

## <a name="enabling-localization"></a>Abilitazione della localizzazione

Progettazione Windows Form fornisce le impostazioni per abilitare la localizzazione in un assembly satellite.

### <a name="to-enable-localization"></a>Per abilitare la localizzazione

1. Nelle **Esplora soluzioni**, fare doppio clic su **Form1.cs** per aprirlo in Progettazione Windows Form.

2. Nel **delle proprietà** finestra, impostare il valore dell'oggetto del form **Localizable** proprietà `true`.

3. Nel **le proprietà** finestra, impostare il valore della **Language** proprietà **spagnolo (Spagna)**.

4. In Progettazione Windows Form selezionare il controllo etichetta.

5. Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà `"Hola"`.

     Un nuovo file di risorse denominato Form1.es-ES.resx verrà aggiunto al progetto.

6. Nelle **Esplora soluzioni**, fare doppio clic su **Form1.cs** e fare clic su **Visualizza codice** per aprirlo nell'Editor del codice.

7. Copiare il codice seguente nel `Form1` costruttore, prima di chiamare `InitializeComponent`.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. Nelle **Esplora soluzioni**, fare doppio clic su **LocalizingWpfInWf** e fare clic su **Scarica progetto**.

     Il nome del progetto viene etichettato **(non disponibile)**.

9. Fare doppio clic su **LocalizingWpfInWf**, fare clic su **Modifica LocalizingWpfInWf**.

     Il file di progetto verrà aperto nell'editor di codice.

10. Copiare la riga seguente nel primo `PropertyGroup` nel file di progetto.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Salvare e chiudere il file di progetto.

12. Nelle **Esplora soluzioni**, fare doppio clic su **LocalizingWpfInWf** e fare clic su **Ricarica progetto**.

## <a name="assigning-resource-identifiers"></a>Assegnazione di identificatori di risorsa

È possibile eseguire il mapping del contenuto localizzabile agli assembly di risorse usando identificatori di risorsa. L'applicazione MsBuild.exe assegna automaticamente gli identificatori di risorsa quando si specifica il `updateuid` opzione.

### <a name="to-assign-resource-identifiers"></a>Per assegnare identificatori di risorsa

1. Dal Menu Start, aprire il prompt dei comandi per gli sviluppatori per Visual Studio.

2. Per assegnare identificatori di risorsa al contenuto localizzabile, usare il comando seguente.

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. Nelle **Esplora soluzioni**, fare doppio clic su **SimpleControl** per aprirlo nell'Editor del codice. Si noterà che il `msbuild` comando è stato aggiunto il `Uid` attributo per tutti gli elementi. In tal modo si semplifica la localizzazione mediante l'assegnazione di identificatori di risorsa.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Premere **F6** per compilare la soluzione.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Utilizzo dello strumento LocBaml per produrre un assembly satellite

Il contenuto localizzato viene memorizzato in una risorsa sola *assembly satellite*. Usare lo strumento da riga di comando LocBaml.exe per produrre un assembly localizzato per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.

### <a name="to-produce-a-satellite-assembly"></a>Per produrre un assembly satellite

1. Copiare LocBaml.exe nella cartella obj\Debug del progetto. Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).

2. Nella finestra del prompt dei comandi usare il comando seguente per estrarre stringhe di risorsa in un file temporaneo.

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Aprire il file TEMP con Visual Studio o un altro editor di testo. Sostituire la stringa `"Hello"` con la relativa traduzione spagnola, `"Hola"`.

4. Salvare il file temp.csv.

5. Per generare il file di risorse localizzato, usare il comando seguente.

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     Il file LocalizingWpfInWf.g.es-ES.resources viene creato nella cartella obj\Debug.

6. Per compilare l'assembly satellite localizzato, usare il comando seguente.

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     Il file LocalizingWpfInWf.resources.dll viene creato nella cartella obj\Debug.

7. Copiare il file LocalizingWpfInWf.resources.dll nella cartella bin\Debug\es-ES del progetto. Sostituire il file esistente.

8. Eseguire LocalizingWpfInWf.exe, situato nella cartella bin\Debug del progetto. Non ricompilare l'applicazione altrimenti l'assembly satellite verrà sovrascritto.

     Nell'applicazione vengono visualizzate le stringhe localizzate invece delle stringhe in inglese.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Localizzare un'applicazione](how-to-localize-an-application.md)
- [Procedura dettagliata: Localizzazione di Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
