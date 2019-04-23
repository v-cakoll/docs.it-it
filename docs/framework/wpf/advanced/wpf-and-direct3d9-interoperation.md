---
title: Interoperatività di WPF e Direct3D9
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 38f5eb36e3e5c055c5a354a67e15cde8049a2967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307730"
---
# <a name="wpf-and-direct3d9-interoperation"></a>Interoperatività di WPF e Direct3D9
È possibile includere contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). In questo argomento viene descritto come creare contenuto Direct3D9 in modo che interagisce in modo efficiente con WPF.  
  
> [!NOTE]
>  Quando si usa contenuto Direct3D9 in WPF, è necessario anche considerare le prestazioni. Per altre informazioni su come ottimizzare le prestazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità di WPF e Direct3D9](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Buffer di visualizzazione  
 Il <xref:System.Windows.Interop.D3DImage> classe gestisce due buffer di visualizzazione, che vengono chiamati i *buffer nascosto* e il *front buffer*. Il buffer è la superficie Direct3D9. Le modifiche al buffer nascosto vengono copiate il front-buffer quando si chiama il <xref:System.Windows.Interop.D3DImage.Unlock%2A> (metodo).  
  
 Nella figura seguente mostra la relazione tra il front-buffer e il buffer nascosto.  
  
 ![Buffer di visualizzazione D3DImage](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Creazione di un dispositivo Direct3D9  
 Per eseguire il rendering Direct3D9 contenuto, è necessario creare un dispositivo Direct3D9. Sono presenti due oggetti Direct3D9 che è possibile usare per creare un dispositivo `IDirect3D9` e `IDirect3D9Ex`. Usare questi oggetti per creare `IDirect3DDevice9` e `IDirect3DDevice9Ex` dispositivi, rispettivamente.  
  
 Creare un dispositivo chiamando uno dei metodi seguenti.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 In Windows Vista o versioni successive del sistema operativo, usare il `Direct3DCreate9Ex` metodo con una visualizzazione che è configurata per utilizzare Windows Visualizza Driver Model (WDDM). Usare il `Direct3DCreate9` metodo su qualsiasi altra piattaforma.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Disponibilità del metodo Direct3DCreate9Ex  
 D3d9. dll ha il `Direct3DCreate9Ex` metodo solo in Windows Vista o versioni successive del sistema operativo. Se si collega direttamente la funzione in Windows XP, l'applicazione non riesce a caricare. Per determinare se il `Direct3DCreate9Ex` metodo è supportato, caricare la DLL e cercare l'indirizzo proc. Il codice seguente illustra come eseguire test per il `Direct3DCreate9Ex` (metodo). Per un esempio di codice completo, vedere [procedura dettagliata: Creazione di contenuto Direct3D9 per l'Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>Creazione di un HWND  
 Creazione di un dispositivo richiede un oggetto HWND. In generale, si crea un HWND fittizio Direct3D9 da utilizzare. Esempio di codice seguente viene illustrato come creare un oggetto HWND fittizio.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Parametri presenti  
 Creazione di un dispositivo richiede anche un `D3DPRESENT_PARAMETERS` struct, ma solo di alcuni parametri sono importanti. Questi parametri vengono scelti per ridurre al minimo il footprint di memoria.  
  
 Impostare il `BackBufferHeight` e `BackBufferWidth` campi su 1. Impostandole su 0 fa in modo che è possibile impostare le dimensioni dell'oggetto HWND.  
  
 Impostare sempre la `D3DCREATE_MULTITHREADED` e `D3DCREATE_FPU_PRESERVE` flag per evitare il danneggiamento della memoria usata da Direct3D9 e impedire Direct3D9 di modificare le impostazioni di FPU.  
  
 Il codice seguente viene illustrato come inizializzare il `D3DPRESENT_PARAMETERS` struct.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Creazione di destinazione di rendering del Buffer nascosto  
 Per visualizzare il contenuto Direct3D9 in una <xref:System.Windows.Interop.D3DImage>, si crea una superficie Direct3D9 e assegnarla chiamando il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> (metodo).  
  
### <a name="verifying-adapter-support"></a>Verifica per determinare se il supporto di Adapter  
 Prima di creare un'area, verificare che tutti gli adapter supportano le proprietà della superficie desiderate. Anche se si esegue il rendering di una sola scheda, potrebbe essere visualizzata la finestra WPF con qualsiasi scheda nel sistema. È sempre consigliabile scrivere codice Direct3D9 che gestisce le configurazioni a più adapter e controllare tutte le schede per il supporto perché WPF può spostare l'area tra le schede disponibili.  
  
 Esempio di codice seguente viene illustrato come controllare tutte le schede sul sistema per Direct3D9 supportano.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>La creazione della superficie  
 Prima di creare un'area, verificare che le funzionalità dei dispositivi supportano buone prestazioni sul sistema operativo di destinazione. Per altre informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità di WPF e Direct3D9](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Dopo avere verificato le funzionalità di dispositivo, è possibile creare l'area. Esempio di codice seguente viene illustrato come creare la destinazione di rendering.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 In Windows Vista e versioni successive, che sono configurati per utilizzare il WDDM, è possibile creare una trama di destinazione di rendering e passare la superficie di livello 0 per il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> (metodo). Questo approccio non è consigliato in Windows XP, poiché non è possibile creare una trama di destinazione di rendering bloccabile e prestazioni risultano ridotte.  
  
## <a name="handling-device-state"></a>Gestione dello stato dispositivo  
 Il <xref:System.Windows.Interop.D3DImage> classe gestisce due buffer di visualizzazione, che vengono chiamati i *buffer nascosto* e il *front buffer*. Il buffer è la superficie Direct3D.  Le modifiche al buffer nascosto vengono copiate il front-buffer quando si chiama il <xref:System.Windows.Interop.D3DImage.Unlock%2A> metodo, in cui vengono visualizzati nell'hardware. In alcuni casi, il front buffer non è più disponibile. Questa mancanza di disponibilità può essere causata dal blocco dello schermo, applicazioni Direct3D esclusive a schermo intero, cambio utente o altre attività di sistema. In questo caso, l'applicazione WPF viene tenuto aggiornato tramite la gestione di <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> evento.  Come l'applicazione risponde al front buffer mancata disponibilità varia a seconda se WPF è abilitato per eseguire il fallback per il rendering software. Il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> metodo ha un overload che accetta un parametro che specifica se WPF esegue il fallback per il rendering software.  
  
 Quando si chiama il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> overload né chiamare le <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> overload con il `enableSoftwareFallback` parametro impostato su `false`, il sistema di rendering rilascia il riferimento al buffer nascosto quando il front buffer non è più disponibile e non è visualizzato. Quando il buffer anteriore è disponibile anche in questo caso, il sistema di rendering genera il <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> evento per notificare all'applicazione WPF.  È possibile creare un gestore eventi per il <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> riavviare rendering nuovamente con una superficie Direct3D valida dell'evento. Per riavviare il rendering, è necessario chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 Quando si chiama il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> rapporto di overload con il `enableSoftwareFallback` parametro impostato su `true`, il sistema per il rendering mantiene il riferimento al buffer nascosto quando il front buffer non è più disponibile, in modo che non è necessario chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> quando anteriore buffer è nuovamente disponibile.  
  
 Quando è abilitato il rendering software, potrebbero verificarsi situazioni in cui il dispositivo dell'utente non è più disponibile, ma il sistema di rendering mantiene un riferimento all'area di Direct3D. Per verificare se è disponibile un dispositivo Direct3D9, chiamare il `TestCooperativeLevel` (metodo). Per verificare una chiamata di dispositivi Direct3D9Ex il `CheckDeviceState` metodo, perché il `TestCooperativeLevel` metodo è obsoleto e restituisce sempre esito positivo. Se il dispositivo utente non è più disponibile, chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> rilascio di riferimento di WPF al buffer nascosto.  Se è necessario reimpostare il dispositivo, chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> con il `backBuffer` parametro impostato su `null`, quindi chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> nuovamente con `backBuffer` impostata su una superficie Direct3D valida.  
  
 Chiamare il `Reset` metodo per il ripristino da un dispositivo non è valido solo se si implementa il supporto di più adapter. In caso contrario, rilascia tutte le interfacce Direct3D9 e crearli di nuovo completamente. Se il layout dell'adattatore è stato modificato, non vengono aggiornati Direct3D9 gli oggetti creati prima della modifica.  
  
## <a name="handling-resizing"></a>Gestione del ridimensionamento  
 Se un <xref:System.Windows.Interop.D3DImage> viene visualizzato con una risoluzione diversa da quella nativa, viene ridimensionata in base al corrente <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, ad eccezione del fatto che <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> viene sostituito <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Se necessaria una maggiore fedeltà, è necessario creare una nuova superficie quando il contenitore del <xref:System.Windows.Interop.D3DImage> Modifica dimensione.  
  
 Esistono tre possibili approcci per gestire il ridimensionamento.  
  
-   Partecipare al sistema di layout e creare una nuova area quando cambiano le dimensioni. Non creare troppi risulta rilevante, perché è possibile esaurire o frammentare la memoria video.  
  
-   Attendere un evento di ridimensionamento non verificato per un periodo fisso di tempo per creare la nuova area.  
  
-   Creare un <xref:System.Windows.Threading.DispatcherTimer> che controlla le dimensioni del contenitore più volte al secondo.  
  
## <a name="multi-monitor-optimization"></a>Ottimizzazione di più monitor  
 In modo significativo calo delle prestazioni può verificarsi quando il sistema di rendering sposta un <xref:System.Windows.Interop.D3DImage> in un altro monitor.  
  
 Su WDDM, purché i monitoraggi sono sullo stesso video card e si usa `Direct3DCreate9Ex`, non vi è alcun calo delle prestazioni. Se i monitoraggi si trovano in schede video separate, le prestazioni sono ridotte. In Windows XP, le prestazioni sono ridotte sempre.  
  
 Quando il <xref:System.Windows.Interop.D3DImage> viene spostato in un altro monitor, è possibile creare una nuova superficie sulla scheda corrispondente per ripristinare le buone prestazioni.  
  
 Per evitare la riduzione delle prestazioni, scrivere codice in modo specifico per il caso di utilizzo di più monitor. Nell'elenco seguente illustra un modo per scrivere il codice con più monitor.  
  
1. Trovare un punto del <xref:System.Windows.Interop.D3DImage> nello spazio dello schermo con le `Visual.ProjectToScreen` (metodo).  
  
2. Usare il `MonitorFromPoint` metodo GDI per trovare il monitoraggio in cui viene visualizzato il punto.  
  
3. Usare il `IDirect3D9::GetAdapterMonitor` metodo per trovare l'adattatore Direct3D9 il monitoraggio si trova.  
  
4. Se l'adapter non è quello utilizzato per l'adapter con il buffer nascosto, creare un nuovo buffer nascosto nel nuovo monitor e assegnarla al <xref:System.Windows.Interop.D3DImage> buffer nascosto.  
  
> [!NOTE]
>  Se il <xref:System.Windows.Interop.D3DImage> gestisce monitoraggi, le prestazioni saranno lente, tranne nel caso di WDDM e `IDirect3D9Ex` nella stessa scheda. Non è possibile migliorare le prestazioni in questa situazione.  
  
 Esempio di codice seguente viene illustrato come trovare il monitoraggio corrente.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Aggiornare il monitoraggio quando il <xref:System.Windows.Interop.D3DImage> le modifiche di dimensione o la posizione del contenitore o aggiorna il monitoraggio tramite un `DispatcherTimer` che aggiorna più volte al secondo.  
  
## <a name="wpf-software-rendering"></a>Rendering Software WPF  
 WPF esegue il rendering in modo sincrono sul thread dell'interfaccia utente in software nelle situazioni seguenti.  
  
-   Stampa  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Quando si verifica una di queste situazioni, il sistema di rendering chiama il <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> metodo per copiare il buffer di hardware per il software. L'implementazione predefinita chiama il `GetRenderTargetData` metodo con la superficie. Poiché questa chiamata si verifica di fuori il criterio di blocco, sblocco, potrebbe non riuscire. In questo caso, il `CopyBackBuffer` restituzione del metodo `null` e viene visualizzata alcuna immagine.  
  
 È possibile eseguire l'override di <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> metodo, chiamare l'implementazione di base, e restituisce `null`, è possibile restituire un segnaposto <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 È anche possibile implementare il proprio rendering software piuttosto che chiama l'implementazione di base.  
  
> [!NOTE]
>  Se viene eseguito il rendering completamente il software, WPF <xref:System.Windows.Interop.D3DImage> non viene visualizzata perché WPF non dispone di un front buffer.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Procedura dettagliata: Creazione di contenuto Direct3D9 per l'Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
