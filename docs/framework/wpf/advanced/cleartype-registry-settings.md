---
title: Impostazioni del Registro di sistema ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 6143cf835cc44a6c6cc50372b2ac1a4d24d65311
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740388"
---
# <a name="cleartype-registry-settings"></a>Impostazioni del Registro di sistema ClearType
In questo argomento viene fornita una panoramica delle impostazioni del registro di sistema di Microsoft ClearType utilizzate dalle applicazioni WPF.  

<a name="overview"></a>   
## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni che eseguono il rendering del testo in un dispositivo di visualizzazione utilizzano le funzionalità ClearType per offrire un'esperienza di lettura avanzata. ClearType è una tecnologia software sviluppata da Microsoft che consente di migliorare la leggibilità del testo sugli schermi LCD (Liquid Crystal Display), ad esempio schermi portatili, schermate Pocket PC e monitor Flat Panel. ClearType funziona tramite l'accesso ai singoli elementi stripe dei colori verticali in ogni pixel di uno schermo LCD. Per ulteriori informazioni su ClearType, vedere [Cenni preliminari su ClearType](cleartype-overview.md).  
  
 Il testo di cui è stato eseguito il rendering con ClearType può apparire significativamente diverso quando viene visualizzato in diversi dispositivi di visualizzazione. Ad esempio, un numero ridotto di monitoraggi implementa gli elementi stripe dei colori in ordine blu, verde, rosso anziché l'ordine rosso, verde, blu (RGB) più comune.  
  
 Il testo di cui è stato eseguito il rendering con ClearType può anche essere significativamente diverso quando viene visualizzato da utenti con diversi livelli di sensibilità del colore. Alcune persone rilevano leggere differenze di colore meglio di altre.  
  
 In ognuno di questi casi, è necessario modificare le funzionalità ClearType per fornire la migliore esperienza di lettura per ogni singolo utente.  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Impostazioni Registro di sistema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] specifica quattro impostazioni del registro di sistema per il controllo delle funzionalità ClearType:  
  
|Impostazione di|Descrizione|  
|-------------|-----------------|  
|Livello ClearType|Descrive il livello di chiarezza dei colori ClearType.|  
|Livello di gamma|Descrive il livello della componente cromatica del pixel per un dispositivo di visualizzazione.|  
|Struttura del pixel|Descrive la disposizione dei pixel per un dispositivo di visualizzazione.|  
|Livello di contrasto del testo|Descrive il livello di contrasto per il testo visualizzato.|  
  
 È possibile accedere a queste impostazioni mediante un'utilità di configurazione esterna in grado di fare riferimento alle impostazioni del registro di sistema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType identificato. È possibile creare o modificare queste impostazioni anche accedendo direttamente ai valori usando l'editor del registro di sistema di Windows.  
  
 Se le impostazioni del registro di sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType non sono impostate (ovvero lo stato predefinito), l'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue una query sulle informazioni sui parametri di sistema di Windows per le impostazioni di smussatura dei caratteri.  
  
