---
title: Livelli di rendering della grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- rendering graphics [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
ms.assetid: 08dd1606-02a2-4122-9351-c0afd2ec3a70
ms.openlocfilehash: 05847271cf82739a6a0b609771043c02a7ffc0e9
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291585"
---
# <a name="graphics-rendering-tiers"></a>Livelli di rendering della grafica
Un livello di rendering definisce un livello di prestazioni e funzionalità hardware grafiche per un dispositivo che esegue un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="graphics_hardware"></a>
## <a name="graphics-hardware"></a>Hardware grafico  
 Le funzionalità dell'hardware grafico che hanno effetto sui livelli di rendering sono:  
  
- **RAM video** La quantità di memoria video sull'hardware grafico determina le dimensioni e il numero di buffer che possono essere usati per la composizione della grafica.  
  
- **Pixel shader** Un pixel shader è una funzione di elaborazione grafica che calcola gli effetti sui singoli pixel. A seconda della risoluzione della grafica visualizzata, potrebbe essere necessario elaborare diversi milioni di pixel per ogni fotogramma visualizzato.  
  
- **Vertex shader** Un vertex shader è una funzione di elaborazione grafica che esegue operazioni matematiche sui dati dei vertici dell'oggetto.  
  
- **Supporto per più trame** Il supporto per più trame è la possibilità di applicare due o più trame distinte durante un'operazione di fusione su un oggetto grafico 3D. Il grado di supporto per più trame è determinato dal numero di unità a più trame nell'hardware grafico.  
  
<a name="rendering_tier_definitions"></a>
## <a name="rendering-tier-definitions"></a>Definizioni dei livelli di rendering  
 Le funzionalità dell'hardware grafico determinano la capacità di rendering di un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definisce tre livelli di rendering:  
  
- **Livello di rendering 0** Nessuna accelerazione hardware grafico. Tutte le funzionalità grafiche usano l'accelerazione software. Il livello di versione di DirectX è inferiore alla versione 9.0.The DirectX version level is less than version 9.0.  
  
- **Livello di rendering 1** Alcune funzionalità grafiche usano l'accelerazione hardware grafico. Il livello di versione di DirectX è maggiore o uguale alla versione 9.0.The DirectX version level is greater than or equal to version 9.0.  
  
- **Livello di rendering 2** La maggior parte delle funzionalità grafiche usa l'accelerazione hardware grafico. Il livello di versione di DirectX è maggiore o uguale alla versione 9.0.The DirectX version level is greater than or equal to version 9.0.  
  
 La <xref:System.Windows.Media.RenderCapability.Tier%2A?displayProperty=nameWithType> proprietà consente di recuperare il livello di rendering in fase di esecuzione dell'applicazione. Il livello di rendering consente di determinare se il dispositivo supporta determinate funzionalità grafiche con accelerazione hardware. L'applicazione può quindi usare percorsi di codice diversi in fase di esecuzione a seconda del livello di rendering supportato dal dispositivo.  
  
### <a name="rendering-tier-0"></a>Livello di rendering 0  
 Il valore 0 del livello di rendering indica che l'accelerazione hardware grafico non è disponibile per l'applicazione sul dispositivo. A questo livello, si deve presupporre che il rendering tutta la grafica verrà eseguito dal software senza accelerazione hardware. La funzionalità di questo livello corrisponde a una versione di DirectX inferiore alla 9.0.This tier's functionality corresponds to a DirectX version that is less than 9.0.  
  
### <a name="rendering-tier-1-and-rendering-tier-2"></a>Livello di rendering 1 e livello di rendering 2
  
> [!NOTE]
> A partire da .NET Framework 4.NET Framework 4, il rendering di livello 1 è stato ridefinito per includere solo l'hardware grafico che supporta DirectX 9.0 o versione successiva. L'hardware grafico che supporta DirectX 7 o 8 è ora definito come livello di rendering 0.  
  
 Il valore 1 o 2 del livello di rendering indica che la maggior parte delle funzionalità grafiche di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] userà l'accelerazione hardware se le risorse di sistema necessarie sono disponibili e non sono state esaurite. Corrisponde a una versione di DirectX maggiore o uguale a 9.0.  
  
 La tabella seguente illustra le differenze dei requisiti di hardware grafico tra il livello di rendering 1 e livello di rendering 2:  
  
