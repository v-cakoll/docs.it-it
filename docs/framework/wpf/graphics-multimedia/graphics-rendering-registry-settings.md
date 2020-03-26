---
title: Impostazioni del Registro di sistema per il rendering della grafica
ms.date: 03/30/2017
helpviewer_keywords:
- rendering graphics [WPF], registry settings
- rendering graphics [WPF]
- rendering graphics [WPF], troubleshooting
- troubleshooting graphics rendering [WPF]
- graphics [WPF], rendering
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
ms.openlocfilehash: 642dfdd784af4b85672cf5b0c8e60079763f4c47
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112284"
---
# <a name="graphics-rendering-registry-settings"></a>Impostazioni del Registro di sistema per il rendering della grafica
Questo argomento fornisce una panoramica delle impostazioni del Registro di sistema per il rendering della grafica di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che influiscono sulle applicazioni di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="overview"></a>
## <a name="when-to-use-graphics-rendering-registry-settings"></a>Quando usare le impostazioni del Registro di sistema per il rendering della grafica  
 Queste impostazioni del Registro di sistema vengono fornite per la risoluzione dei problemi, il debug e supporto per il prodotto. Poiché le modifiche al Registro di sistema influiscono su tutte le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], l'applicazione non deve mai modificare queste chiavi del Registro di sistema, automaticamente o durante l'installazione.  
  
