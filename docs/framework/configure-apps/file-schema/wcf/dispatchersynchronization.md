---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925848"
---
# <a name="dispatchersynchronization"></a>\<> dispatcherSynchronization
  
Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.  
  
\<system.serviceModel>  
\<comportamenti >  
\<endpointBehaviors>  
\<comportamento >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a>Type  
  
`Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
  
Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi

| Attributo               | DESCRIZIONE       |
| ----------------------- | ----------------- |
| asynchronousSendEnabled | Valore booleano che specifica se il comportamento di invio asincrono è abilitato. |
| `maxPendingReceives`    | Integer che specifica il numero di ricezioni simultanee che è possibile inviare sul canale.<br /><br /> Questo valore deve essere configurato solo dopo aver configurato correttamente il comportamento di limitazione del servizio. |

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

| Elemento | DESCRIZIONE |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint. |

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
