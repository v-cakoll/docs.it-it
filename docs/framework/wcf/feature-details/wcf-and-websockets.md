---
title: WCF e WebSocket
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: df4a251eb5a570c9fedf19d385a027e23481afed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594946"
---
# <a name="wcf-and-websockets"></a>WCF e WebSocket
Con .NET Framework 4.5 è stato introdotto il supporto per WebSocket in Windows Communication Foundation.  Si tratta di una tecnologia efficiente e basata su standard che consente la comunicazione bidirezionale sulle porte 80 e 443 HTTP standard. L'utilizzo delle porte HTTP standard consente la comunicazione WebSocket attraverso il Web mediante intermediari.  Sono state aggiunte due nuove associazioni standard per supportare la comunicazione tramite un trasporto WebSocket, <xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>. Le impostazioni specifiche di WebSockets possono essere configurate su <xref:System.ServiceModel.Channels.HttpTransportBindingElement> tramite l'accesso alla <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Proprietà.
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Uso di NetHttpBinding](using-the-nethttpbinding.md)  
 Viene illustrato l'oggetto <xref:System.ServiceModel.NetHttpBinding> e la relativa configurazione.  
  
 [Procedura: creare un servizio WCF che comunica tramite WebSockets](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Viene descritto come creare un servizio WCF che comunica tramite WebSockets.  
  
## <a name="reference"></a>Informazioni di riferimento  
  
## <a name="related-sections"></a>Sezioni correlate
