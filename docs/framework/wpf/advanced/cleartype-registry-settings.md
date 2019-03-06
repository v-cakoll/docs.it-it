---
title: Impostazioni del Registro di sistema ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 471a94333260d30bc9c650f13e3a7489d9d5db7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369721"
---
# <a name="cleartype-registry-settings"></a>Impostazioni del Registro di sistema ClearType
In questo argomento viene fornita una panoramica di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] le impostazioni del Registro di sistema usate dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni.  
  
  
<a name="overview"></a>   
## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni che eseguono il rendering di testo da un dispositivo di visualizzazione usano [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] funzionalità per fornire una migliore esperienza di lettura. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] è una tecnologia software sviluppata da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] che consente di migliorare la leggibilità del testo sui display LCD (Liquid Crystal Display), ad esempio gli schermi di computer portatili, Pocket PC e i monitor a schermo piatto. Il funzionamento della tecnologia [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] si basa sull'accesso a singoli elementi striscia di colore verticali in ogni pixel di uno schermo LCD. Per ulteriori informazioni sul [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], vedere [Cenni preliminari su ClearType](cleartype-overview.md).  
  
 Testo che viene eseguito il rendering con [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] può avere un aspetto diverso quando viene visualizzato nei vari dispositivi di visualizzazione. Ad esempio, un numero limitato di monitor implementa gli elementi striscia di colore nell'ordine blu, verde, rosso anziché il più comune rosso, verde, blu ( [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) ordine.  
  
 Testo che viene eseguito il rendering con [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] può anche avere un aspetto diverso quando viene visualizzato da persone con diversi livelli di sensibilità al colore. Alcune persone rilevano leggere differenze di colore meglio di altre.  
  
 In ognuno di questi casi, [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] funzionalità devono essere modificate per fornire un'esperienza di lettura per ogni singolo cliente.  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Impostazioni Registro di sistema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Specifica quattro impostazioni del Registro di sistema per il controllo [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] funzionalità:  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|Livello [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]|Descrive il livello di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] chiarezza del colore.|  
|Livello di gamma|Descrive il livello della componente cromatica del pixel per un dispositivo di visualizzazione.|  
|Struttura del pixel|Descrive la disposizione dei pixel per un dispositivo di visualizzazione.|  
|Livello di contrasto del testo|Descrive il livello di contrasto per il testo visualizzato.|  
  
 Queste impostazioni sono accessibili tramite un'utilità di configurazione esterno che sa come fare riferimento l'oggetto identificato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] le impostazioni del Registro di sistema. Per creare o modificare queste impostazioni, è possibile accedere ai valori direttamente usando l'editor del Registro di sistema di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 Se il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] le impostazioni del Registro di sistema non vengono impostate (stato predefinito), il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le query dell'applicazione di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] le informazioni sui parametri di sistema per le impostazioni di smussatura dei caratteri.  
  
> [!NOTE]
>  Per informazioni sull'enumerazione dei nomi dei dispositivi di visualizzazione, vedere la `SystemParametersInfo` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (funzione).  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>Livello ClearType  
 Il [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] livello consente di regolare il rendering del testo in base alla sensibilità al colore e alla percezione di un individuo. Per alcune persone, il rendering del testo che usa [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] al livello più alto non consente di produrre la migliore esperienza di lettura.  
  
 Il [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] livello è un valore intero compreso tra 0 e 100. Il livello predefinito è 100, ovvero [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] della capacità massima degli elementi striscia di colore della periferica di visualizzazione. Tuttavia, un [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] livello pari a 0 esegue il rendering di testo in scala di grigi. Impostando il [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] livello in un punto compreso tra 0 e 100, è possibile creare un livello intermedio adatto alla sensibilità al colore dei singoli.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso di impostazione del Registro di sistema per il [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] livello è un'impostazione del singolo utente che corrisponde a un nome di dispositivo di visualizzazione specifici:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo di visualizzazione per un utente, un `ClearTypeLevel` viene definito valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] livello.  
  
 ![Impostazioni ClearType nell'Editor del Registro di sistema](./media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni il rendering del testo in una delle due due modalità, con e senza [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]. Quando viene eseguito rendering del testo senza [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], si intende per il rendering in scala di grigi.  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>Livello di gamma  
 Il livello di gamma fa riferimento alla relazione non lineare tra un valore in pixel e la luminanza. L'impostazione del livello di gamma deve corrispondere alle caratteristiche fisiche del dispositivo di visualizzazione, in caso contrario possono verificarsi distorsioni nell'output del rendering. Ad esempio, il testo potrebbe risultare troppo largo o troppo stretto o è possibile che compaiano sbavature di colore sui bordi dei gambi verticali dei glifi.  
  
 Il livello di gamma è un valore intero compreso tra 1000 e 2200. Il livello predefinito è 1900.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per il livello di gamma è un'impostazione del computer locale che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo di visualizzazione per un utente, un `GammaLevel` viene definito valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello di gamma.  
  
 ![Impostazioni ClearType nell'Editor del Registro di sistema](./media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>Struttura del pixel  
 La struttura del pixel descrive il tipo di pixel alla base di un dispositivo di visualizzazione. La struttura del pixel è definita come uno di tre tipi:  
  
|Tipo|Value|Descrizione|  
|----------|-----------|-----------------|  
|Semplice|0|Il dispositivo di visualizzazione non ha struttura del pixel. In questo caso le sorgenti di luce per ogni colore sono distribuite in modo uniforme nell'area dei pixel, condizione nota come rendering in scala di grigi. Questo è il funzionamento di un dispositivo di visualizzazione standard. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] non viene mai applicato al testo di cui si esegue il rendering.|  
|RGB|1|Il dispositivo di visualizzazione dispone di pixel costituiti da tre strisce nell'ordine seguente: rosso, verde e blu. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] viene applicato al testo di cui si esegue il rendering.|  
|BGR|2|Il dispositivo di visualizzazione dispone di pixel costituiti da tre strisce nell'ordine seguente: blu, verde e rosso. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] viene applicato al testo di cui si esegue il rendering. Si noti come l'ordine viene invertito rispetto al tipo RGB.|  
  
 La struttura dei pixel corrisponde a un valore intero compreso tra 0 e 2. Il livello predefinito è 0, che rappresenta una struttura del pixel flat.  
  
> [!NOTE]
>  Per informazioni sull'enumerazione dei nomi dei dispositivi di visualizzazione, vedere la `EnumDisplayDevices` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (funzione).  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per la struttura del pixel è un'impostazione del computer locale che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo di visualizzazione per un utente, un `PixelStructure` viene definito valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per la struttura del pixel.  
  
 ![Impostazioni ClearType nell'Editor del Registro di sistema](./media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>Livello di contrasto del testo  
 Il livello di contrasto del testo consente di regolare il rendering del testo in base alle larghezze del gambo dei glifi. Il livello di contrasto del testo è un valore intero compreso tra 0 e 6, dove il valore più grande indica una maggiore larghezza. Il livello predefinito è 1.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per il livello di contrasto del testo è un'impostazione del singolo utente che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo di visualizzazione per un utente, un `TextContrastLevel` viene definito valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello di contrasto del testo.  
  
 ![Impostazioni ClearType nell'Editor del Registro di sistema](./media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica su ClearType](cleartype-overview.md)
- [ClearType Antialiasing (Anti-aliasing ClearType)](/windows/desktop/gdi/cleartype-antialiasing)
