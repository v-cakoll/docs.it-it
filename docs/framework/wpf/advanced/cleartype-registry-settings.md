---
title: Impostazioni del Registro di sistema ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: bedd99fcf9b4ca1d10b4c24d7cff9de320e6fd12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186168"
---
# <a name="cleartype-registry-settings"></a>Impostazioni del Registro di sistema ClearType
In questo argomento viene fornita una panoramica delle impostazioni del Registro di sistema Microsoft ClearType utilizzate dalle applicazioni WPFWPF.  

<a name="overview"></a>
## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Le applicazioni che eseguono il rendering del testo su un dispositivo di visualizzazione utilizzano le funzionalità ClearType per offrire un'esperienza di lettura avanzata. ClearType è una tecnologia software sviluppata da Microsoft che migliora la leggibilità del testo sui display LCD (Liquid Crystal Display) esistenti, come schermi di laptop, pocket PC e monitor a pannello piatto. ClearType funziona accedendo ai singoli elementi striscia di colore verticale in ogni pixel di uno schermo LCD. Per ulteriori informazioni su ClearType, vedere Cenni preliminari su [ClearType](cleartype-overview.md).  
  
 Il testo di cui viene eseguito il rendering con ClearType può apparire significativamente diverso quando viene visualizzato su vari dispositivi di visualizzazione. Ad esempio, un piccolo numero di monitor implementa gli elementi striscia di colore in ordine blu, verde, rosso anziché nell'ordine più comune rosso, verde, blu (RGB).  
  
 Il testo di cui viene eseguito il rendering con ClearType può anche apparire significativamente diverso se visualizzato da utenti con diversi livelli di sensibilità al colore. Alcune persone rilevano leggere differenze di colore meglio di altre.  
  
 In ognuno di questi casi, le funzionalità ClearType devono essere modificate per fornire la migliore esperienza di lettura per ogni individuo.  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>Impostazioni Registro di sistema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]specifica quattro impostazioni del Registro di sistema per il controllo delle funzionalità ClearType:  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|Livello ClearType|Descrive il livello di chiarezza dei colori ClearType.|  
