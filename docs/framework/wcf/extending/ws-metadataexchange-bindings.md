---
title: Associazioni WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488624"
---
# <a name="ws-metadataexchange-bindings"></a>Associazioni WS-MetadataExchange
In questo argomento vengono illustrate le modalità di costruzione delle associazioni predefinite per lo scambio di metadati per i vari trasporti.  
  
## <a name="the-default-bindings"></a>Associazioni predefinite  
  
|Nome associazione predefinita|Modalità di costruzione dell'associazione|  
|--------------------------|------------------------------------|  
|MexHttpBinding|Una classe <xref:System.ServiceModel.WSHttpBinding> con protezione a livello di trasporto attivata.|  
|MexHttpsBinding|Una classe <xref:System.ServiceModel.WSHttpBinding> che supporta la protezione a livello di trasporto.|  
|MexNamedPipeBinding|Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> che utilizza valori predefiniti.|  
|MexTcpBinding|Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.TcpTransportBindingElement> che utilizza valori predefiniti.|
