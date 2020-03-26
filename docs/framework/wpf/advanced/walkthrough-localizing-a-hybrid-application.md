---
title: "Procedura dettagliata: Localizzazione di un'applicazione ibrida"
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111114"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Procedura dettagliata: Localizzazione di un'applicazione ibrida

In questa procedura dettagliata [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene illustrato come localizzare gli elementi in un'applicazione ibrida basata su Windows Form.This walkthrough shows you how to localize elements in a Windows Forms-based hybrid application.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto host Windows Form.

- Aggiunta di contenuto localizzabile.

- Abilitazione della localizzazione.

- Assegnazione di identificatori di risorsa.

- Utilizzo dello strumento LocBaml per produrre un assembly satellite.

Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Localizzazione di un esempio](https://go.microsoft.com/fwlink/?LinkID=160015)di applicazione ibrida .

Al termine, sarà disponibile un'applicazione ibrida localizzata.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Creazione del progetto host Windows Form

Il primo passaggio consiste nel creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto di applicazione Windows Form e aggiungere un elemento con contenuto che verrà localizzato.

### <a name="to-create-the-host-project"></a>Per creare il progetto host

1. Creare un progetto `LocalizingWpfInWf`di app **WPF** denominato .  (**File** > **Nuovo** > **progetto** > Visual**Cè** o Visual **Basic** > Classic**Desktop** > WPF**Application**).

2. Aggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> un `SimpleControl` elemento chiamato al progetto.

3. Utilizzare <xref:System.Windows.Forms.Integration.ElementHost> il controllo `SimpleControl` per inserire un elemento nel form. Per altre informazioni, vedere [Procedura dettagliata: hosting di un controllo composito WPF 3D in Windows Form.For more information, see Walkthrough: Hosting a 3D WPF Composite Control in Windows Forms.](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)

## <a name="adding-localizable-content"></a>Aggiunta di contenuto localizzabile

Successivamente, si aggiungerà un controllo etichetta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Form e si imposterà il contenuto dell'elemento su una stringa localizzabile.

### <a name="to-add-localizable-content"></a>Per aggiungere contenuto localizzabile

1. In **Esplora soluzioni**fare doppio clic su **SimpleControl.xaml** per aprirlo in Progettazione WPF.

2. Impostare il <xref:System.Windows.Controls.Button> contenuto del controllo utilizzando il codice seguente.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. In **Esplora soluzioni**fare doppio clic su **Form1** per aprirlo in Progettazione Windows Form.

4. Aprire la **Casella degli strumenti** e fare doppio clic su **Etichetta** per aggiungere un controllo etichetta al form. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hello"`.

5. Premere **F5** per compilare ed eseguire l'applicazione.

     Sia `SimpleControl` l'elemento che il controllo etichetta visualizzano il testo **"Hello".**

## <a name="enabling-localization"></a>Abilitazione della localizzazione

Progettazione Windows Form fornisce le impostazioni per abilitare la localizzazione in un assembly satellite.

### <a name="to-enable-localization"></a>Per abilitare la localizzazione

1. In **Esplora soluzioni**fare doppio clic su **Form1.cs** per aprirla in Progettazione Windows Form.

2. Nella finestra **Proprietà** impostare il valore della proprietà **Localizable** del form su `true`.

3. Nella finestra **Proprietà** impostare il valore della proprietà **Language** su **Spagnolo (Spagna)**.

4. In Progettazione Windows Form selezionare il controllo etichetta.

5. Nella finestra **Proprietà** impostare il <xref:System.Windows.Forms.Control.Text%2A> valore `"Hola"`della proprietà su .

     Un nuovo file di risorse denominato Form1.es-ES.resx verrà aggiunto al progetto.

6. In **Esplora soluzioni**fare clic con il pulsante destro del mouse **su Form1.cs** e scegliere Visualizza **codice** per aprirlo nell'editor di codice.

7. Copiare il codice `Form1` seguente nel costruttore, prima della chiamata a `InitializeComponent`.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **LocalizingWpfInWf** e scegliere **Scarica progetto**.

     Il nome del progetto è etichettato **(non disponibile).**

9. Fare clic con il pulsante destro del mouse su **LocalizingWpfInWf**e **scegliere Modifica LocalizingWpfInWf.csproj**.

     Il file di progetto verrà aperto nell'editor di codice.

10. Copiare la riga `PropertyGroup` seguente nella prima nel file di progetto.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Salvare e chiudere il file di progetto.

12. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **LocalizingWpfInWf** e scegliere **Ricarica progetto**.

## <a name="assigning-resource-identifiers"></a>Assegnazione di identificatori di risorsa

È possibile eseguire il mapping del contenuto localizzabile agli assembly di risorse usando identificatori di risorsa. L'applicazione MsBuild.exe assegna automaticamente gli identificatori di risorsa quando si specifica l'opzione. `updateuid`

### <a name="to-assign-resource-identifiers"></a>Per assegnare identificatori di risorsa

1. Dal menu Start aprire il prompt dei comandi per gli sviluppatori per Visual Studio.From the Start Menu, open the Developer Command Prompt for Visual Studio.

2. Per assegnare identificatori di risorsa al contenuto localizzabile, usare il comando seguente.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. In **Esplora soluzioni**fare doppio clic su **SimpleControl.xaml** per aprirlo nell'editor di codice. Si noterà `msbuild` che il `Uid` comando ha aggiunto l'attributo a tutti gli elementi. In tal modo si semplifica la localizzazione mediante l'assegnazione di identificatori di risorsa.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Premere **F6** per compilare la soluzione.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Utilizzo dello strumento LocBaml per produrre un assembly satellite

Il contenuto localizzato viene archiviato in un *assembly satellite*di sole risorse. Utilizzare lo strumento da riga di comando LocBaml.exe per produrre un assembly localizzato per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.

### <a name="to-produce-a-satellite-assembly"></a>Per produrre un assembly satellite

1. Copiare LocBaml.exe nella cartella obj\Debug del progetto. Per ulteriori informazioni, vedere [Localizzare un'applicazione](how-to-localize-an-application.md).

2. Nella finestra del prompt dei comandi usare il comando seguente per estrarre stringhe di risorsa in un file temporaneo.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Aprire il file temp.csv con Visual Studio o un altro editor di testo. Sostituire la `"Hello"` stringa con `"Hola"`la relativa traduzione in spagnolo, .

4. Salvare il file temp.csv.

5. Per generare il file di risorse localizzato, usare il comando seguente.

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     Il file LocalizingWpfInWf.g.es-ES.resources viene creato nella cartella obj\Debug.

6. Per compilare l'assembly satellite localizzato, usare il comando seguente.

    ```console
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
- [Procedura dettagliata: localizzazione di Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
