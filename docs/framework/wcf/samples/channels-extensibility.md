---
title: Estensibilità dei canali
ms.date: 03/30/2017
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
ms.openlocfilehash: 9dbae26a548bdc8a8cfb05a3dd90db91475b55ba
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600633"
---
# <a name="channels-extensibility"></a>Estensibilità dei canali
Contenuto della sezione sono inclusi esempi che descrivono canali personalizzati.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Canale locale](local-channel.md)  
 Viene illustrato il canale locale, ovvero un canale di trasporto WCF utilizzato per la comunicazione all'interno dello stesso dominio applicazione.  
  
 [Reliable Secure Profile](reliable-secure-profile.md)  
 Viene illustrato come comporre WCF e un profilo sicuro affidabile (RSP).  
  
 [Dispatcher di canali personalizzati](custom-channel-dispatcher.md)  
 Viene descritto come compilare lo stack di canali in modo personalizzato implementando direttamente <xref:System.ServiceModel.ServiceHostBase> e come creare un dispatcher del canale personalizzato in un ambiente host Web.  
  
 [Chunking del canale](chunking-channel.md)  
 Viene illustrato come limitare la quantità di memoria utilizzata per memorizzare nel buffer messaggi di grandi dimensioni inviati tramite WCF.
  
 [HttpCookieSession](httpcookiesession.md)  
 Viene illustrato come compilare un canale di protocollo personalizzato per utilizzare cookie HTTP per la gestione della sessione.  
  
 [Intercettore dei messaggi personalizzati](custom-message-interceptor.md)  
 Viene illustrato come implementare un elemento di associazione personalizzato che crea channel factory e listener del canale per intercettare tutti i messaggi in ingresso e in uscita in un particolare punto nello stack di runtime.
