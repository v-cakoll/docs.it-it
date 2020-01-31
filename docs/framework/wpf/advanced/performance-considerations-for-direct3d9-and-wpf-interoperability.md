---
title: Considerazioni sulle prestazioni per l'interoperabilità Direct3D9 e WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 2445732c27d210a41da26303d6a9ce07ef6fcc94
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743939"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF
È possibile ospitare il contenuto di Direct3D9 usando la classe <xref:System.Windows.Interop.D3DImage>. L'hosting del contenuto di Direct3D9 può influire sulle prestazioni dell'applicazione. In questo argomento vengono descritte le procedure consigliate per ottimizzare le prestazioni quando si ospita il contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). Queste procedure consigliate includono l'utilizzo di <xref:System.Windows.Interop.D3DImage> e le procedure consigliate quando si utilizzano le visualizzazioni di Windows Vista, Windows XP e multimonitor.  
  
> [!NOTE]
> Per esempi di codice che illustrano queste procedure consigliate, vedere l' [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>USA D3DImage sporadicamente  
 Il rendering del contenuto Direct3D9 ospitato in un'istanza di <xref:System.Windows.Interop.D3DImage> non viene eseguito in modo rapido come in un'applicazione Direct3D pura. La copia della superficie e lo svuotamento del buffer dei comandi possono essere operazioni costose. Man mano che il numero di istanze di <xref:System.Windows.Interop.D3DImage> aumenta, si verificano più Scaricamenti e si verifica un peggioramento delle prestazioni. Pertanto, è consigliabile utilizzare <xref:System.Windows.Interop.D3DImage> sporadicamente.  
  
## <a name="best-practices-on-windows-vista"></a>Procedure consigliate in Windows Vista  
 Per prestazioni ottimali in Windows Vista con uno schermo configurato per l'uso di Windows Display Driver Model (WDDM), creare la superficie Direct3D9 in un dispositivo `IDirect3DDevice9Ex`. In questo modo viene abilitata la condivisione della superficie. La scheda video deve supportare le funzionalità di `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` e `D3DCAPS2_CANSHARERESOURCE` driver in Windows Vista. Tutte le altre impostazioni comportano la copia della superficie tramite software, riducendo in modo significativo le prestazioni.  
  
> [!NOTE]
> Se Windows Vista dispone di una visualizzazione configurata per l'utilizzo di Windows XP Display Driver Model (XDDM), la superficie viene sempre copiata tramite software, indipendentemente dalle impostazioni. Con le impostazioni e la scheda video appropriate, è possibile ottenere prestazioni migliori in Windows Vista quando si usa WDDM, perché le copie di superficie vengono eseguite nell'hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Procedure consigliate su Windows XP  
 Per prestazioni ottimali in Windows XP, che utilizza il modello di driver di visualizzazione di Windows XP (XDDM), creare una superficie bloccabile che funziona correttamente quando viene chiamato il metodo `IDirect3DSurface9::GetDC`. Internamente, il metodo `BitBlt` trasferisce la superficie tra i dispositivi nell'hardware. Il metodo `GetDC` funziona sempre sulle superfici sulle XRGB mentre. Tuttavia, se nel computer client è in esecuzione Windows XP con SP3 o SP2 e se il client dispone anche dell'hotfix per la funzionalità finestra a più livelli, questo metodo funziona solo su superfici ARGB. La scheda video deve supportare la funzionalità del driver `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES`.  
  
 Una profondità di visualizzazione desktop a 16 bit può ridurre significativamente le prestazioni. È consigliabile usare un desktop a 32 bit.  
  
 Se si sta sviluppando per Windows Vista e Windows XP, testare le prestazioni in Windows XP. L'esaurimento della memoria del video in Windows XP costituisce un problema. Inoltre, <xref:System.Windows.Interop.D3DImage> in Windows XP utilizza una maggiore quantità di memoria e larghezza di banda video rispetto a Windows Vista WDDM, a causa di una copia di memoria video aggiuntiva necessaria. Pertanto, è possibile che le prestazioni siano peggiori in Windows XP rispetto a Windows Vista per lo stesso hardware video.  
  
> [!NOTE]
> XDDM è disponibile sia in Windows XP che in Windows Vista. Tuttavia, WDDM è disponibile solo in Windows Vista.  
  
## <a name="general-best-practices"></a>Procedure consigliate generali  
 Quando si crea il dispositivo, usare il flag di creazione `D3DCREATE_MULTITHREADED`. Questo consente di ridurre le prestazioni, ma il sistema di rendering WPF chiama i metodi su questo dispositivo da un altro thread. Assicurarsi di seguire correttamente il protocollo di blocco, in modo che nessuno dei due thread acceda al dispositivo nello stesso momento.  
  
 Se il rendering viene eseguito su un thread gestito WPF, è consigliabile creare il dispositivo con il flag di creazione del `D3DCREATE_FPU_PRESERVE`. Senza questa impostazione, il rendering D3D può ridurre l'accuratezza delle operazioni di precisione doppia WPF e introdurre problemi di rendering.  
  
 L'affiancamento di un <xref:System.Windows.Interop.D3DImage> è veloce, a meno che non si riquadri una superficie non pow2 senza supporto hardware oppure se si affianca un <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> che contiene una <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Procedure consigliate per la visualizzazione di più monitor  
 Se si utilizza un computer che dispone di più monitoraggi, è necessario attenersi alle procedure consigliate descritte in precedenza. Esistono inoltre alcune considerazioni aggiuntive sulle prestazioni per una configurazione a più monitor.  
  
 Quando si crea il buffer nascosto, questo viene creato su un dispositivo e un adattatore specifici, ma WPF può visualizzare il buffer anteriore su qualsiasi scheda. La copia tra gli adapter per aggiornare il buffer anteriore può essere molto costosa. In Windows Vista, configurato per l'uso di WDDM con più schede video e con un dispositivo `IDirect3DDevice9Ex`, se il buffer anteriore si trova in una scheda diversa ma ancora la stessa scheda video, non si verifica alcun calo delle prestazioni. Tuttavia, in Windows XP e XDDM con più schede video, si verifica un calo significativo delle prestazioni quando il buffer anteriore viene visualizzato su un adattatore diverso rispetto al buffer nascosto. Per ulteriori informazioni, vedere l' [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
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
