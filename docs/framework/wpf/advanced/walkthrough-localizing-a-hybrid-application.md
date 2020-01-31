---
title: "Procedura dettagliata: localizzazione di un'applicazione ibrida"
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: b406d539f2446824027e9462c8ecbe20c18cfb27
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794132"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Procedura dettagliata: localizzazione di un'applicazione ibrida

Questa procedura dettagliata illustra come localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi in un'applicazione ibrida basata su Windows Forms.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto host Windows Forms.

- Aggiunta di contenuto localizzabile.

- Abilitazione della localizzazione.

- Assegnazione di identificatori di risorsa.

- Utilizzo dello strumento LocBaml per produrre un assembly satellite.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [esempio di localizzazione di un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=160015).

Al termine, sarà disponibile un'applicazione ibrida localizzata.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Creazione del progetto host Windows Form

Il primo passaggio consiste nel creare il progetto Windows Forms Application e aggiungere un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con contenuto che verrà localizzato.

### <a name="to-create-the-host-project"></a>Per creare il progetto host

1. Creare un progetto di **applicazione WPF** denominato `LocalizingWpfInWf`.  (**File** > **nuovo** > **progetto** > **Visual C#**  o **Visual Basic** > **desktop classico** > **applicazione WPF**).

2. Aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]elemento <xref:System.Windows.Controls.UserControl> chiamato `SimpleControl` al progetto.

3. Utilizzare il controllo <xref:System.Windows.Forms.Integration.ElementHost> per inserire un elemento `SimpleControl` nel form. Per ulteriori informazioni, vedere [procedura dettagliata: hosting di un controllo composito 3D WPF in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).

## <a name="adding-localizable-content"></a>Aggiunta di contenuto localizzabile

Successivamente, si aggiungerà un controllo Label Windows Forms e si imposterà il contenuto dell'elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] su una stringa localizzabile.

### <a name="to-add-localizable-content"></a>Per aggiungere contenuto localizzabile

1. In **Esplora soluzioni**fare doppio clic su **SimpleControl. XAML** per aprirlo in WPF Designer.

2. Impostare il contenuto del controllo <xref:System.Windows.Controls.Button> usando il codice seguente.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. In **Esplora soluzioni**fare doppio clic su **Form1** per aprirlo nella progettazione Windows Form.

4. Aprire la **casella degli strumenti** e fare doppio clic su **etichetta** per aggiungere un controllo etichetta al modulo. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hello"`.

5. Premere **F5** per compilare ed eseguire l'applicazione.

     Sia l'elemento `SimpleControl` che il controllo Label visualizzano il testo **"Hello"** .

## <a name="enabling-localization"></a>Abilitazione della localizzazione

Progettazione Windows Form fornisce le impostazioni per abilitare la localizzazione in un assembly satellite.

### <a name="to-enable-localization"></a>Per abilitare la localizzazione

1. In **Esplora soluzioni**fare doppio clic su **Form1.cs** per aprirlo nella progettazione Windows Form.

2. Nella finestra **Proprietà** impostare il valore della proprietà **localizzabile** del modulo su `true`.

3. Nella finestra **Proprietà** impostare il valore della proprietà **Language** su **spagnolo (Spagna)** .

4. In Progettazione Windows Form selezionare il controllo etichetta.

5. Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hola"`.

     Un nuovo file di risorse denominato Form1.es-ES.resx verrà aggiunto al progetto.

6. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Form1.cs** e scegliere **Visualizza codice** per aprirlo nell'editor di codice.

7. Copiare il codice seguente nel costruttore `Form1`, prima della chiamata a `InitializeComponent`.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **LocalizingWpfInWf** e scegliere **Scarica progetto**.

     Il nome del progetto è contrassegnato come non **disponibile**.

9. Fare clic con il pulsante destro del mouse su **LocalizingWpfInWf**e scegliere **Modifica LocalizingWpfInWf. csproj**.

     Il file di progetto verrà aperto nell'editor di codice.

10. Copiare la riga seguente nella prima `PropertyGroup` nel file di progetto.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Salvare e chiudere il file di progetto.

12. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **LocalizingWpfInWf** e scegliere **Ricarica progetto**.

## <a name="assigning-resource-identifiers"></a>Assegnazione di identificatori di risorsa

È possibile eseguire il mapping del contenuto localizzabile agli assembly di risorse usando identificatori di risorsa. Quando si specifica l'opzione `updateuid`, l'applicazione MsBuild. exe assegna automaticamente gli identificatori di risorsa.

### <a name="to-assign-resource-identifiers"></a>Per assegnare identificatori di risorsa

1. Dal menu Start aprire il Prompt dei comandi per gli sviluppatori per Visual Studio.

2. Per assegnare identificatori di risorsa al contenuto localizzabile, usare il comando seguente.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. In **Esplora soluzioni**fare doppio clic su **SimpleControl. XAML** per aprirlo nell'editor di codice. Si noterà che il comando `msbuild` ha aggiunto l'attributo `Uid` a tutti gli elementi. In tal modo si semplifica la localizzazione mediante l'assegnazione di identificatori di risorsa.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Premere **F6** per compilare la soluzione.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Utilizzo dello strumento LocBaml per produrre un assembly satellite

Il contenuto localizzato viene archiviato in un *assembly satellite*di sole risorse. Utilizzare lo strumento da riga di comando LocBaml. exe per generare un assembly localizzato per il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="to-produce-a-satellite-assembly"></a>Per produrre un assembly satellite

1. Copiare LocBaml.exe nella cartella obj\Debug del progetto. Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).

2. Nella finestra del prompt dei comandi usare il comando seguente per estrarre stringhe di risorsa in un file temporaneo.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Aprire il file Temp. csv con Visual Studio o un altro editor di testo. Sostituire la stringa `"Hello"` con la relativa traduzione spagnola, `"Hola"`.

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
- [Procedura dettagliata: localizzazione di Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
