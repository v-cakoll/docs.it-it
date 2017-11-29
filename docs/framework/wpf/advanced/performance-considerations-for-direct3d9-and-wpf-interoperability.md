---
title: "Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 886ef6c8c9df9d14b5c2a805da2e3948d5e55f69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF
È possibile ospitare contenuto Direct3D9 utilizzando la <xref:System.Windows.Interop.D3DImage> classe. Hosting di contenuto Direct3D9 influire sulle prestazioni dell'applicazione. In questo argomento vengono descritte le procedure consigliate per ottimizzare le prestazioni quando si ospita il contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF). Queste procedure consigliate per la modalità di utilizzo <xref:System.Windows.Interop.D3DImage> e procedure consigliate quando si utilizza Windows Vista, Windows XP, e viene visualizzato con più monitor.  
  
> [!NOTE]
>  Per esempi di codice che illustrano le procedure consigliate, vedere [interoperatività di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Utilizzare con cautela D3DImage  
 Contenuto Direct3D9 ospitato in un <xref:System.Windows.Interop.D3DImage> istanza non esegue il rendering con la stessa velocità come in un'applicazione Direct3D pura. Area di copia e lo scaricamento buffer dei comandi possono essere operazioni costose. Come il numero di <xref:System.Windows.Interop.D3DImage> aumento di istanze, viene eseguita una svuotamento aumentano e comporta una riduzione delle prestazioni. Pertanto, è necessario utilizzare <xref:System.Windows.Interop.D3DImage> con cautela.  
  
## <a name="best-practices-on-windows-vista"></a>Procedure consigliate in Windows Vista  
 Per prestazioni ottimali in Windows Vista con un display configurato per l'utilizzo di Windows Driver Model (WDDM Display), creare la superficie Direct3D9 in un `IDirect3DDevice9Ex` dispositivo. In questo modo la condivisione della superficie. La scheda video deve supportare il `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` e `D3DCAPS2_CANSHARERESOURCE` le funzionalità del driver in Windows Vista. Tutte le altre impostazioni causano la superficie viene copiata attraverso il software, che riduce significativamente le prestazioni.  
  
> [!NOTE]
>  Se Windows Vista ha una visualizzazione che è configurata per l'utilizzo di Windows XP Driver XDDM (Display Model), la superficie viene sempre copiata tramite software, indipendentemente dalle impostazioni. Con le impostazioni appropriate e la scheda video si noteranno prestazioni migliori in Windows Vista quando si utilizza WDDM perché le copie della superficie vengono eseguite nell'hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Procedure consigliate in Windows XP  
 Per prestazioni ottimali in Windows XP, che utilizza il Windows XP Visualizza modello XDDM (Driver), creare una superficie bloccabile che si comporti correttamente quando il `IDirect3DSurface9::GetDC` metodo viene chiamato. Internamente, il `BitBlt` metodo trasferisce la superficie tra i dispositivi hardware. Il `GetDC` metodo funziona sempre sulle superfici XRGB. Tuttavia, se il computer client è in esecuzione Windows XP con SP3 o SP2, e se il client ha anche l'aggiornamento rapido per la funzionalità di finestre sovrapposte, questo metodo funziona solo sulle superfici ARGB. La scheda video deve supportare il `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` funzionalità del driver.  
  
 Una profondità di visualizzazione del desktop a 16 bit può ridurre notevolmente le prestazioni. È consigliabile un desktop a 32 bit.  
  
 Se si sviluppa per Windows Vista e Windows XP, è possibile testare le prestazioni in Windows XP. Esaurimento di memoria video in Windows XP è un problema. Inoltre, <xref:System.Windows.Interop.D3DImage> in Windows XP Usa più memoria video e larghezza di banda rispetto a Windows Vista WDDM, a causa di una copia di memoria video aggiuntiva necessaria. Pertanto, è possibile prevedere prestazioni peggiori in Windows XP rispetto a Windows Vista per lo stesso hardware video.  
  
> [!NOTE]
>  XDDM è disponibile in Windows XP e Windows Vista. Tuttavia, WDDM è disponibile solo in Windows Vista.  
  
## <a name="general-best-practices"></a>Procedure consigliate generali  
 Quando si crea il dispositivo, utilizzare il `D3DCREATE_MULTITHREADED` flag di creazione. Ciò riduce le prestazioni, ma il sistema di rendering WPF chiama i metodi su questo dispositivo da un altro thread. Assicurarsi di seguire il protocollo di blocco in modo corretto, in modo che nessun due thread di accedere al dispositivo nello stesso momento.  
  
 Se il rendering viene eseguito in un thread gestito da WPF, è consigliabile creare il dispositivo con il `D3DCREATE_FPU_PRESERVE` flag di creazione. Senza questa impostazione, il rendering D3D può ridurre l'accuratezza di operazioni a precisione doppia WPF e comportare problemi di rendering.  
  
 Affiancamento un <xref:System.Windows.Interop.D3DImage> è veloce, a meno che non è affiancare un'area di non-pow2 senza supporto hardware o se è affiancare un <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> che contiene un <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Procedure consigliate per visualizzazioni con più monitor  
 Se si utilizza un computer che dispone di più monitor, è necessario seguire le procedure consigliate descritte in precedenza. Esistono inoltre alcune considerazioni sulle prestazioni per una configurazione di più monitor.  
  
 Quando si crea il buffer nascosto, viene creato in un dispositivo specifico e l'adapter ma WPF visualizzi il front buffer in qualsiasi scheda. Copia tra le schede per aggiornare il front-buffer può risultare molto costosa. In Windows Vista, è configurato per l'utilizzo di WDDM con più schede video e con un `IDirect3DDevice9Ex` dispositivo, se il buffer anteriore è su una scheda differente ma con la stessa scheda video, non vi è alcuna riduzione delle prestazioni. Tuttavia, in Windows XP e la XDDM con più schede video, è una riduzione significativa delle prestazioni quando il buffer anteriore viene visualizzato in una scheda diversa rispetto al buffer nascosto. Per ulteriori informazioni, vedere [interoperatività di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Riepilogo delle prestazioni  
 La tabella seguente mostra le prestazioni dell'aggiornamento buffer front-come funzione di sistema operativo, il formato pixel e bloccabilità superficie di attacco. Il front buffer e buffer nascosto vengono considerati nella stessa scheda. A seconda della configurazione di adapter, gli aggiornamenti hardware sono in genere molto più veloci gli aggiornamenti software.  
  
|Formato pixel della superficie|9Ex, WDDM e Windows Vista|Altre configurazioni di Windows Vista|Windows XP SP3 o SP2 con aggiornamento rapido|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (non bloccabile)|**Aggiornamento dell'hardware**|Aggiornamento software|Aggiornamento software|Aggiornamento software|  
|D3DFMT_X8R8G8B8 (bloccabile)|**Aggiornamento dell'hardware**|Aggiornamento software|**Aggiornamento dell'hardware**|**Aggiornamento dell'hardware**|  
|D3DFMT_A8R8G8B8 (non bloccabile)|**Aggiornamento dell'hardware**|Aggiornamento software|Aggiornamento software|Aggiornamento software|  
|D3DFMT_A8R8G8B8 (bloccabile)|**Aggiornamento dell'hardware**|Aggiornamento software|**Aggiornamento dell'hardware**|Aggiornamento software|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.D3DImage>  
 [Interoperatività di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)  
 [Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
