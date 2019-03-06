---
title: Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: fd3c99f22a1d097c82494ba6eff344820162ed87
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356728"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF
È possibile ospitare contenuto Direct3D9 usando il <xref:System.Windows.Interop.D3DImage> classe. Hosting di contenuto Direct3D9 può influire sulle prestazioni dell'applicazione. In questo argomento descrive le procedure consigliate per ottimizzare le prestazioni durante l'hosting di contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). Queste procedure consigliate includono come usare <xref:System.Windows.Interop.D3DImage> e procedure consigliate quando si utilizza Windows Vista, Windows XP, e viene visualizzato con più monitor.  
  
> [!NOTE]
>  Per esempi di codice che illustrano le procedure consigliate, vedere [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Utilizzare in modo sporadico D3DImage  
 Direct3D9 contenuto ospitato un <xref:System.Windows.Interop.D3DImage> istanza non sottoposti a rendering come veloce come in un'applicazione Direct3D. L'area di copia e lo scaricamento buffer dei comandi possono essere operazioni costose. Come il numero di <xref:System.Windows.Interop.D3DImage> aumenta istanze, viene eseguita una svuotamento aumentano e comporta una riduzione delle prestazioni. Pertanto, è necessario utilizzare <xref:System.Windows.Interop.D3DImage> quando strettamente necessario.  
  
## <a name="best-practices-on-windows-vista"></a>Le procedure consigliate in Windows Vista  
 Per prestazioni ottimali su Windows Vista con una visualizzazione che è configurata per utilizzare Windows Visualizza Driver Model (WDDM), creare la superficie Direct3D9 in un `IDirect3DDevice9Ex` dispositivo. In questo modo la condivisione della superficie. La scheda video deve supportare le `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` e `D3DCAPS2_CANSHARERESOURCE` le funzionalità del driver in Windows Vista. Tutte le altre impostazioni causano la superficie deve essere copiato tramite software, che riduce significativamente le prestazioni.  
  
> [!NOTE]
>  Se Windows Vista ha una visualizzazione a cui è configurata per l'utilizzo di Windows XP XDDM Display Driver Model (), l'area viene sempre copiato tramite software, indipendentemente dalle impostazioni. Con le impostazioni appropriate e la scheda video, si noteranno prestazioni migliori su Windows Vista quando si usa il WDDM perché vengono eseguite le copie della superficie in hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Procedure consigliate su Windows XP  
 Per ottenere prestazioni ottimali su Windows XP, che utilizza il Windows Display Driver Model XDDM (XP), creare una superficie bloccabile che funziona correttamente quando il `IDirect3DSurface9::GetDC` viene chiamato il metodo. Internamente, il `BitBlt` metodo trasferisce la superficie su dispositivi hardware. Il `GetDC` metodo è sempre valido su superfici XRGB. Tuttavia, se il computer client è in esecuzione Windows XP con SP2 o SP3, e se il client ha anche l'hotfix per la funzionalità delle finestre sovrapposte, questo metodo funziona solo nelle aree ARGB. La scheda video deve supportare la `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` funzionalità del driver.  
  
 Una profondità di monitor per desktop a 16 bit può ridurre notevolmente le prestazioni. È consigliabile un desktop a 32 bit.  
  
 Se si sviluppa per Windows Vista e Windows XP, test delle prestazioni in Windows XP. Esaurimento memoria video su Windows XP è un problema. Inoltre, <xref:System.Windows.Interop.D3DImage> in Windows XP utilizza più memoria video e della larghezza di banda rispetto a Windows Vista WDDM, a causa di una copia di memoria video aggiuntiva necessaria. Pertanto, è possibile prevedere prestazioni peggiori in Windows XP a Windows Vista sono per lo stesso hardware video.  
  
> [!NOTE]
>  XDDM è disponibile in Windows XP e Windows Vista. Tuttavia, WDDM è disponibile solo in Windows Vista.  
  
## <a name="general-best-practices"></a>Procedure consigliate generali  
 Quando si crea il dispositivo, usare il `D3DCREATE_MULTITHREADED` flag di creazione. Ciò riduce le prestazioni, ma il sistema di rendering WPF chiama metodi su questo dispositivo da un altro thread. Assicurarsi di seguire correttamente, il protocollo di blocco in modo che nessun due thread di accedere al dispositivo nello stesso momento.  
  
 Se il rendering viene eseguito su un thread gestito WPF, è consigliabile creare il dispositivo con il `D3DCREATE_FPU_PRESERVE` flag di creazione. Senza questa impostazione, il rendering di D3D può ridurre la precisione delle operazioni con precisione doppia WPF e introdurre problemi di rendering.  
  
 Affiancamento di un <xref:System.Windows.Interop.D3DImage> è veloce, a meno che non è affiancare un'area di non-pow2 senza il supporto di hardware o se è affiancare un <xref:System.Windows.Media.DrawingBrush> oppure <xref:System.Windows.Media.VisualBrush> che contiene un <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Le procedure consigliate per gli schermi con più Monitor  
 Se si utilizza un computer che dispone di più monitor, è necessario seguire le procedure consigliate descritte in precedenza. Esistono inoltre alcune considerazioni aggiuntive sulle prestazioni per una configurazione con più monitor.  
  
 Quando si crea il buffer nascosto, viene creato in un dispositivo specifico e un adapter, ma WPF può visualizzare il buffer di front con qualsiasi scheda. Copia tra gli adattatori per aggiornare il front buffer può essere molto dispendiosa. In Windows Vista che è configurato per l'uso di WDDM con più schede video e con un `IDirect3DDevice9Ex` dispositivo, se il buffer anteriore è su una scheda diversa ma nella stessa scheda video, non vi è alcuna riduzione delle prestazioni. Tuttavia, in Windows XP e il XDDM con più schede video, vi è una riduzione significativa delle prestazioni quando front buffer viene visualizzato in una scheda diversa rispetto al buffer nascosto. Per altre informazioni, vedere [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Riepilogo delle prestazioni  
 La tabella seguente mostra le prestazioni dell'aggiornamento front buffer come una funzione del sistema operativo, il formato pixel e bloccabilità surface. Il buffer anteriore e buffer nascosto rientrano nella stessa scheda. A seconda della configurazione di adapter, gli aggiornamenti hardware sono in genere molto più veloci rispetto agli aggiornamenti software.  
  
|Formato pixel della superficie|9Ex, WDDM e Windows Vista|Altre configurazioni di Windows Vista|Windows XP SP3 o SP2 con aggiornamento rapido|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (non bloccabile)|**Aggiornamento dell'hardware**|Aggiornamento software|Aggiornamento software|Aggiornamento software|  
|D3DFMT_X8R8G8B8 (lockable)|**Aggiornamento dell'hardware**|Aggiornamento software|**Aggiornamento dell'hardware**|**Aggiornamento dell'hardware**|  
|D3DFMT_A8R8G8B8 (non bloccabile)|**Aggiornamento dell'hardware**|Aggiornamento software|Aggiornamento software|Aggiornamento software|  
|D3DFMT_A8R8G8B8 (lockable)|**Aggiornamento dell'hardware**|Aggiornamento software|**Aggiornamento dell'hardware**|Aggiornamento software|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Interop.D3DImage>
- [Interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md)
- [Procedura dettagliata: Creazione di contenuto Direct3D9 per l'Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
