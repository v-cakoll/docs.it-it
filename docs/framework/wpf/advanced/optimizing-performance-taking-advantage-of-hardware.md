---
title: "Ottimizzazione delle prestazioni: sfruttare appieno l'hardware"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
ms.openlocfilehash: eb790da63b4636e3dd6c25ea118075304702acc0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Ottimizzazione delle prestazioni: sfruttare appieno l'hardware
Architettura interna di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta due pipeline di rendering, hardware e software. In questo argomento fornisce informazioni su queste pipeline di rendering che consentono di prendere decisioni relative all'ottimizzazione delle prestazioni delle applicazioni.  
  
## <a name="hardware-rendering-pipeline"></a>Pipeline di Rendering hardware  
 Uno dei fattori più importanti nel determinare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] prestazioni sono che sono associate al rendering, ovvero il numero di pixel è necessario eseguire il rendering, maggiore sarà l'impatto sulle prestazioni. Tuttavia, più il rendering, che possono essere scaricate per il [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], i vantaggi delle prestazioni ulteriori vantaggi. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pipeline di rendering hardware dell'applicazione si avvale delle [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] funzionalità hardware che supporta un minimo di [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versione 7.0. Ulteriori ottimizzazioni ottenibili dall'hardware che supporta [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] versione 7.0 e le funzionalità di PixelShader 2.0.  
  
## <a name="software-rendering-pipeline"></a>Pipeline di Rendering software  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pipeline di rendering software è completamente associata alla CPU. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sfrutta i vantaggi dell'istruzione di istruzioni SSE ed SSE2 imposta della CPU per implementare un'unità di rasterizzazione software ottimizzata e con funzionalità complete. Il fallback al software è trasparente ogni volta che la funzionalità dell'applicazione non è possibile eseguire il rendering tramite la pipeline di rendering hardware.  
  
 Il problema di prestazioni principale si verifica quando il rendering in modalità software corrisponde alla velocità di riempimento, che è definita come numero di pixel che si esegue il rendering. Se desidera massimizzare le prestazioni in modalità di rendering software, provare a ridurre al minimo il numero di volte in cui che un pixel viene ridisegnato. Ad esempio, se si dispone di un'applicazione con uno sfondo blu, che esegue il rendering di un'immagine leggermente trasparente su di essa, si eseguirà il rendering tutti i pixel nell'applicazione due volte. Di conseguenza, saranno necessari due volte a condizione per il rendering dell'applicazione con l'immagine di se è necessario solo lo sfondo blu.  
  
### <a name="graphics-rendering-tiers"></a>Livelli di rendering della grafica  
 Può risultare molto difficile da prevedere la configurazione hardware che l'applicazione verrà eseguita in. Tuttavia, è consigliabile considerare una progettazione che consente all'applicazione di scambiare funzionalità durante l'esecuzione su hardware diverso, in modo che è possibile usufruire di tutte le configurazioni hardware diverse.  
  
 A tale scopo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce funzionalità per determinare le funzionalità grafiche di un sistema in fase di esecuzione. La funzionalità grafica è determinata dal categorizzazione della scheda video come uno dei tre livelli di funzionalità di rendering. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espone un [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] che consente a un'applicazione eseguire una query il livello di funzionalità per il rendering. L'applicazione può quindi accettare i percorsi del codice diverso in fase di esecuzione a seconda del livello di rendering supportato dall'hardware.  
  
 Le funzionalità dell'hardware grafico che hanno effetto sui livelli di rendering sono:  
  
-   **RAM video** La quantità di memoria video sull'hardware grafico determina le dimensioni e il numero di buffer che possono essere usati per la composizione della grafica.  
  
-   **Pixel shader** Un pixel shader è una funzione di elaborazione grafica che calcola gli effetti sui singoli pixel. A seconda della risoluzione della grafica visualizzata, potrebbe essere necessario elaborare diversi milioni di pixel per ogni fotogramma visualizzato.  
  
-   **Vertex shader** Un vertex shader è una funzione di elaborazione grafica che esegue operazioni matematiche sui dati dei vertici dell'oggetto.  
  
-   **Supporto per più trame** Il supporto per più trame è la possibilità di applicare due o più trame distinte durante un'operazione di fusione su un oggetto grafico 3D. Il grado di supporto per più trame è determinato dal numero di unità a più trame nell'hardware grafico.  
  
 Il pixel shader, shader vertex e funzionalità multitrama vengono utilizzate per definire specifici [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] livelli di versione, che a sua volta, vengono utilizzati per definire i diversi livelli di rendering in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Le funzionalità dell'hardware grafico determinano la capacità di rendering di un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definisce tre livelli di rendering:  
  
-   **Livello di rendering 0** Nessuna accelerazione hardware grafico. Il [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] livello di versione è precedente alla versione 7.0.  
  
-   **Il rendering di livello 1** accelerazione hardware grafico parziale. Il [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] livello di versione è maggiore o uguale alla versione 7.0, e **minore** alla versione 9.0.  
  
-   **Livello di rendering 2** La maggior parte delle funzionalità grafiche usa l'accelerazione hardware grafico. Il livello della versione di [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] è superiore o uguale alla versione 9.0.  
  
 Per ulteriori informazioni su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] livelli di rendering, vedere [livelli di Rendering della grafica](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
