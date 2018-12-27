---
title: Associazioni WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767348"
---
# <a name="ws-metadataexchange-bindings"></a>Associazioni WS-MetadataExchange
In questo argomento vengono illustrate le modalità di costruzione delle associazioni predefinite per lo scambio di metadati per i vari trasporti.  
  
## <a name="the-default-bindings"></a>Associazioni predefinite  
  
|Nome associazione predefinita|Modalità di costruzione dell'associazione|  
|--------------------------|------------------------------------|  
|mexHttpBinding|Una classe <xref:System.ServiceModel.WSHttpBinding> con protezione a livello di trasporto attivata.|  
|mexHttpsBinding|Una classe <xref:System.ServiceModel.WSHttpBinding> che supporta la protezione a livello di trasporto.|  
|mexNamedPipeBinding|Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> che utilizza valori predefiniti.|  
|mexTcpBinding|Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.TcpTransportBindingElement> che utilizza valori predefiniti.|
