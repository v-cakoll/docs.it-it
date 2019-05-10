---
title: "Ottimizzazione delle prestazioni: Sfruttare appieno l'hardware"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
ms.openlocfilehash: d40d1636b510fcfe667ab3e728d1688ce38641d4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611935"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Ottimizzazione delle prestazioni: Sfruttare appieno l'hardware
L'architettura interna di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone di due pipeline di rendering, hardware e software. In questo argomento fornisce informazioni su queste pipeline di rendering che consentono di prendere decisioni sull'ottimizzazione delle prestazioni delle applicazioni.  
  
## <a name="hardware-rendering-pipeline"></a>Pipeline di Rendering hardware  
 Uno dei fattori più importanti nel determinare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] prestazioni sono costituito da rendering associato, ovvero il numero di pixel è necessario eseguire il rendering, maggiore sarà la riduzione delle prestazioni. Tuttavia, più il rendering, che possono essere scaricate per il [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], i vantaggi di prestazioni più avere. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pipeline di rendering hardware applicazione sfrutta appieno [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] funzionalità su hardware che supporta un minimo di [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versione 7.0. Ulteriori ottimizzazioni ottenibili dall'hardware che supporta [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versione 7.0 e le funzionalità PixelShader 2.0.  
  
## <a name="software-rendering-pipeline"></a>Pipeline di Rendering software  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pipeline di rendering software è completamente associata alla CPU. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sfrutta le istruzioni SSE ed SSE2 imposta della CPU per implementare un'unità di rasterizzazione software con funzionalità complete e ottimizzato. Il fallback al software è facile ogni volta la funzionalità dell'applicazione non è possibile eseguire il rendering tramite la pipeline di rendering hardware.  
  
 Il principale problema di prestazioni si verifica quando il rendering in modalità software è correlato alla velocità di riempimento, che è definita come il numero di pixel che si esegue il rendering. Se si è preoccupati per le prestazioni in modalità di rendering software, provare a ridurre al minimo il numero di volte in cui che un pixel viene ridisegnato. Ad esempio, se si dispone di un'applicazione con uno sfondo blu, che quindi esegue il rendering di un'immagine trasparente leggermente posizionato sopra di essa, si forniranno tutti i pixel nell'applicazione due volte. Di conseguenza, saranno necessari due volte a condizione per il rendering dell'applicazione con l'immagine di se è necessario solo lo sfondo blu.  
  
### <a name="graphics-rendering-tiers"></a>Livelli di rendering della grafica  
 Potrebbe essere molto difficile prevedere la configurazione hardware che eseguiranno l'applicazione in. Tuttavia, si potrebbe voler considerare una progettazione che consente all'applicazione scambiare le funzionalità durante l'esecuzione su hardware diverso, in modo che è possibile sfruttare appieno tutte le configurazioni hardware diverse.  
  
 A tale scopo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce funzionalità per determinare le funzionalità grafiche di un sistema in fase di esecuzione. Una funzionalità grafica è determinata dal categorizzazione della scheda video come uno dei tre livelli di funzionalità di rendering. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espone un [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] che consente a un'applicazione eseguire una query il livello di funzionalità di rendering. L'applicazione può quindi accettare i percorsi del codice diversi in fase di esecuzione a seconda del livello di rendering supportato dall'hardware.  
  
 Le funzionalità dell'hardware grafico che hanno effetto sui livelli di rendering sono:  
  
- **RAM video** La quantità di memoria video sull'hardware grafico determina le dimensioni e il numero di buffer che possono essere usati per la composizione della grafica.  
  
- **Pixel shader** Un pixel shader è una funzione di elaborazione grafica che calcola gli effetti sui singoli pixel. A seconda della risoluzione della grafica visualizzata, potrebbe essere necessario elaborare diversi milioni di pixel per ogni fotogramma visualizzato.  
  
- **Vertex shader** Un vertex shader è una funzione di elaborazione grafica che esegue operazioni matematiche sui dati dei vertici dell'oggetto.  
  
- **Supporto per più trame** Il supporto per più trame è la possibilità di applicare due o più trame distinte durante un'operazione di fusione su un oggetto grafico 3D. Il grado di supporto per più trame è determinato dal numero di unità a più trame nell'hardware grafico.  
  
 Il shader pixel, vertex shader e le funzionalità più trame vengono usate per definire specifiche [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] livelli di versione, che a sua volta, vengono usati per definire i diversi livelli di rendering in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Le funzionalità dell'hardware grafico determinano la capacità di rendering di un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definisce tre livelli di rendering:  
  
- **Livello di rendering 0** Nessuna accelerazione hardware grafico. Il [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] a livello di versione è precedente alla versione 7.0.  
  
- **Livello di rendering 1** l'accelerazione hardware grafico parziale. Il [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] a livello di versione è maggiore o uguale alla versione 7.0, e **minore** alla versione 9.0.  
  
- **Livello di rendering 2** La maggior parte delle funzionalità grafiche usa l'accelerazione hardware grafico. Il livello della versione di [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] è superiore o uguale alla versione 9.0.  
  
 Per ulteriori informazioni sul [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] livelli di rendering, vedere [livelli di Rendering della grafica](graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [per](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
