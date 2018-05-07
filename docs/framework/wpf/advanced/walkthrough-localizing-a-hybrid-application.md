---
title: "Procedura dettagliata: localizzazione di un'applicazione ibrida"
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 010c8f75a1151f5606be5ffa63d60fca364bdb59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Procedura dettagliata: localizzazione di un'applicazione ibrida
Questa procedura dettagliata viene illustrato come localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi in un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-basato su un'applicazione ibrida.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] progetto host.  
  
-   Aggiunta di contenuto localizzabile.  
  
-   Abilitazione della localizzazione.  
  
-   Assegnazione di identificatori di risorsa.  
  
-   Utilizzo dello strumento LocBaml per produrre un assembly satellite.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [localizzazione di un'applicazione ibrida](http://go.microsoft.com/fwlink/?LinkID=160015).  
  
 Al termine, sarà disponibile un'applicazione ibrida localizzata.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-windows-forms-host-project"></a>Creazione del progetto host Windows Form  
 Il primo passaggio consiste nella creazione di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicazione del progetto e aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento con contenuto da localizzare.  
  
#### <a name="to-create-the-host-project"></a>Per creare il progetto host  
  
1.  Creare un progetto di applicazione WPF denominato `LocalizingWpfInWf`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> elemento denominato `SimpleControl` al progetto.  
  
3.  Utilizzare il <xref:System.Windows.Forms.Integration.ElementHost> controllo per inserire un `SimpleControl` elemento del form. Per ulteriori informazioni, vedere [procedura dettagliata: Hosting di un controllo composito WPF 3D in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).  
  
## <a name="adding-localizable-content"></a>Aggiunta di contenuto localizzabile  
 Successivamente, si aggiungerà un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo etichetta e impostare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto dell'elemento da una stringa localizzabile.  
  
#### <a name="to-add-localizable-content"></a>Per aggiungere contenuto localizzabile  
  
1.  In Esplora soluzioni fare doppio clic su **SimpleControl. XAML** per aprirlo nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Impostare il contenuto del <xref:System.Windows.Controls.Button> controllare tramite il codice seguente.  
  
     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  In Esplora soluzioni fare doppio clic su **Form1** per aprirlo in Progettazione Windows Form.  
  
4.  Aprire la casella degli strumenti e fare doppio clic su **etichetta** per aggiungere un controllo etichetta al form. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hello"`.  
  
5.  Premere F5 per compilare ed eseguire l'applicazione.  
  
     Entrambi i `SimpleControl` elemento e il controllo etichetta visualizzare il testo **"Hello"**.  
  
## <a name="enabling-localization"></a>Abilitazione della localizzazione  
 Progettazione Windows Form fornisce le impostazioni per abilitare la localizzazione in un assembly satellite.  
  
#### <a name="to-enable-localization"></a>Per abilitare la localizzazione  
  
1.  In Esplora soluzioni fare doppio clic su **Form1. cs** per aprirlo in Progettazione Windows Form.  
  
2.  Nella finestra Proprietà impostare il valore nel formato **Localizable** proprietà `true`.  
  
3.  Nella finestra Proprietà impostare il valore della **Language** proprietà **spagnolo (Spagna)**.  
  
4.  In Progettazione Windows Form selezionare il controllo etichetta.  
  
5.  Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà `"Hola"`.  
  
     Un nuovo file di risorse denominato Form1.es-ES.resx verrà aggiunto al progetto.  
  
6.  In Esplora soluzioni fare doppio clic su **Form1. cs** e fare clic su **Visualizza codice** per aprirlo nell'Editor di codice.  
  
7.  Copiare il codice seguente nel `Form1` costruttore, prima di chiamare `InitializeComponent`.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  In Esplora soluzioni fare doppio clic su **LocalizingWpfInWf** e fare clic su **Scarica progetto**.  
  
     Il nome del progetto con l'etichetta **(non disponibile)**.  
  
9. Fare doppio clic su **LocalizingWpfInWf**, fare clic su **Modifica LocalizingWpfInWf**.  
  
     Il file di progetto verrà aperto nell'editor di codice.  
  
10. Copiare la riga seguente nel primo `PropertyGroup` nel file di progetto.  
  
    ```xml  
    <UICulture>en-US</UICulture>   
    ```  
  
11. Salvare e chiudere il file di progetto.  
  
12. In Esplora soluzioni fare doppio clic su **LocalizingWpfInWf** e fare clic su **Ricarica progetto**.  
  
## <a name="assigning-resource-identifiers"></a>Assegnazione di identificatori di risorsa  
 È possibile eseguire il mapping del contenuto localizzabile agli assembly di risorse usando identificatori di risorsa. L'applicazione di MsBuild.exe assegna automaticamente identificatori di risorsa quando si specifica il `updateuid` opzione.  
  
#### <a name="to-assign-resource-identifiers"></a>Per assegnare identificatori di risorsa  
  
1.  Dal Menu Start, aprire il prompt dei comandi di Visual Studio.  
  
2.  Per assegnare identificatori di risorsa al contenuto localizzabile, usare il comando seguente.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  In Esplora soluzioni fare doppio clic su **SimpleControl. XAML** per aprirlo nell'Editor di codice. Si noterà che il `msbuild` comando che ha aggiunto la `Uid` attributo per tutti gli elementi. In tal modo si semplifica la localizzazione mediante l'assegnazione di identificatori di risorsa.  
  
     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  Premere F6 per compilare la soluzione.  
  
## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Utilizzo dello strumento LocBaml per produrre un assembly satellite  
 Il contenuto localizzato viene archiviato in una risorsa sola *assembly satellite*. Utilizzare lo strumento da riga di comando LocBaml.exe per produrre un assembly localizzato per le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.  
  
#### <a name="to-produce-a-satellite-assembly"></a>Per produrre un assembly satellite  
  
1.  Copiare LocBaml.exe nella cartella obj\Debug del progetto. Per ulteriori informazioni, vedere [localizzazione di un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
2.  Nella finestra del prompt dei comandi usare il comando seguente per estrarre stringhe di risorsa in un file temporaneo.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Aprire il file TEMP. csv con Visual Studio o un altro editor di testo. Sostituire la stringa `"Hello"` con la relativa traduzione spagnola, `"Hola"`.  
  
4.  Salvare il file temp.csv.  
  
5.  Per generare il file di risorse localizzato, usare il comando seguente.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     Il file LocalizingWpfInWf.g.es-ES.resources viene creato nella cartella obj\Debug.  
  
6.  Per compilare l'assembly satellite localizzato, usare il comando seguente.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     Il file LocalizingWpfInWf.resources.dll viene creato nella cartella obj\Debug.  
  
7.  Copiare il file LocalizingWpfInWf.resources.dll nella cartella bin\Debug\es-ES del progetto. Sostituire il file esistente.  
  
8.  Eseguire LocalizingWpfInWf.exe, situato nella cartella bin\Debug del progetto. Non ricompilare l'applicazione altrimenti l'assembly satellite verrà sovrascritto.  
  
     Nell'applicazione vengono visualizzate le stringhe localizzate invece delle stringhe in inglese.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Localizzare un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)  
 [Procedura dettagliata: Localizzazione di Windows Form](http://msdn.microsoft.com/library/9a96220d-a19b-4de0-9f48-01e5d82679e5)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
