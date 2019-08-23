---
title: Interoperatività di WPF e Direct3D9
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 5fccd49b4f6fa64e5902197423d732ba0b31790e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917429"
---
# <a name="wpf-and-direct3d9-interoperation"></a>Interoperatività di WPF e Direct3D9
È possibile includere contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). Questo argomento descrive come creare contenuto Direct3D9 in modo che interagisca in modo efficiente con WPF.  
  
> [!NOTE]
> Quando si usa il contenuto Direct3D9 in WPF, è necessario considerare anche le prestazioni. Per ulteriori informazioni su come ottimizzare le prestazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Buffer di visualizzazione  
 La <xref:System.Windows.Interop.D3DImage> classe gestisce due buffer di visualizzazione, denominati *buffer nascosto* e il *buffer anteriore*. Il buffer nascosto è la superficie di Direct3D9. Le modifiche apportate al buffer nascosto vengono copiate in avanti nel buffer anteriore <xref:System.Windows.Interop.D3DImage.Unlock%2A> quando si chiama il metodo.  
  
 Nella figura seguente viene illustrata la relazione tra il buffer nascosto e il buffer anteriore.  
  
 ![Buffer di visualizzazione D3DImage](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Creazione del dispositivo Direct3D9  
 Per eseguire il rendering del contenuto di Direct3D9, è necessario creare un dispositivo Direct3D9. Esistono due oggetti Direct3D9 che è possibile usare per creare un dispositivo, `IDirect3D9` e. `IDirect3D9Ex` Usare questi oggetti per creare `IDirect3DDevice9` rispettivamente `IDirect3DDevice9Ex` i dispositivi e.  
  
 Creare un dispositivo chiamando uno dei metodi seguenti.  
  
- `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
- `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 In Windows Vista o sistemi operativi successivi utilizzare il `Direct3DCreate9Ex` metodo con una visualizzazione configurata per l'utilizzo di Windows Display Driver Model (WDDM). Usare il `Direct3DCreate9` metodo su qualsiasi altra piattaforma.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Disponibilità del metodo Direct3DCreate9Ex  
 D3d9. dll ha il `Direct3DCreate9Ex` metodo solo in Windows Vista o in un sistema operativo successivo. Se si collega direttamente la funzione in Windows XP, il caricamento dell'applicazione non riesce. Per determinare se il `Direct3DCreate9Ex` metodo è supportato, caricare la dll e cercare l'indirizzo proc. Nel codice seguente viene illustrato come eseguire il test `Direct3DCreate9Ex` per il metodo. Per un esempio di codice completo, [vedere Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)in WPF.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>Creazione di HWND  
 Per la creazione di un dispositivo è necessario un HWND. In generale, si crea un HWND fittizio per Direct3D9 da usare. Nell'esempio di codice seguente viene illustrato come creare un HWND fittizio.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Parametri presenti  
 La creazione di un dispositivo richiede `D3DPRESENT_PARAMETERS` anche uno struct, ma sono importanti solo alcuni parametri. Questi parametri vengono scelti per ridurre al minimo il footprint di memoria.  
  
 Impostare i `BackBufferHeight` campi `BackBufferWidth` e su 1. Impostando il valore su 0, tali elementi vengono impostati sulle dimensioni di HWND.  
  
 Impostare sempre i `D3DCREATE_MULTITHREADED` flag `D3DCREATE_FPU_PRESERVE` e per evitare che il danneggiamento della memoria utilizzata da Direct3D9 e per impedire a Direct3D9 di modificare le impostazioni FPU.  
  
 Il codice seguente illustra come inizializzare lo `D3DPRESENT_PARAMETERS` struct.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Creazione della destinazione di rendering del buffer nascosto  
 Per visualizzare il contenuto di Direct3D9 <xref:System.Windows.Interop.D3DImage>in un oggetto, creare una superficie Direct3D9 e assegnarla chiamando <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> il metodo.  
  
### <a name="verifying-adapter-support"></a>Verifica del supporto dell'adapter  
 Prima di creare una superficie, verificare che tutti gli adapter supportino le proprietà di superficie richieste. Anche se si esegue il rendering in una sola scheda, è possibile che la finestra WPF venga visualizzata in qualsiasi scheda del sistema. È necessario scrivere sempre il codice Direct3D9 che gestisce le configurazioni a più schede ed è necessario controllare tutte le schede per il supporto, perché WPF potrebbe spostare la superficie tra le schede disponibili.  
  
 Nell'esempio di codice seguente viene illustrato come controllare tutte le schede del sistema per il supporto di Direct3D9.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>Creazione della superficie  
 Prima di creare una superficie, verificare che le funzionalità del dispositivo supportino prestazioni ottimali sul sistema operativo di destinazione. Per ulteriori informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Una volta verificate le funzionalità del dispositivo, è possibile creare la superficie. Nell'esempio di codice seguente viene illustrato come creare la destinazione di rendering.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 In Windows Vista e nei sistemi operativi successivi, che sono configurati per l'uso di WDDM, è possibile creare una trama di destinazione di rendering e passare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> la superficie di livello 0 al metodo. Questo approccio non è consigliato in Windows XP, perché non è possibile creare una trama di destinazione di rendering bloccabile e le prestazioni risulteranno ridotte.  
  
## <a name="handling-device-state"></a>Gestione dello stato del dispositivo  
 La <xref:System.Windows.Interop.D3DImage> classe gestisce due buffer di visualizzazione, denominati *buffer nascosto* e il *buffer anteriore*. Il buffer nascosto è la superficie Direct3D.  Le modifiche apportate al buffer nascosto vengono copiate in avanti nel buffer anteriore <xref:System.Windows.Interop.D3DImage.Unlock%2A> quando si chiama il metodo, dove viene visualizzato sull'hardware. In alcuni casi, il buffer anteriore diventa non disponibile. Questa mancanza di disponibilità può essere causata da blocchi schermo, applicazioni Direct3D esclusive a schermo intero, cambio utente o altre attività del sistema. In tal caso, l'applicazione WPF riceve una notifica gestendo <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> l'evento.  La modalità di risposta dell'applicazione al buffer anteriore diventa non disponibile a seconda che WPF sia abilitato per il fallback al rendering del software. Il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> metodo ha un overload che accetta un parametro che specifica se WPF esegue il fallback al rendering software.  
  
 Quando si chiama l' <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> overload o si chiama <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> l'overload con `enableSoftwareFallback` il parametro impostato `false`su, il sistema di rendering rilascia il riferimento al buffer nascosto quando il buffer anteriore diventa non disponibile e non è presente alcun elemento visualizzato. Quando il buffer anteriore è nuovamente disponibile, il sistema di rendering genera <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> l'evento per notificare all'applicazione WPF.  È possibile creare un gestore eventi per l' <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> evento per riavviare nuovamente il rendering con una superficie Direct3D valida. Per riavviare il rendering, è necessario <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>chiamare.  
  
 Quando si chiama l' <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> overload con il `enableSoftwareFallback` parametro impostato su `true`, il sistema di rendering mantiene il relativo riferimento al buffer nascosto quando il buffer anteriore non è più disponibile, pertanto non è necessario chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> quando il front-end il buffer è nuovamente disponibile.  
  
 Quando il rendering del software è abilitato, in alcune situazioni il dispositivo dell'utente non è più disponibile, ma il sistema di rendering mantiene un riferimento alla superficie Direct3D. Per verificare se un dispositivo Direct3D9 non è disponibile, chiamare `TestCooperativeLevel` il metodo. Per controllare che i dispositivi Direct3D9Ex chiamino il `CheckDeviceState` metodo, perché il `TestCooperativeLevel` metodo è deprecato e restituisce sempre success. Se il dispositivo utente non è più disponibile, <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> chiamare per rilasciare il riferimento di WPF al buffer nascosto.  Se è necessario reimpostare il dispositivo, chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> con il `backBuffer` parametro impostato su `null`e quindi chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> di nuovo con `backBuffer` impostato su una superficie Direct3D valida.  
  
 Chiamare il `Reset` metodo per eseguire il ripristino da un dispositivo non valido solo se si implementa il supporto per più adapter. In caso contrario, rilasciare tutte le interfacce Direct3D9 e ricrearle completamente. Se il layout dell'adapter è stato modificato, gli oggetti Direct3D9 creati prima della modifica non vengono aggiornati.  
  
## <a name="handling-resizing"></a>Gestione del ridimensionamento  
 Se un <xref:System.Windows.Interop.D3DImage> oggetto viene visualizzato con una risoluzione diversa dalle dimensioni native, viene ridimensionato in base all'oggetto <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>corrente, ad <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> eccezione del <xref:System.Windows.Media.BitmapScalingMode.Fant>fatto che viene sostituito da.  
  
 Se è necessaria una maggiore fedeltà, è necessario creare una nuova superficie quando il contenitore delle <xref:System.Windows.Interop.D3DImage> dimensioni cambia.  
  
 Sono disponibili tre approcci possibili per gestire il ridimensionamento.  
  
- Partecipare al sistema di layout e creare una nuova superficie quando cambiano le dimensioni. Non creare troppe superfici perché è possibile che si verifichi un esaurimento o un frammento di memoria video.  
  
- Attendere fino a quando non si è verificato un evento di ridimensionamento per un periodo di tempo fisso per la creazione della nuova superficie.  
  
- Creare una <xref:System.Windows.Threading.DispatcherTimer> che controlla le dimensioni del contenitore più volte al secondo.  
  
## <a name="multi-monitor-optimization"></a>Ottimizzazione di più monitor  
 Una riduzione significativa delle prestazioni può verificarsi quando il sistema di <xref:System.Windows.Interop.D3DImage> rendering sposta un oggetto in un altro monitor.  
  
 In WDDM, purché i monitoraggi si trovino nella stessa scheda video e si usi `Direct3DCreate9Ex`, non si verifica alcuna riduzione delle prestazioni. Se i monitoraggi si trovano su schede video separate, le prestazioni sono ridotte. In Windows XP, le prestazioni sono sempre ridotte.  
  
 Quando il <xref:System.Windows.Interop.D3DImage> passa a un altro monitor, è possibile creare una nuova superficie sull'adattatore corrispondente per ripristinare le prestazioni ottimali.  
  
 Per evitare la riduzione delle prestazioni, scrivere codice specifico per il caso di più monitor. Nell'elenco seguente viene illustrato un modo per scrivere codice di più monitor.  
  
1. Trovare un punto di <xref:System.Windows.Interop.D3DImage> nello spazio dello schermo con il `Visual.ProjectToScreen` metodo.  
  
2. Utilizzare il `MonitorFromPoint` metodo GDI per individuare il monitoraggio che Visualizza il punto.  
  
3. Utilizzare il `IDirect3D9::GetAdapterMonitor` metodo per individuare l'adattatore Direct3D9 su cui si trova il monitoraggio.  
  
4. Se l'adapter non è uguale all'adapter con il buffer nascosto, creare un nuovo buffer nascosto sul nuovo monitoraggio e assegnarlo al <xref:System.Windows.Interop.D3DImage> buffer nascosto.  
  
> [!NOTE]
> Se si <xref:System.Windows.Interop.D3DImage> trova a cavalcioni dei monitoraggi, le prestazioni saranno lente, tranne nel caso di WDDM `IDirect3D9Ex` e sulla stessa scheda. In questa situazione non è possibile migliorare le prestazioni.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come individuare il monitoraggio corrente.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Aggiornare il monitoraggio quando cambiano <xref:System.Windows.Interop.D3DImage> le dimensioni o la posizione del contenitore oppure aggiornare il monitoraggio utilizzando un `DispatcherTimer` che si aggiorna alcune volte al secondo.  
  
## <a name="wpf-software-rendering"></a>Rendering del software WPF  
 WPF esegue il rendering in modo sincrono sul thread dell'interfaccia utente nel software nelle situazioni seguenti.  
  
- Stampa  
  
- <xref:System.Windows.Media.Effects.BitmapEffect>  
  
- <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Quando si verifica una di queste situazioni, il sistema di rendering <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> chiama il metodo per copiare il buffer hardware nel software. L'implementazione predefinita chiama il `GetRenderTargetData` metodo con la superficie. Poiché questa chiamata si verifica al di fuori del modello di blocco/sblocco, potrebbe non riuscire. In questo caso, il `CopyBackBuffer` metodo restituisce `null` e non viene visualizzata alcuna immagine.  
  
 È possibile eseguire l' <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> override del metodo, chiamare l'implementazione di base e, `null`se restituisce, è possibile restituire <xref:System.Windows.Media.Imaging.BitmapSource>un segnaposto.  
  
 È anche possibile implementare il proprio rendering software anziché chiamare l'implementazione di base.  
  
> [!NOTE]
> Se WPF esegue il rendering completamente nel software <xref:System.Windows.Interop.D3DImage> , non viene visualizzato perché WPF non dispone di un buffer anteriore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
