---
title: Condivisione delle porte Net.TCP
ms.date: 03/30/2017
helpviewer_keywords:
- port activation [WCF]
- port sharing [WCF]
ms.assetid: f13692ee-a179-4439-ae72-50db9534eded
ms.openlocfilehash: d9c6caa546d9f31f4e68b850dc1b1e750da2e93c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598762"
---
# <a name="nettcp-port-sharing"></a>Condivisione delle porte Net.TCP
Windows Communication Foundation (WCF) fornisce un nuovo protocollo di rete basato su TCP (NET. TCP://) per la comunicazione a prestazioni elevate. WCF introduce inoltre un nuovo componente di sistema, il servizio di condivisione delle porte net. TCP che consente la condivisione delle porte net. TCP tra più processi utente.  
  
## <a name="background-and-motivation"></a>Informazioni generali e motivazione  
 Quando il protocollo TCP/IP è stato introdotto per la prima volta, solo pochi protocolli di applicazione lo utilizzavano. TCP/IP usa numeri di porta per differenziare le applicazioni, assegnando un numero di porta univoco a 16 bit a ogni protocollo di applicazione. Ad esempio, il traffico HTTP è oggi standardizzato sull'utilizzo del TCP sulla porta 80, l'SMTP usa il TCP sulla porta 25 e l'FTP usa il TCP sulle porte 20 e 21. Per altre applicazioni che usano il TCP come trasporto è possibile scegliere un altro numero di porta disponibile, per convenzione o attraverso la standardizzazione formale.  
  
 L'utilizzo di numeri di porta per fare distinzioni tra le applicazioni comporta problemi di sicurezza. I firewall sono generalmente configurati per bloccare il traffico TCP su tutte le porte, a parte alcuni punti di ingresso conosciuti, pertanto la distribuzione di un'applicazione che usa una porta non standard è spesso complicata, se non impossibile, a causa della presenza di firewall aziendali e personali. Le applicazioni che possono comunicare su porte note standard, già consentite, riducono la superficie d'attacco esterna. Molte applicazioni di rete usano il protocollo HTTP, poiché la maggior parte dei firewall è configurata, per impostazione predefinita, per consentire il traffico sulla porta TCP 80.  
  
 Il modello HTTP.SYS, in cui il traffico per molte applicazioni HTTP diverse viene reso multiplex su una sola porta TCP, è diventato lo standard sulla piattaforma Windows. Questo offre un punto di controllo comune per gli amministratori dei firewall, consentendo al contempo agli sviluppatori di applicazioni di ridurre al minimo i costi di distribuzione associati alla creazione di nuove applicazioni che possono fare uso della rete.  
  
 La possibilità di condividere porte tra più applicazioni HTTP caratterizza da molto tempo Internet Information Services (IIS). Tuttavia, era solo con l'introduzione del protocollo HTTP. SYS (il listener del protocollo HTTP in modalità kernel) con IIS 6,0 che questa infrastruttura è stata completamente generalizzata. In effetti, HTTP.SYS consente a processi utente arbitrari di condividere le porte TCP dedicate al traffico HTTP. Questa capacità consente a molte applicazioni HTTP di coesistere sullo stesso computer fisico in processi isolati, distinti e nel contempo condividere l'infrastruttura di rete richiesta per inviare e ricevere il traffico su TCP sulla porta 80. Il Servizio di condivisione porte Net.TCP consente alle applicazioni net.tcp di condividere lo stesso tipo di porta.  
  
## <a name="port-sharing-architecture"></a>Architettura di condivisione delle porte  
 L'architettura di condivisione delle porte in WCF è costituita da tre componenti principali:  
  
- Un processo di lavoro: qualsiasi processo che comunica su net.tcp:// usando porte condivise.  
  
- Il trasporto TCP WCF: implementa il protocollo net. TCP://.  
  
- Il Servizio di condivisione porte Net.TCP: consente a molti processi di lavoro di condividere la stessa porta TCP.  
  
 Il Servizio di condivisione porte Net.TCP è un servizio Windows in modalità utente che accetta connessioni net.tcp:// per conto dei processi di lavoro che stabiliscono connessioni tramite esso. Quando arriva una connessione socket, il servizio di condivisione delle porte esamina il flusso di messaggi in ingresso per ottenerne l'indirizzo di destinazione. In base a questo indirizzo, il servizio di condivisione delle porte può instradare il flusso di dati all'applicazione che in definitiva lo elaborerà.  
  
 Quando si apre un servizio WCF che usa la condivisione delle porte net. TCP://, l'infrastruttura di trasporto TCP WCF non apre direttamente un socket TCP nel processo dell'applicazione. Registra, invece, l'URI (Uniform Resource Identifier) dell'indirizzo di base del servizio presso il Servizio di condivisione porte Net.TCP e attende che quest'ultimo ascolti i messaggi per suo conto.  Il servizio di condivisione delle porte invia i messaggi indirizzati al servizio dell'applicazione non appena arrivano.  
  
## <a name="installing-port-sharing"></a>Installazione della condivisione delle porte  
 Il servizio di condivisione porte net. TCP è disponibile in tutti i sistemi operativi che supportano WinFX, ma il servizio non è abilitato per impostazione predefinita. Per motivi di sicurezza, gli amministratori devono attivare manualmente il Servizio di condivisione porte Net.TCP al primo utilizzo. Il Servizio di condivisione porte Net.TCP espone opzioni di configurazione che consentono di modificare diverse caratteristiche dei socket di rete appartenenti al servizio stesso. Per altre informazioni, vedere [procedura: abilitare il servizio di condivisione porte net. TCP](how-to-enable-the-net-tcp-port-sharing-service.md).  
  
## <a name="using-nettcp-port-sharing-in-an-application"></a>Utilizzo della condivisione delle porte Net.tcp in un'applicazione  
 Il modo più semplice per utilizzare la condivisione delle porte net. TCP://nell'applicazione WCF consiste nell'esporre un servizio utilizzando <xref:System.ServiceModel.NetTcpBinding> e quindi abilitare il servizio di condivisione delle porte net. TCP utilizzando la <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> Proprietà.  
  
 Per altre informazioni su come eseguire questa operazione, vedere [procedura: configurare un servizio WCF per l'uso della condivisione delle porte](how-to-configure-a-wcf-service-to-use-port-sharing.md).  
  
## <a name="security-implications-of-port-sharing"></a>Implicazioni di sicurezza della condivisione delle porte  
 Sebbene il Servizio di condivisione porte Net.TCP preveda un livello di elaborazione tra le applicazioni e la rete, le applicazioni che usano la condivisione delle porte dovrebbero comunque essere protette come se fossero direttamente in ascolto sulla rete. In particolare, le applicazioni che usano la condivisione delle porte dovrebbero valutare i privilegi del processo con cui vengono eseguite. Considerare l'ipotesi di eseguire l'applicazione usando l'account predefinito Servizio di rete, che viene eseguito con il set minimo di privilegi del processo necessari per la comunicazione di rete.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione del servizio di condivisione delle porte Net.TCP](configuring-the-net-tcp-port-sharing-service.md)
- [Hosting](hosting.md)
- [Procedura: configurare un servizio WCF per l'uso della condivisione delle porte](how-to-configure-a-wcf-service-to-use-port-sharing.md)
- [Procedura: attivare il servizio di condivisione delle porte Net.TCP](how-to-enable-the-net-tcp-port-sharing-service.md)