> [!NOTE]
> Per informazioni sull'enumerazione dei nomi dei dispositivi di visualizzazione, vedere la `SystemParametersInfo`funzione Win32.  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>Livello ClearType  
 Il livello ClearType consente di modificare il rendering del testo in base alla sensibilità del colore e alla percezione di un singolo utente. Per alcune persone, il rendering del testo che usa ClearType al livello più alto non produce la migliore esperienza di lettura.  
  
 Il livello ClearType è un valore intero compreso tra 0 e 100. Il livello predefinito è 100, che indica che ClearType utilizza la funzionalità massima degli elementi stripe del dispositivo di visualizzazione. Tuttavia, un livello ClearType pari a 0 esegue il rendering del testo come scala di grigi. Impostando il livello ClearType in un punto compreso tra 0 e 100, è possibile creare un livello intermedio adatto alla sensibilità del colore di un utente.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del registro di sistema per il livello ClearType è una singola impostazione utente che corrisponde a un nome di dispositivo di visualizzazione specifico:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo visualizzato per un utente, viene definito un `ClearTypeLevel` valore DWORD. Lo screenshot seguente mostra l'impostazione dell'editor del registro di sistema per il livello ClearType.  
  
 ![Impostazioni ClearType nell'editor del registro di sistema.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eseguono il rendering del testo in una delle due modalità, con e senza ClearType. Quando viene eseguito il rendering del testo senza ClearType, viene definito rendering in scala di grigi.  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>Livello di gamma  
 Il livello di gamma fa riferimento alla relazione non lineare tra un valore in pixel e la luminanza. L'impostazione del livello di gamma deve corrispondere alle caratteristiche fisiche del dispositivo di visualizzazione, in caso contrario possono verificarsi distorsioni nell'output del rendering. Ad esempio, il testo potrebbe sembrare troppo ampio o troppo piccolo oppure le frange dei colori possono apparire sui bordi delle steli verticali dei glifi.  
  
 Il livello di gamma è un valore intero compreso tra 1000 e 2200. Il livello predefinito è 1900.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per il livello di gamma è un'impostazione del computer locale che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo visualizzato per un utente, viene definito un `GammaLevel` valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello di gamma.  
  
 ![Impostazioni a livello di gamma ClearType nell'editor del registro di sistema](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>Struttura del pixel  
 La struttura del pixel descrive il tipo di pixel alla base di un dispositivo di visualizzazione. La struttura del pixel è definita come uno di tre tipi:  
  
|Tipo di|Valore|Descrizione|  
|----------|-----------|-----------------|  
|Semplice|0|Il dispositivo di visualizzazione non ha struttura del pixel. In questo caso le sorgenti di luce per ogni colore sono distribuite in modo uniforme nell'area dei pixel, condizione nota come rendering in scala di grigi. Questo è il funzionamento di un dispositivo di visualizzazione standard. ClearType non viene mai applicato al testo sottoposto a rendering.|  
|RGB|1|Il dispositivo di visualizzazione dispone di pixel costituiti da tre strisce nell'ordine seguente: rosso, verde e blu. ClearType viene applicato al testo sottoposto a rendering.|  
|BGR|2|Il dispositivo di visualizzazione dispone di pixel costituiti da tre strisce nell'ordine seguente: blu, verde e rosso. ClearType viene applicato al testo sottoposto a rendering. Si noti come l'ordine viene invertito rispetto al tipo RGB.|  
  
 La struttura dei pixel corrisponde a un valore intero compreso tra 0 e 2. Il livello predefinito è 0, che rappresenta una struttura del pixel flat.  
  
> [!NOTE]
> Per informazioni sull'enumerazione dei nomi dei dispositivi di visualizzazione, vedere la `EnumDisplayDevices`funzione Win32.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per la struttura del pixel è un'impostazione del computer locale che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo visualizzato per un utente, viene definito un `PixelStructure` valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per la struttura del pixel.  
  
 ![Impostazioni a livello di gamma ClearType nell'editor del registro di sistema](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>Livello di contrasto del testo  
 Il livello di contrasto del testo consente di regolare il rendering del testo in base alle larghezze del gambo dei glifi. Il livello di contrasto del testo è un valore intero compreso tra 0 e 6, dove il valore più grande indica una maggiore larghezza. Il livello predefinito è 1.  
  
### <a name="registry-setting"></a>Impostazione del Registro di sistema  
 Il percorso dell'impostazione del Registro di sistema per il livello di contrasto del testo è un'impostazione del singolo utente che corrisponde al nome di uno specifico dispositivo di visualizzazione:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Per ogni nome di dispositivo visualizzato per un utente, viene definito un `TextContrastLevel` valore DWORD. Lo screenshot seguente mostra l'impostazione dell'Editor del Registro di sistema per il livello di contrasto del testo.  
  
 ![Impostazioni ClearType nell'editor del registro di sistema.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica su ClearType](cleartype-overview.md)
- [ClearType Antialiasing (Anti-aliasing ClearType)](/windows/desktop/gdi/cleartype-antialiasing)
