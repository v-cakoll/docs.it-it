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
ms.openlocfilehash: 7acf5a3f48ac4987037873c63111d988ec3a4979
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629657"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Ottimizzazione delle prestazioni: Sfruttare appieno l'hardware
L'architettura interna di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone di due pipeline di rendering, hardware e software. In questo argomento vengono fornite informazioni su queste pipeline di rendering che consentono di prendere decisioni in merito alle ottimizzazioni delle prestazioni delle applicazioni.  
  
## <a name="hardware-rendering-pipeline"></a>Pipeline di rendering hardware  
 Uno dei fattori più importanti per determinare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le prestazioni è che è associato al rendering, maggiore è il numero di pixel di cui è necessario eseguire il rendering, maggiore è il costo delle prestazioni. Tuttavia, maggiore è il rendering che può essere ripartito [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)]in, i vantaggi in termini di prestazioni che è possibile ottenere. La [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pipeline di rendering hardware dell'applicazione sfrutta appieno le funzionalità di Microsoft DirectX su hardware che supporta almeno Microsoft DirectX versione 7,0. Ulteriori ottimizzazioni possono essere ottenute con hardware che supporta le funzionalità di Microsoft DirectX versione 7,0 e PixelShader 2.0 +.  
  
## <a name="software-rendering-pipeline"></a>Pipeline di rendering software  
 La [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pipeline di rendering software è interamente associata alla CPU. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]sfrutta i set di istruzioni SSE e SSE2 nella CPU per implementare un'rasterizzatore software ottimizzato e con funzionalità complete. Il fallback al software è facile ogni volta che non è possibile eseguire il rendering della funzionalità dell'applicazione utilizzando la pipeline di rendering hardware.  
  
 Il problema di prestazioni più grande che si verificherà quando il rendering in modalità software è correlato alla velocità di riempimento, definita come il numero di pixel di cui si esegue il rendering. Se si è interessati alle prestazioni in modalità di rendering software, provare a ridurre al minimo il numero di volte in cui un pixel viene ridisegnato. Se, ad esempio, si dispone di un'applicazione con uno sfondo blu, che quindi esegue il rendering di un'immagine leggermente trasparente su di essa, si eseguirà il rendering di tutti i pixel nell'applicazione due volte. Di conseguenza, il rendering dell'applicazione con l'immagine verrà eseguito il doppio rispetto a quando si dispone solo dello sfondo blu.  
  
### <a name="graphics-rendering-tiers"></a>Livelli di rendering della grafica  
 Potrebbe essere molto difficile prevedere la configurazione hardware in cui verrà eseguita l'applicazione. Tuttavia, potrebbe essere opportuno prendere in considerazione una progettazione che consenta all'applicazione di cambiare facilmente le funzionalità quando vengono eseguite su hardware diverso, in modo che sia possibile sfruttare appieno tutte le diverse configurazioni hardware.  
  
 A tale scopo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce la funzionalità per determinare la funzionalità grafica di un sistema in fase di esecuzione. La funzionalità grafica è determinata dalla categorizzazione della scheda video come uno dei tre livelli di funzionalità di rendering. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]espone un'API che consente a un'applicazione di eseguire query sul livello di funzionalità di rendering. L'applicazione può quindi usare percorsi di codice diversi in fase di esecuzione a seconda del livello di rendering supportato dall'hardware.  
  
 Le funzionalità dell'hardware grafico che hanno effetto sui livelli di rendering sono:  
  
- **RAM video** La quantità di memoria video sull'hardware grafico determina le dimensioni e il numero di buffer che possono essere usati per la composizione della grafica.  
  
- **Pixel shader** Un pixel shader è una funzione di elaborazione grafica che calcola gli effetti sui singoli pixel. A seconda della risoluzione della grafica visualizzata, potrebbe essere necessario elaborare diversi milioni di pixel per ogni fotogramma visualizzato.  
  
- **Vertex shader** Un vertex shader è una funzione di elaborazione grafica che esegue operazioni matematiche sui dati dei vertici dell'oggetto.  
  
- **Supporto per più trame** Il supporto per più trame è la possibilità di applicare due o più trame distinte durante un'operazione di fusione su un oggetto grafico 3D. Il grado di supporto per più trame è determinato dal numero di unità a più trame nell'hardware grafico.  
  
 Le funzionalità pixel shader, vertex shader e multitexture vengono usate per definire livelli di versione DirectX specifici, che, a loro volta, vengono usati per definire i diversi livelli di rendering in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Le funzionalità dell'hardware grafico determinano la capacità di rendering di un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definisce tre livelli di rendering:  
  
- **Livello di rendering 0** Nessuna accelerazione hardware grafico. Il livello della versione di DirectX è inferiore alla versione 7,0.  
  
- **Livello di rendering 1** Accelerazione hardware grafica parziale. Il livello della versione di DirectX è maggiore o uguale alla versione 7,0 e **inferiore** alla versione 9,0.  
  
- **Livello di rendering 2** La maggior parte delle funzionalità grafiche usa l'accelerazione hardware grafico. Il livello della versione di DirectX è maggiore o uguale alla versione 9,0.  
  
 Per altre informazioni sui [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] livelli di rendering, vedere [livelli di rendering della grafica](graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
