---
title: Pianificazione delle prestazioni dell'applicazione
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
ms.openlocfilehash: 70dda68112d47d3e5a0609a5df7696920477c698
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210204"
---
# <a name="planning-for-application-performance"></a>Pianificazione delle prestazioni dell'applicazione
La possibilità di raggiungere gli obiettivi di prestazioni dipende dalla capacità di sviluppare una strategia di prestazioni. La pianificazione è la prima fase nello sviluppo di qualsiasi prodotto. Questo argomento descrive alcune regole molto semplice per sviluppare una strategia di prestazioni ottimali.  
  
## <a name="think-in-terms-of-scenarios"></a>Pensare in termini di scenari  
 Scenari consentono di concentrarsi sui componenti critici dell'applicazione. Scenari a livello generale sono derivati dai clienti, nonché i prodotti competitivi. Sempre studiare i tuoi clienti e scoprire ciò che rende li entusiasti al prodotto e i prodotti della concorrenza. Commenti e suggerimenti dei clienti possono aiutare a determinare uno scenario principale dell'applicazione. Ad esempio, se si sta sviluppando un componente che verrà usato all'avvio, è probabile che il componente verrà chiamato una sola volta, all'avvio dell'applicazione. Tempo di avvio diventa il principale scenario. Altri esempi di scenari chiave potrebbero essere la frequenza dei fotogrammi desiderati per le sequenze di animazione, o il working set massimo consentito per l'applicazione.  
  
## <a name="define-goals"></a>Definire gli obiettivi  
 Obiettivi di aiutano a determinare se un'applicazione sta effettuando più veloce o lenta. È consigliabile definire obiettivi per tutti gli scenari. Tutti gli obiettivi di prestazioni che definiscono devono basarsi sulle aspettative dei clienti. Potrebbe essere difficile per le prestazioni dei set del ciclo di obiettivi sin dall'inizio per lo sviluppo di applicazioni, se sono presenti problemi non risolti molti. Tuttavia, è preferibile definire un obiettivo iniziale e rivederla successiva rispetto a non a essere un obiettivo del tutto.  
  
## <a name="understand-your-platform"></a>Comprendere la piattaforma in uso  
 Mantenere sempre il ciclo di misurazione, analisi, perfezionando/correggere durante il ciclo di sviluppo dell'applicazione. A partire dall'inizio alla fine del ciclo di sviluppo, è necessario misurare le prestazioni dell'applicazione in un ambiente stabile e affidabile. È consigliabile evitare la variabilità causata da fattori esterni. Ad esempio, durante il test delle prestazioni, si dovrebbe disabilitare antivirus o qualsiasi altro aggiornamento automatico, ad esempio SMS, in modo da non influenzare i risultati del test. Dopo aver misurato le prestazioni dell'applicazione, è necessario identificare le modifiche che comporterà i miglioramenti più significativi. Dopo aver modificato l'applicazione, avviare nuovamente il ciclo.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>Creare un processo iterativo di ottimizzazione delle prestazioni  
 È necessario conoscere il costo relativo di ogni funzione che si userà. Ad esempio, l'uso della reflection in Microsoft .NET Framework è in genere prestazioni elevate in termini di risorse di calcolo, in modo che si desidera utilizzarlo con cautela. Ciò non significa evitare l'uso della reflection, solo che è necessario prestare attenzione a bilanciare i requisiti di prestazioni dell'applicazione con le esigenze di prestazioni delle funzionalità usate.  
  
## <a name="build-towards-graphical-richness"></a>Compilare verso ricchezza con interfaccia grafica  
 Una tecnica fondamentale per la creazione di un approccio scalabile per il raggiungimento di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le prestazioni dell'applicazione consiste nel compilare verso la ricchezza di con interfaccia grafica e complessità. Iniziare sempre con l'uso minimo con utilizzo intensivo delle risorse di prestazioni per raggiungere gli obiettivi di scenario. Una volta raggiungere questi obiettivi, compilare verso ricchezza grafico usando più funzionalità con utilizzo intensivo di prestazioni, sempre tenendo presenti gli obiettivi dello scenario. Tenere presente che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è una piattaforma molto avanzata e offre numerose funzionalità grafiche. Uso delle prestazioni a elevato utilizzo di funzionalità può influire negativamente sulle prestazioni dell'applicazione complessiva.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i controlli sono intrinsecamente estensibili, consentendo la diffusa personalizzazione dell'aspetto, mentre non modifica il comportamento di controllo. Grazie all'uso di stili, modelli di dati e modelli di controllo, è possibile creare e sviluppare in modo incrementale un personalizzabile [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] che si adatta ai requisiti di prestazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica 2D e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento degli oggetti](optimizing-performance-object-behavior.md)
- [Risorse dell'applicazione](optimizing-performance-application-resources.md)
- [Testo](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