|Funzionalità|Livello 1|Livello 2|  
|-------------|------------|------------|  
|Versione DirectX|Deve essere superiore o uguale alla 9.0.|Deve essere superiore o uguale alla 9.0.|  
|RAM video|Deve essere maggiore o uguale a 60 MB.|Deve essere maggiore o uguale a 120 MB.|  
|Pixel shader|Il livello della versione deve essere superiore o uguale alla 2.0.|Il livello della versione deve essere superiore o uguale alla 2.0.|  
|Vertex shader|Nessun requisito.|Il livello della versione deve essere superiore o uguale alla 2.0.|  
|Unità a più trame|Nessun requisito.|Il numero di unità deve essere superiore o uguale a 4.|  
  
 Le funzionalità e capacità seguenti sono con accelerazione hardware per il livello di rendering 1 e livello di rendering 2:  
  
|Funzionalità|Note|  
|-------------|-----------|  
|Rendering 2D|È supportata la maggior parte del rendering 2D.|  
|Rasterizzazione 3D|È supportata la maggior parte delle rasterizzazioni 3D.|  
|Filtro anisotropico 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] prova a usare il filtro anisotropico quando viene eseguito il rendering del contenuto 3D. Il filtro anisotropico consente di migliorare la qualità delle trame di un'immagine su superfici lontane e molto inclinate rispetto alla fotocamera.|  
|Mapping MIP 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] prova a usare il mapping MIP quando viene eseguito il rendering del contenuto 3D. Il mapping MIP migliora la qualità del rendering delle trame <xref:System.Windows.Controls.Viewport3D>quando una trama occupa un campo visivo più piccolo in un oggetto .|  
|Sfumature radiali|Sebbene sia supportato, evitare l'utilizzo di su oggetti di <xref:System.Windows.Media.RadialGradientBrush> grandi dimensioni.|  
|Calcoli per l'illuminazione 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue l'illuminazione per vertice, in cui l'intensità della luce deve essere calcolata in ogni vertice per ogni materiale applicato a un mesh.|  
|Rendering del testo|Il rendering dei font subpixel utilizza pixel shader disponibili sull'hardware grafico.|  
  
 Le funzionalità e capacità seguenti sono con accelerazione hardware solo per il livello di rendering 2:  
  
|Funzionalità|Note|  
|-------------|-----------|  
|Anti-aliasing 3D|L'anti-aliasing 3D è supportato solo nei sistemi operativi che supportano Windows Display Driver Model (WDDM), ad esempio Windows Vista e Windows 7.|  
  
 Le funzionalità e capacità seguenti sono **senza** accelerazione hardware:  
  
|Funzionalità|Note|  
|-------------|-----------|  
|Contenuti stampati|Il rendering di tutto il contenuto stampato viene eseguito con la pipeline software [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Contenuto rasterizzato che utilizza<xref:System.Windows.Media.Imaging.RenderTargetBitmap>|Qualsiasi contenuto sottoposto <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>rendering utilizzando il metodo di .|  
|Contenuti affiancati che utilizzano<xref:System.Windows.Media.TileBrush>|Qualsiasi contenuto affiancato <xref:System.Windows.Media.TileBrush.TileMode%2A> in cui <xref:System.Windows.Media.TileBrush> la <xref:System.Windows.Media.TileMode.Tile>proprietà dell'oggetto è impostato su .|  
|Superfici che superano le dimensioni massime della trama dell'hardware grafico|Per la maggior parte dell'hardware grafico, le superfici di grandi dimensioni sono pari a 2048x2048 o 4096x4096 pixel.|  
|Qualsiasi operazione il cui requisito per la RAM video supera la memoria dell'hardware grafico|È possibile monitorare l'utilizzo della RAM video dell'applicazione usando lo strumento Perforator incluso nella [famiglia di prodotti per l'analisi delle prestazioni WPF](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100)) in Windows SDK.|  
|Finestre a livelli|Le finestre a livelli consentono alle applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di eseguire il rendering del contenuto sullo schermo in una finestra non rettangolare. Nei sistemi operativi che supportano Windows Display Driver Model (WDDM), ad esempio Windows Vista e Windows 7, le finestre sovrapposte sono con accelerazione dell'hardware. In altri sistemi, ad esempio Windows XP, il rendering delle finestre sovrapposte viene eseguito tramite software senza accelerazione hardware.<br /><br /> È possibile abilitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le finestre <xref:System.Windows.Window> sovrapposte impostando le seguenti proprietà:<br /><br /> -   <xref:System.Windows.Window.WindowStyle%2A> = <xref:System.Windows.WindowStyle.None><br />-   <xref:System.Windows.Window.AllowsTransparency%2A> = `true`<br />-   <xref:System.Windows.Controls.Control.Background%2A> = <xref:System.Windows.Media.Brushes.Transparent%2A>|  
  
