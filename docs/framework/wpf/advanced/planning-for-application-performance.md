---
title: Pianificazione delle prestazioni dell'applicazione
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
ms.openlocfilehash: c8e763686b30ca9c8e1dc5a7f6234d77201e4cba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546952"
---
# <a name="planning-for-application-performance"></a>Pianificazione delle prestazioni dell'applicazione
La possibilità di raggiungere gli obiettivi di prestazioni dipende dalla capacità di sviluppare una strategia di prestazioni. La pianificazione è la prima fase dello sviluppo di qualsiasi prodotto. In questo argomento vengono descritte alcune regole molto semplice per definire una strategia per prestazioni ottimali.  
  
## <a name="think-in-terms-of-scenarios"></a>Pensare in termini di scenari  
 Scenari consentono di concentrarsi sui componenti critici dell'applicazione. Scenari in genere sono derivati dai clienti, nonché prodotti della concorrenza. Sempre studiare i clienti e scoprire ciò che effettivamente rende entusiasti del prodotto e i prodotti della concorrenza. Commenti e suggerimenti dei clienti può essere utile per determinare lo scenario principale dell'applicazione. Ad esempio, se si progetta un componente che verrà utilizzato all'avvio, è probabile che il componente verrà chiamato una sola volta, quando l'avvio dell'applicazione. Tempo di avvio diventa lo scenario di chiave. Altri esempi di scenari principali potrebbero essere la frequenza dei fotogrammi desiderato per le sequenze di animazione oppure il working set massimo consentito per l'applicazione.  
  
## <a name="define-goals"></a>Definire gli obiettivi  
 Gli obiettivi consentono di determinare se un'applicazione è velocità di esecuzione. È consigliabile definire obiettivi per tutti gli scenari. Tutti gli obiettivi di prestazioni che definiscono dovrebbero essere basati sulle aspettative dei clienti. Potrebbe risultare difficile per le prestazioni di set di obiettivi sin dall'inizio per lo sviluppo di applicazioni del ciclo, quando sono presenti molti problemi non risolti. Tuttavia, è preferibile definire un obiettivo iniziale e modificarlo successivamente di per hanno un obiettivo affatto.  
  
## <a name="understand-your-platform"></a>Comprendere la piattaforma  
 Mantenere sempre il ciclo di misurazione, analisi, perfezionamento e correzione durante il ciclo di sviluppo di applicazioni. A partire dall'inizio alla fine del ciclo di sviluppo, è necessario misurare le prestazioni dell'applicazione in un ambiente stabile e affidabile. È consigliabile evitare variabilità causata da fattori esterni. Ad esempio, durante il test delle prestazioni, si deve disabilitare antivirus o qualsiasi altro aggiornamento automatico, ad esempio SMS, in modo da non influenzare i risultati del test. Dopo aver misurato le prestazioni dell'applicazione, è necessario identificare le modifiche che generano i miglioramenti principali. Dopo aver modificato l'applicazione, avviare nuovamente il ciclo.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>Verificare un processo iterativo di ottimizzazione delle prestazioni  
 È necessario conoscere il costo relativo di ogni funzionalità che verranno utilizzate. Ad esempio, l'uso della reflection in Microsoft .NET Framework è in genere prestazioni elevate in termini di risorse di elaborazione, pertanto si desidera utilizzarlo con cautela. Ciò non significa evitare l'uso della reflection, solo che è necessario prestare attenzione a bilanciare i requisiti di prestazioni dell'applicazione con le esigenze di prestazioni delle funzionalità utilizzate.  
  
## <a name="build-towards-graphical-richness"></a>Compilare verso ricchezza grafica  
 Una tecnica chiave per la creazione di un approccio scalabile per raggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le prestazioni dell'applicazione consiste nel compilare verso la ricchezza di con interfaccia grafica e complessità. Iniziare sempre con le risorse che richiedono prestazioni almeno per raggiungere gli obiettivi di scenario. Una volta raggiungere questi obiettivi, compilare verso ricchezza grafica con altre funzionalità con utilizzo intensivo di prestazioni, sempre tenendo presenti gli obiettivi dello scenario. Tenere presente che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è una piattaforma molto articolata e offre numerose funzionalità grafiche. Utilizzo delle prestazioni con utilizzo intensivo di funzionalità può influire negativamente sulle prestazioni complessive dell'applicazione.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i controlli sono intrinsecamente estensibili, consentendo diffusa personalizzazione dell'aspetto, mentre non modifica il comportamento di controllo. Sfruttare gli stili, modelli di dati e modelli di controllo, è possibile creare e sviluppare in modo incrementale un personalizzabile [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] che si adatta ai requisiti di prestazioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