<a name="xpdmandwddm"></a>
## <a name="what-are-xpdm-and-wddm"></a>Definizione di XPDM e WDDM  
 Alcune impostazioni del Registro di sistema per il rendering della grafica hanno valori predefiniti diversi, a seconda che la scheda video usi un driver XPDM o WDDM. XPDM è Microsoft Windows XP Display Driver Model e WDDM è il modello di driver video di Windows. WDDM è disponibile nei computer che eseguono Windows Vista e Windows 7. XPDM è disponibile nei computer che eseguono Windows Vista, Microsoft Windows XP e Microsoft Windows Server 2003. Per ulteriori informazioni su WDDM, vedere Guida alla progettazione di [Windows Display Driver Model (WDDM).](/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide)  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>Impostazioni Registro di sistema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce quattro impostazioni del Registro di sistema per controllare il rendering [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|**Opzione per la disabilitazione dell'accelerazione hardware**|Specifica se l'accelerazione hardware deve essere abilitata.|  
|**Valore massimo di multicampionamento**|Specifica il grado di campionamento multiplo per l'antialiasing del contenuto 3D.|  
|**Impostazione Data driver video necessaria**|Specifica se il sistema disabilita l'accelerazione hardware per i driver rilasciati prima di novembre 2004.|  
|**Opzione per l'uso di unità di rasterizzazione dei riferimenti**|Specifica se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deve usare l'unità di rasterizzazione dei riferimenti.|  
  
 A queste impostazioni è possibile accedere tramite qualsiasi utilità di configurazione esterna che possa fare riferimento alle impostazioni del Registro di sistema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste impostazioni possono anche essere create o modificate accedendo direttamente ai valori utilizzando l'Editor del Registro di sistema di Windows.  
  
<a name="disablehardwareacceleration"></a>
## <a name="disable-hardware-acceleration-option"></a>Opzione per la disabilitazione dell'accelerazione hardware  
  
|Chiave del Registro di sistema|Tipo di valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|DWORD|  
  
 L'**opzione di disabilitazione dell'accelerazione hardware** consente di disattivare l'accelerazione hardware per scopi di debug e test. Se in un'applicazione si vedono elementi di rendering, provare a disattivare l'accelerazione hardware. Se l'elemento scompare, potrebbe trattarsi di un problema con il driver video.  
  
 L'**opzione di disabilitazione dell'accelerazione hardware** è un valore DWORD che è 0 o 1. Il valore 1 disabilita l'accelerazione hardware. Il valore 0 consente l'accelerazione hardware, purché il sistema soddisfi i requisiti di accelerazione hardware. Per altre informazioni, vedere [Livelli di rendering della grafica](../advanced/graphics-rendering-tiers.md).  
  
<a name="maxmultisample"></a>
## <a name="maximum-multisample-value"></a>Valore massimo di multicampionamento  
  
|Chiave del Registro di sistema|Tipo di valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|DWORD|  
  
 Il **valore multicampione massimo** consente di regolare la quantità massima di antialiasing del contenuto 3D. Utilizzare questo livello per disabilitare l'antialiasing 3D in Windows Vista.  
  
 Il **valore massimo di multicampionamento** è un valore DWORD che va da 0 a 16. Un valore pari a 0 specifica che l'antialiasing multicampione del contenuto 3D deve essere disabilitato e un valore pari a 16 tenterà di utilizzare fino a 16 volte l'antialiasing multicampione, se supportato dalla scheda video. Tenere presente che l'impostazione di questo valore della chiave del Registro di sistema nei computer che utilizzano driver XPDM causerà l'utilizzo di una grande quantità di memoria video aggiuntiva da parte delle applicazioni, la riduzione delle prestazioni del rendering 3D e l'utilizzo di errori di rendering e stabilità Problemi.  
  
 Quando questa chiave del Registro di sistema non è impostata, il valore predefinito di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è 0 per i driver XPDM e 4 per i driver WDDM.  
  
<a name="requiredvideodriverdatesetting"></a>
## <a name="required-video-driver-date-setting"></a>Impostazione Data driver video necessaria  
  
|Chiave del Registro di sistema|Tipo di valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|string|  
  
 Nel novembre 2004, Microsoft ha rilasciato una nuova versione delle linee guida per il test dei driver; i driver scritti dopo questa data offrono una migliore stabilità. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa la pipeline di accelerazione hardware per questi driver ed esegue il fallback al rendering del software per driver XPDM pubblicati prima di tale data.  
  
 L'**impostazione Data driver video necessaria** consente di specificare una data alternativa minima per i driver XPDM. È necessario specificare solo una data precedente a novembre 2004 se si è certi che il driver video è sufficientemente stabile per supportare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 L'impostazione necessaria per il driver video accetta una stringa nel formato seguente:  
  
| |  
|-|  
|*AAAA* `/` *MM* `/` *GG*|  
  
 Dove *AAAA* è l'anno a quattro cifre, *MM* è il mese a due cifre, e *GG* è il giorno a due cifre. Se questo valore non è impostato, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa novembre 2004 come data necessaria del driver video.  
  
<a name="usereferencerasterizeroption"></a>
## <a name="use-reference-rasterizer-option"></a>Opzione per l'uso di unità di rasterizzazione dei riferimenti  
  
|Chiave del Registro di sistema|Tipo di valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|DWORD|  
  
 **L'opzione Usa rasterizzatore** di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] riferimento consente di forzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una modalità di rendering hardware simulata per il debug: passa alla modalità hardware, ma usa l'unità di rasterizzazione software di riferimento Microsoft Direct3D, d3dref9.dll, anziché un dispositivo hardware effettivo.  
  
 L'unità di rasterizzazione dei riferimenti è molto lenta, ma ignora il driver video per evitare eventuali problemi di rendering causati da problemi del driver. Per questo motivo, usare l'unità di rasterizzazione dei riferimenti per determinare se i problemi di rendering sono causati dal driver video. Il file d3dref9. dll deve essere in una posizione a cui l'applicazione può accedere, ad esempio una posizione qualsiasi nel percorso di sistema o nella directory locale dell'applicazione.  
  
 L'**opzione per l'uso di unità di rasterizzazione dei riferimenti** accetta un valore DWORD. Il valore 0 indica che l'unità di rasterizzazione dei riferimenti non viene usata. Qualsiasi altro valore diverso da zero forza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a usare l'unità di rasterizzazione dei riferimenti.  
  
## <a name="see-also"></a>Vedere anche

- [Livelli di rendering della grafica](../advanced/graphics-rendering-tiers.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
