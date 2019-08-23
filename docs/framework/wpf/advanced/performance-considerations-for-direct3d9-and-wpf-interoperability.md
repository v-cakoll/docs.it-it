---
title: Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 02a91c1824c5d6374f37b0af66a3308d33210c4a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932485"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF
È possibile ospitare il contenuto di Direct3D9 usando <xref:System.Windows.Interop.D3DImage> la classe. L'hosting del contenuto di Direct3D9 può influire sulle prestazioni dell'applicazione. In questo argomento vengono descritte le procedure consigliate per ottimizzare le prestazioni quando si ospita il contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). Queste procedure consigliate includono l'utilizzo <xref:System.Windows.Interop.D3DImage> e le procedure consigliate quando si utilizzano le visualizzazioni di Windows Vista, Windows XP e multimonitor.  
  
> [!NOTE]
> Per esempi di codice che illustrano queste procedure consigliate, vedere l'interoperatività di [WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>USA D3DImage sporadicamente  
 Il rendering del contenuto Direct3D9 <xref:System.Windows.Interop.D3DImage> ospitato in un'istanza non viene eseguito in modo rapido come in un'applicazione Direct3D pura. La copia della superficie e lo svuotamento del buffer dei comandi possono essere operazioni costose. Con l'aumentare del <xref:System.Windows.Interop.D3DImage> numero di istanze, si verifica una maggiore scaricamento e peggioramento delle prestazioni. Pertanto, è consigliabile utilizzare <xref:System.Windows.Interop.D3DImage> con moderazione.  
  
## <a name="best-practices-on-windows-vista"></a>Procedure consigliate in Windows Vista  
 Per prestazioni ottimali in Windows Vista con uno schermo configurato per l'uso di Windows Display Driver Model (WDDM), creare la superficie Direct3D9 in un `IDirect3DDevice9Ex` dispositivo. In questo modo viene abilitata la condivisione della superficie. La scheda video deve supportare le `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` funzionalità `D3DCAPS2_CANSHARERESOURCE` del driver e in Windows Vista. Tutte le altre impostazioni comportano la copia della superficie tramite software, riducendo in modo significativo le prestazioni.  
  
> [!NOTE]
> Se Windows Vista dispone di una visualizzazione configurata per l'utilizzo di Windows XP Display Driver Model (XDDM), la superficie viene sempre copiata tramite software, indipendentemente dalle impostazioni. Con le impostazioni e la scheda video appropriate, è possibile ottenere prestazioni migliori in Windows Vista quando si usa WDDM, perché le copie di superficie vengono eseguite nell'hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Procedure consigliate su Windows XP  
 Per prestazioni ottimali in Windows XP, che utilizza il modello di driver di visualizzazione di Windows XP (XDDM), creare una superficie bloccabile che funziona correttamente `IDirect3DSurface9::GetDC` quando viene chiamato il metodo. Internamente, `BitBlt` il metodo trasferisce la superficie tra i dispositivi nell'hardware. Il `GetDC` metodo funziona sempre sulle superfici sulle XRGB mentre. Tuttavia, se nel computer client è in esecuzione Windows XP con SP3 o SP2 e se il client dispone anche dell'hotfix per la funzionalità finestra a più livelli, questo metodo funziona solo su superfici ARGB. La scheda video deve supportare la `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` funzionalità del driver.  
  
 Una profondità di visualizzazione desktop a 16 bit può ridurre significativamente le prestazioni. È consigliabile usare un desktop a 32 bit.  
  
 Se si sta sviluppando per Windows Vista e Windows XP, testare le prestazioni in Windows XP. L'esaurimento della memoria del video in Windows XP costituisce un problema. Inoltre, <xref:System.Windows.Interop.D3DImage> in Windows XP utilizza una maggiore quantità di memoria e larghezza di banda del video rispetto a Windows Vista WDDM, a causa di una copia di memoria video aggiuntiva necessaria. Pertanto, è possibile che le prestazioni siano peggiori in Windows XP rispetto a Windows Vista per lo stesso hardware video.  
  
> [!NOTE]
> XDDM è disponibile sia in Windows XP che in Windows Vista. Tuttavia, WDDM è disponibile solo in Windows Vista.  
  
## <a name="general-best-practices"></a>Procedure consigliate generali  
 Quando si crea il dispositivo, usare il `D3DCREATE_MULTITHREADED` flag di creazione. Questo consente di ridurre le prestazioni, ma il sistema di rendering WPF chiama i metodi su questo dispositivo da un altro thread. Assicurarsi di seguire correttamente il protocollo di blocco, in modo che nessuno dei due thread acceda al dispositivo nello stesso momento.  
  
 Se il rendering viene eseguito su un thread gestito WPF, è consigliabile creare il dispositivo con il `D3DCREATE_FPU_PRESERVE` flag di creazione. Senza questa impostazione, il rendering D3D può ridurre l'accuratezza delle operazioni di precisione doppia WPF e introdurre problemi di rendering.  
  
 L'affiancamento a <xref:System.Windows.Interop.D3DImage> è veloce, a meno che non si riquadri una superficie non pow2 senza supporto hardware oppure se si <xref:System.Windows.Media.VisualBrush> affianca un <xref:System.Windows.Media.DrawingBrush> oggetto <xref:System.Windows.Interop.D3DImage>o che contiene un oggetto.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Procedure consigliate per la visualizzazione di più monitor  
 Se si utilizza un computer che dispone di più monitoraggi, è necessario attenersi alle procedure consigliate descritte in precedenza. Esistono inoltre alcune considerazioni aggiuntive sulle prestazioni per una configurazione a più monitor.  
  
 Quando si crea il buffer nascosto, questo viene creato su un dispositivo e un adattatore specifici, ma WPF può visualizzare il buffer anteriore su qualsiasi scheda. La copia tra gli adapter per aggiornare il buffer anteriore può essere molto costosa. In Windows Vista, configurato per l'uso di WDDM con più schede video e con un `IDirect3DDevice9Ex` dispositivo, se il buffer anteriore si trova in una scheda diversa ma ancora la stessa scheda video, non si verifica alcuna riduzione delle prestazioni. Tuttavia, in Windows XP e XDDM con più schede video, si verifica un calo significativo delle prestazioni quando il buffer anteriore viene visualizzato su un adattatore diverso rispetto al buffer nascosto. Per ulteriori informazioni, vedere l'interoperatività di [WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Riepilogo prestazioni  
 La tabella seguente illustra le prestazioni dell'aggiornamento del buffer anteriore come funzione del sistema operativo, del formato pixel e della blocco della superficie. Si presuppone che il buffer anteriore e il buffer indietro si trovino nella stessa scheda. A seconda della configurazione dell'adapter, gli aggiornamenti hardware sono in genere molto più veloci degli aggiornamenti software.  
  
|Formato pixel superficie|Windows Vista, WDDM e 9Ex|Altre configurazioni di Windows Vista|Windows XP SP3 o SP2 w/hotfix|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (non bloccabile)|**Aggiornamento hardware**|Aggiornamento software|Aggiornamento software|Aggiornamento software|  
|D3DFMT_X8R8G8B8 (bloccabile)|**Aggiornamento hardware**|Aggiornamento software|**Aggiornamento hardware**|**Aggiornamento hardware**|  
|D3DFMT_A8R8G8B8 (non bloccabile)|**Aggiornamento hardware**|Aggiornamento software|Aggiornamento software|Aggiornamento software|  
|D3DFMT_A8R8G8B8 (bloccabile)|**Aggiornamento hardware**|Aggiornamento software|**Aggiornamento hardware**|Aggiornamento software|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md)
- [Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