<a name="other_resources"></a>
## <a name="other-resources"></a>Risorse aggiuntive  
 Le risorse seguenti consentono di analizzare le caratteristiche delle prestazioni dell'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="graphics-rendering-registry-settings"></a>Impostazioni del Registro di sistema per il rendering della grafica  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce quattro impostazioni del Registro di sistema per controllare il rendering [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|**Opzione per la disabilitazione dell'accelerazione hardware**|Specifica se l'accelerazione hardware deve essere abilitata.|  
|**Valore massimo di multicampionamento**|Specifica il grado di campionamento multiplo per l'antialiasing del contenuto 3D.|  
|**Impostazione Data driver video necessaria**|Specifica se il sistema disabilita l'accelerazione hardware per i driver rilasciati prima di novembre 2004.|  
|**Opzione per l'uso di unità di rasterizzazione dei riferimenti**|Specifica se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deve usare l'unità di rasterizzazione dei riferimenti.|  
  
 A queste impostazioni è possibile accedere tramite qualsiasi utilità di configurazione esterna che possa fare riferimento alle impostazioni del Registro di sistema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste impostazioni possono anche essere create o modificate accedendo direttamente ai valori utilizzando l'Editor del Registro di sistema di Windows. Per altre informazioni, vedere [Impostazioni del Registro di sistema per il rendering della grafica](../graphics-multimedia/graphics-rendering-registry-settings.md).  
  
### <a name="wpf-performance-profiling-tools"></a>Strumenti per la profilatura delle prestazioni WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include una suite di strumenti per la profilatura delle prestazioni che consentono di analizzare il comportamento dell'applicazione in fase di esecuzione e di determinare i tipi di ottimizzazioni delle prestazioni che è possibile applicare. Nella tabella seguente sono elencati gli strumenti di profilatura delle prestazioni inclusi nello strumento Windows SDK, WPF Performance Suite:  
  
|Strumento|Descrizione|  
|----------|-----------------|  
|Perforator|Da usare per l'analisi del comportamento di rendering.|  
|Visual Profiler|Da usare per la profilatura dell'uso dei servizi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], come gestione del layout e degli eventi, per gli elementi nella struttura ad albero visuale.|  
  
 WPF Performance Suite offre una visualizzazione grafica avanzata dei dati sulle prestazioni. Per altre informazioni sugli strumenti per le prestazioni WPF, vedere [Famiglia di prodotti per l'analisi delle prestazioni WPF](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100)).  
  
### <a name="directx-diagnostic-tool"></a>Strumento di diagnostica DirectX  
 Lo strumento di diagnostica DirectX, Dxdiag.exe, è progettato per facilitare la risoluzione dei problemi relativi a DirectX. La cartella di installazione predefinita per lo Strumento di diagnostica DirectX è:  
  
 `~\Windows\System32`  
  
 Quando si esegue lo Strumento di diagnostica DirectX, la finestra principale contiene un set di schede che consentono di visualizzare e diagnosticare le informazioni relative a DirectX. Ad esempio, la scheda **Sistema** fornisce informazioni di sistema sul computer e specifica la versione di DirectX installata nel computer.  
  
 ![Schermata: Strumento di diagnostica DirectX](./media/directxdiagnostictool-01.png "DirectXDiagnosticTool_01")  
Finestra principale dello strumento di diagnostica DirectX  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.RenderCapability>
- <xref:System.Windows.Media.RenderOptions>
- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Famiglia di prodotti per l'analisi delle prestazioni WPF](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100))
- [Impostazioni del Registro di sistema per il rendering della grafica](../graphics-multimedia/graphics-rendering-registry-settings.md)
- [Suggerimenti sulle animazioni](../graphics-multimedia/animation-tips-and-tricks.md)
