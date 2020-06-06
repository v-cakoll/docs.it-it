---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399533"
---
# \<soapProcessing>

Definisce il comportamento dell'endpoint client usato per effettuare il marshalling dei messaggi tra versioni del messaggio e tipi di associazione diversi.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
  
Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|                   | Descrizione |
| ----------------- | ----------- |
| `processMessages` | Valore booleano che specifica se è necessario effettuare il marshalling dei messaggi tra le versioni di messaggi SOAP. |

### <a name="child-elements"></a>Elementi figlio

nessuno

### <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [**\<behavior>**](behavior-of-endpointbehaviors.md) | Specifica un comportamento dell'endpoint. |

## <a name="remarks"></a>Commenti

L'elaborazione SOAP è il processo in cui i messaggi vengono convertiti tra le versioni dei messaggi.

Il servizio di routing Windows Communication Foundation (WCF) può convertire i messaggi da un protocollo a un altro. Se le versioni del messaggio in ingresso e in uscita sono diverse, viene creato un nuovo messaggio della versione corretta. L'elaborazione di messaggi da un oggetto <xref:System.ServiceModel.Channels.MessageVersion> a un altro viene eseguita costruendo un nuovo messaggio WCF contenente la parte del corpo e le relative intestazioni dal messaggio WCF in ingresso. Le intestazioni specifiche dell'indirizzamento o quelle riconosciute al livello del router non vengono usate durante la costruzione del nuovo messaggio WCF, poiché queste intestazioni presentano una versione diversa (nel caso delle intestazioni di indirizzamento) o sono state elaborate come parte della comunicazione tra il client e il router.

Il posizionamento di un'intestazione nel messaggio in uscita viene determinato dal fatto che essa venga contrassegnata o meno come riconosciuta quando è passata attraverso il livello del canale in ingresso. Le intestazioni non riconosciute (ad esempio le intestazioni personalizzate) non vengono rimosse e passano pertanto attraverso il servizio di routing mediante copia nel messaggio in uscita. Il corpo del messaggio viene copiato nel messaggio in uscita. Il messaggio viene quindi inviato al canale di uscita al quale puntano tutte le intestazioni e verranno creati e aggiunti gli altri dati di envelope specifici di tale protocollo/trasporto di comunicazione.

Questi passaggi di elaborazione vengono eseguiti quando il comportamento di elaborazione SOAP è specificato. Questo [\<soapProcessingExtension>](soapprocessing.md) comportamento è un comportamento dell'endpoint applicato a tutti gli endpoint client (in uscita) all'avvio del servizio di routing. per impostazione predefinita, il [\<routing>](routing-of-servicebehavior.md) comportamento crea e associa un nuovo [\<soapProcessingExtension>](soapprocessing.md) comportamento con `processMessages` impostato su `true` per ogni endpoint client. Se si dispone di un protocollo che il servizio di routing non interpreta o si desidera eseguire l'override del comportamento di elaborazione predefinito, è possibile disabilitare l'elaborazione SOAP per l'intero servizio di routing o solo per determinati endpoint.  Per disabilitare l'elaborazione SOAP per l'intero servizio di routing su tutti gli endpoint, impostare l' `soapProcessing` attributo del [\<routing>](routing-of-servicebehavior.md) comportamento su `false` . Per disattivare l'elaborazione SOAP per un determinato endpoint, utilizzare questo comportamento e impostare l'attributo `processMessages` su `false`, quindi collegare questo comportamento all'endpoint che non si desidera venga eseguito con il codice di elaborazione predefinito.  Quando il [\<routing>](routing-of-servicebehavior.md) comportamento configura il servizio di routing, la riapplicazione del comportamento dell'endpoint verrà ignorata perché ne esiste già una.
