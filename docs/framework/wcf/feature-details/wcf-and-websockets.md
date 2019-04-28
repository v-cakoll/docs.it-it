---
title: WCF e WebSocket
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768732"
---
# <a name="wcf-and-websockets"></a>WCF e WebSocket
Con .NET Framework 4.5 è stato introdotto il supporto per WebSocket in Windows Communication Foundation.  Si tratta di una tecnologia efficiente e basata su standard che consente la comunicazione bidirezionale sulle porte 80 e 443 HTTP standard. L'utilizzo delle porte HTTP standard consente la comunicazione WebSocket attraverso il Web mediante intermediari.  Sono state aggiunte due nuove associazioni standard per supportare la comunicazione tramite un trasporto WebSocket, <xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>. Impostazioni specifiche per WebSocket possono essere configurate nel <xref:System.ServiceModel.Channels.HttpTransportBindingElement> accedendo il <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> proprietà.
  
## <a name="in-this-section"></a>In questa sezione  
 [Uso di NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Viene illustrato l'oggetto <xref:System.ServiceModel.NetHttpBinding> e la relativa configurazione.  
  
 [Procedura: Creare un servizio WCF che comunica tramite WebSockets](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Viene descritto come creare un servizio WCF che comunica tramite WebSockets.  
  
## <a name="reference"></a>Riferimenti  
  
## <a name="related-sections"></a>Sezioni correlate
