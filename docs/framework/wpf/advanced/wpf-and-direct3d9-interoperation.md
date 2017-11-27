---
title: "Interoperatività di WPF e Direct3D9"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1bd4d7486f546a340a4c722d140c6c7f5cee707
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-and-direct3d9-interoperation"></a>Interoperatività di WPF e Direct3D9
È possibile includere contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). In questo argomento viene descritto come creare contenuto Direct3D9 in modo che in modo efficiente interagisce con WPF.  
  
> [!NOTE]
>  Quando si utilizza il contenuto Direct3D9 in WPF, è necessario anche valutare le prestazioni. Per ulteriori informazioni su come ottimizzare le prestazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Buffer di visualizzazione  
 Il <xref:System.Windows.Interop.D3DImage> classe gestisce due buffer di visualizzazione, ovvero il *buffer nascosto* e *buffer front-*. Il buffer rappresenta la superficie Direct3D9. Le modifiche apportate al buffer nascosto vengono copiate nel front buffer quando si chiama il <xref:System.Windows.Interop.D3DImage.Unlock%2A> metodo.  
  
 Nella figura seguente viene illustrata la relazione tra il buffer nascosto e il buffer anteriore.  
  
 ![Buffer di visualizzazione D3DImage](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Creazione di un dispositivo Direct3D9  
 Per eseguire il rendering Direct3D9 contenuto, è necessario creare un dispositivo Direct3D9. Esistono due oggetti Direct3D9 che è possibile utilizzare per creare un dispositivo, `IDirect3D9` e `IDirect3D9Ex`. Utilizzare questi oggetti per creare `IDirect3DDevice9` e `IDirect3DDevice9Ex` dispositivi, rispettivamente.  
  
 Creare un dispositivo chiamando uno dei metodi seguenti.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 In Windows Vista o versioni successive del sistema operativo, utilizzare il `Direct3DCreate9Ex` metodo con una visualizzazione che è configurata per l'utilizzo di Windows Driver Model (WDDM Display). Utilizzare il `Direct3DCreate9` metodo su qualsiasi altra piattaforma.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Disponibilità del metodo Direct3DCreate9Ex  
 È il d3d9.dll il `Direct3DCreate9Ex` metodo solo in Windows Vista o versioni successive del sistema operativo. Se si collega direttamente la funzione in Windows XP, l'applicazione non riesce a caricare. Per determinare se il `Direct3DCreate9Ex` metodo è supportato, caricare la DLL e cercare l'indirizzo di routine. Il codice seguente viene illustrato come verificare la presenza di `Direct3DCreate9Ex` metodo. Per un esempio di codice completo, vedere [procedura dettagliata: creazione di contenuto Direct3D9 per l'Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>Creazione di un HWND  
 Creazione di un dispositivo richiede un elemento HWND. In generale, si crea un HWND fittizio Direct3D9 da utilizzare. Esempio di codice seguente viene illustrato come creare un HWND fittizio.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Parametri presenti  
 La creazione di un dispositivo richiede anche un `D3DPRESENT_PARAMETERS` struct, ma solo alcuni parametri sono importanti. Questi parametri vengono scelti per ridurre il footprint di memoria.  
  
 Impostare il `BackBufferHeight` e `BackBufferWidth` campi su 1. Se li su 0, che è possibile impostare le dimensioni di HWND.  
  
 Impostare sempre la `D3DCREATE_MULTITHREADED` e `D3DCREATE_FPU_PRESERVE` flag per evitare il danneggiamento della memoria utilizzata da Direct3D9 e per impedire a Direct3D9 di modificare le impostazioni FPU.  
  
 Il codice seguente viene illustrato come inizializzare il `D3DPRESENT_PARAMETERS` struct.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Creazione di destinazione di rendering del Buffer nascosto  
 Per visualizzare il contenuto Direct3D9 in un <xref:System.Windows.Interop.D3DImage>, si crea una superficie di Direct3D9 e assegnarlo chiamando il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> metodo.  
  
### <a name="verifying-adapter-support"></a>Supporto per gli Adapter di verifica  
 Prima di creare un'area, verificare che tutti gli adapter supportano la superficie di attacco proprietà che necessarie. Anche se si esegue il rendering di una sola scheda, la finestra WPF è visualizzata in qualsiasi scheda nel sistema. È necessario scrivere sempre codice Direct3D9 che gestisce le configurazioni delle multi- schede e controllare tutte le schede per il supporto, poiché WPF è possibile spostare l'area tra le schede disponibili.  
  
 Esempio di codice seguente viene illustrato come controllare tutte le schede sul sistema per Direct3D9 supportano.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>La creazione della superficie  
 Prima di creare un'area, verificare che le funzionalità dei dispositivi supportano buone prestazioni nel sistema operativo di destinazione. Per ulteriori informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Dopo avere verificato le funzionalità di dispositivo, è possibile creare l'area. Esempio di codice seguente viene illustrato come creare la destinazione di rendering.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 In Windows Vista e versioni successive, che sono configurati per l'utilizzo di WDDM, è possibile creare una trama di destinazione di rendering e passare la superficie di livello 0 per il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> metodo. Questo approccio non è consigliato in Windows XP, perché non è possibile creare una trama di destinazione di rendering bloccabile e prestazioni risultano ridotte.  
  
## <a name="handling-device-state"></a>Gestione dello stato del dispositivo  
 Il <xref:System.Windows.Interop.D3DImage> classe gestisce due buffer di visualizzazione, ovvero il *buffer nascosto* e *buffer front-*. Il buffer rappresenta la superficie di Direct3D.  Le modifiche apportate al buffer nascosto vengono copiate nel front buffer quando si chiama il <xref:System.Windows.Interop.D3DImage.Unlock%2A> (metodo), in cui vengono visualizzati nell'hardware. In alcuni casi, il front buffer non è più disponibile. La mancanza di disponibilità può essere causata dal blocco dello schermo, applicazioni Direct3D esclusive a schermo intero, cambio utente o altre attività di sistema. In questo caso, l'applicazione WPF notifica gestendo il <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> evento.  Modalità di risposta dell'applicazione nel front buffer non sono più disponibili dipende dal tipo di attivazione WPF per eseguire il fallback per il rendering software. Il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> metodo presenta un overload che accetta un parametro che specifica se il fallback WPF per il rendering software.  
  
 Quando si chiama il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> overload o chiamare il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> eseguire l'overload con il `enableSoftwareFallback` parametro impostato su `false`, il sistema di rendering rilascia il riferimento al buffer nascosto quando il front buffer non è più disponibile e non è visualizzato. Quando il buffer anteriore è nuovamente disponibile, il sistema di rendering genera il <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> evento per notificare all'applicazione WPF.  È possibile creare un gestore eventi per il <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> riavviare il rendering con una superficie Direct3D valida dell'evento. Per riavviare il rendering, è necessario chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 Quando si chiama il <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> eseguire l'overload con il `enableSoftwareFallback` parametro impostato su `true`, il sistema di rendering mantiene il relativo riferimento al buffer nascosto quando il front buffer non è disponibile, in modo non è necessario chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> quando all'inizio buffer sarà nuovamente disponibile.  
  
 Quando è abilitato per il rendering software, potrebbero verificarsi situazioni in cui il dispositivo dell'utente non è più disponibile, ma il sistema di rendering mantiene un riferimento all'area di Direct3D. Per verificare se un dispositivo Direct3D9 è disponibile, chiamare il `TestCooperativeLevel` metodo. Per verificare una chiamata di dispositivi Direct3D9Ex il `CheckDeviceState` (metodo), in quanto il `TestCooperativeLevel` metodo è obsoleto e restituisce sempre esito positivo. Se il dispositivo dell'utente non è più disponibile, chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> per rilasciare il riferimento di WPF al buffer nascosto.  Per reimpostare il dispositivo, è necessario chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> con il `backBuffer` parametro impostato su `null`e quindi chiamare <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> con `backBuffer` impostato su una superficie Direct3D valida.  
  
 Chiamare il `Reset` metodo per recuperare da un dispositivo non valido solo se si implementa il supporto per più adattatori. In caso contrario, rilascia tutte le interfacce Direct3D9 e ricrearle completamente. Se è stato modificato il layout dell'adattatore, gli oggetti Direct3D9 creati prima della modifica non vengono aggiornati.  
  
## <a name="handling-resizing"></a>Gestione del ridimensionamento  
 Se un <xref:System.Windows.Interop.D3DImage> viene visualizzata una risoluzione diversa da quella nativa, viene ridimensionato in base alle corrente <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, ad eccezione del fatto che <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> verrà sostituito con <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Se è necessaria fedeli, è necessario creare un nuovo superficie quando il contenitore di <xref:System.Windows.Interop.D3DImage> Modifica dimensione.  
  
 Esistono tre possibili approcci per gestire il ridimensionamento.  
  
-   Creare una nuova area quando cambiano le dimensioni fanno parte del sistema di layout. Non creare troppe superfici, perché non è possibile esaurire o frammentare la memoria video.  
  
-   Attendere un evento di ridimensionamento non è stata eseguita per un determinato periodo di tempo per creare la nuova area.  
  
-   Creare un <xref:System.Windows.Threading.DispatcherTimer> che controlla le dimensioni del contenitore varie volte al secondo.  
  
## <a name="multi-monitor-optimization"></a>Ottimizzazione di più monitor  
 In modo significativo calo delle prestazioni può verificarsi quando il sistema di rendering sposta un <xref:System.Windows.Interop.D3DImage> in un altro monitor.  
  
 In WDDM, purché i monitoraggi si trovano nello stesso video card e si utilizza `Direct3DCreate9Ex`, non vi è alcuna riduzione delle prestazioni. Se i monitoraggi sono sulle schede video separate, le prestazioni sono ridotte. In Windows XP, le prestazioni sono sempre ridotte.  
  
 Quando il <xref:System.Windows.Interop.D3DImage> viene spostato in un altro monitor, è possibile creare una nuova superficie nell'adattatore corrispondente per ripristinare le buone prestazioni.  
  
 Per evitare la riduzione delle prestazioni, è possibile scrivere codice in modo specifico per il caso di più monitor. Nell'elenco seguente viene illustrato un modo per scrivere codice più monitor.  
  
1.  Trovare un punto del <xref:System.Windows.Interop.D3DImage> nello spazio dello schermo con il `Visual.ProjectToScreen` metodo.  
  
2.  Utilizzare il `MonitorFromPoint` metodo GDI per trovare il monitoraggio in cui viene visualizzato il punto.  
  
3.  Utilizzare il `IDirect3D9::GetAdapterMonitor` metodo per trovare l'adattatore Direct3D9 il monitor si trova.  
  
4.  Se l'adapter non corrisponde l'adapter per il buffer nascosto, creare un nuovo buffer nascosto nel nuovo monitor e assegnarlo al <xref:System.Windows.Interop.D3DImage> buffer nascosto.  
  
> [!NOTE]
>  Se il <xref:System.Windows.Interop.D3DImage> monitor gestisce, le prestazioni saranno lente, salvo nel caso WDDM e `IDirect3D9Ex` sulla stessa scheda. Non è possibile migliorare le prestazioni in questa situazione.  
  
 Esempio di codice seguente viene illustrato come trovare il monitoraggio corrente.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Aggiornare il monitoraggio quando il <xref:System.Windows.Interop.D3DImage> le modifiche apportate a dimensioni o la posizione del contenitore o l'aggiornamento del monitoraggio utilizzando un `DispatcherTimer` che aggiorna più volte al secondo.  
  
## <a name="wpf-software-rendering"></a>Rendering Software WPF  
 WPF esegue il rendering in modo sincrono sul thread dell'interfaccia utente in software nelle situazioni seguenti.  
  
-   Stampa  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Quando si verifica una di queste situazioni, il rendering viene chiamato il <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> metodo per copiare il buffer hardware nel software. L'implementazione predefinita chiama il `GetRenderTargetData` metodo con la superficie. Poiché questa chiamata si trova di fuori il criterio di blocco/sblocco, potrebbe non riuscire. In questo caso, il `CopyBackBuffer` restituisce `null` e viene visualizzata alcuna immagine.  
  
 È possibile eseguire l'override di <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> metodo, chiamare l'implementazione di base, e se viene restituito `null`, è possibile restituire un segnaposto <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 È anche possibile implementare direttamente il rendering software anziché chiamare l'implementazione di base.  
  
> [!NOTE]
>  Se viene eseguito il rendering completamente il software, WPF <xref:System.Windows.Interop.D3DImage> non viene visualizzato perché WPF non dispone di un front buffer.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.D3DImage>  
 [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