|Livello di gamma|Descrive il livello della componente cromatica del pixel per un dispositivo di visualizzazione.|  
|Struttura del pixel|Descrive la disposizione dei pixel per un dispositivo di visualizzazione.|  
|Livello di contrasto del testo|Descrive il livello di contrasto per il testo visualizzato.|  
  
 Queste impostazioni sono accessibili da un'utilità di configurazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esterna che sa come fare riferimento alle impostazioni del Registro di sistema ClearType identificate. Queste impostazioni possono anche essere create o modificate accedendo direttamente ai valori utilizzando l'Editor del Registro di sistema di Windows.  
  
 Se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le impostazioni del Registro di sistema ClearType [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono impostate (che è lo stato predefinito), l'applicazione esegue una query sui parametri di sistema di Windows per le impostazioni di smussatura dei caratteri.  
  
> [!NOTE]
> Per informazioni sull'enumerazione dei `SystemParametersInfo`nomi dei dispositivi di visualizzazione, vedere la funzione Win32.For information on enumerating display device names, see the Win32 function.  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a>Livello ClearType  
 Il livello ClearType consente di regolare il rendering del testo in base alla sensibilità al colore e alla percezione di un individuo. Per alcuni individui, il rendering del testo che utilizza ClearType al livello più alto non produce la migliore esperienza di lettura.  
  
 Il livello ClearType è un valore intero compreso tra 0 e 100.The ClearType level is an integer value that ranges from 0 to 100. Il livello predefinito è 100, il che significa che ClearType utilizza la capacità massima degli elementi striscia di colore del dispositivo di visualizzazione. Tuttavia, un livello ClearType pari a 0 esegue il rendering del testo come scala di grigi. Impostando il livello ClearType tra 0 e 100, è possibile creare un livello intermedio adatto alla sensibilità al colore di un individuo.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso delle impostazioni del Registro di sistema per il livello ClearType è un'impostazione utente individuale che corrisponde a un nome di periferica di visualizzazione specifico:The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di periferica `ClearTypeLevel` di visualizzazione per un utente, viene definito un valore DWORD. La schermata seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello ClearType.The following screenshot shows the Registry Editor setting for the ClearType level.  
  
 ![ClearType nell'Editor del Registro di sistema.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le applicazioni eseguono il rendering del testo in una delle due modalità, con e senza ClearType. Quando il rendering del testo viene eseguito senza ClearType, viene definito rendering in scala di grigi.  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a>Livello di gamma  
 Il livello di gamma fa riferimento alla relazione non lineare tra un valore in pixel e la luminanza. L'impostazione del livello di gamma deve corrispondere alle caratteristiche fisiche del dispositivo di visualizzazione, in caso contrario possono verificarsi distorsioni nell'output del rendering. Ad esempio, il testo potrebbe apparire troppo largo o troppo stretto oppure le frange di colore possono apparire sui bordi degli steli verticali dei glifi.  
  
 Il livello di gamma è un valore intero compreso tra 1000 e 2200. Il livello predefinito è 1900.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per il livello di gamma è un'impostazione del computer locale che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di periferica `GammaLevel` di visualizzazione per un utente, viene definito un valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello di gamma.  
  
 ![ClearType impostazioni del livello gamma nell'Editor del Registro di sistema](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a>Struttura del pixel  
 La struttura del pixel descrive il tipo di pixel alla base di un dispositivo di visualizzazione. La struttura del pixel è definita come uno di tre tipi:  
  
|Type|valore|Descrizione|  
|----------|-----------|-----------------|  
|Semplice|0|Il dispositivo di visualizzazione non ha struttura del pixel. In questo caso le sorgenti di luce per ogni colore sono distribuite in modo uniforme nell'area dei pixel, condizione nota come rendering in scala di grigi. Questo è il funzionamento di un dispositivo di visualizzazione standard. ClearType non viene mai applicato al testo sottoposto a rendering.|  
|RGB|1|Il dispositivo di visualizzazione dispone di pixel costituiti da tre strisce nell'ordine seguente: rosso, verde e blu. ClearType viene applicato al testo sottoposto a rendering.|  
|BGR|2|Il dispositivo di visualizzazione dispone di pixel costituiti da tre strisce nell'ordine seguente: blu, verde e rosso. ClearType viene applicato al testo sottoposto a rendering. Si noti come l'ordine viene invertito rispetto al tipo RGB.|  
  
 La struttura dei pixel corrisponde a un valore intero compreso tra 0 e 2. Il livello predefinito è 0, che rappresenta una struttura del pixel flat.  
  
> [!NOTE]
> Per informazioni sull'enumerazione dei `EnumDisplayDevices`nomi dei dispositivi di visualizzazione, vedere la funzione Win32.For information on enumerating display device names, see the Win32 function.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per la struttura del pixel è un'impostazione del computer locale che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di periferica `PixelStructure` di visualizzazione per un utente, viene definito un valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per la struttura del pixel.  
  
 ![ClearType impostazioni del livello gamma nell'Editor del Registro di sistema](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a>Livello di contrasto del testo  
 Il livello di contrasto del testo consente di regolare il rendering del testo in base alle larghezze del gambo dei glifi. Il livello di contrasto del testo è un valore intero compreso tra 0 e 6, dove il valore più grande indica una maggiore larghezza. Il livello predefinito è 1.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per il livello di contrasto del testo è un'impostazione del singolo utente che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di periferica `TextContrastLevel` di visualizzazione per un utente, viene definito un valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello di contrasto del testo.  
  
 ![ClearType nell'Editor del Registro di sistema.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica su ClearType](cleartype-overview.md)
- [ClearType Antialiasing (Anti-aliasing ClearType)](/windows/desktop/gdi/cleartype-antialiasing)
