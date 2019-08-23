---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 678b1f71ac15d3ad30df28cec5abbe403fb08c95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937056"
---
# <a name="soapprocessing"></a>\<> soapProcessing

Definisce il comportamento dell'endpoint client usato per effettuare il marshalling dei messaggi tra versioni del messaggio e tipi di associazione diversi.

**\<system.ServiceModel>**    
&nbsp;&nbsp; **\<comportamenti >**    
&nbsp;&nbsp;&nbsp;&nbsp; **\<endpointBehaviors>**    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<behavior>**    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<soapProcessing>**
  
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

Nessuna

### <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [ **\<behavior>** ](behavior-of-endpointbehaviors.md) | Specifica un comportamento dell'endpoint. |

## <a name="remarks"></a>Note

L'elaborazione SOAP è il processo in cui i messaggi vengono convertiti tra le versioni dei messaggi.

Il servizio di routing Windows Communication Foundation (WCF) può convertire i messaggi da un protocollo a un altro. Se le versioni del messaggio in ingresso e in uscita sono diverse, viene creato un nuovo messaggio della versione corretta. L'elaborazione di messaggi da un oggetto <xref:System.ServiceModel.Channels.MessageVersion> a un altro viene eseguita costruendo un nuovo messaggio WCF contenente la parte del corpo e le relative intestazioni dal messaggio WCF in ingresso. Le intestazioni specifiche dell'indirizzamento o quelle riconosciute al livello del router non vengono usate durante la costruzione del nuovo messaggio WCF, poiché queste intestazioni presentano una versione diversa (nel caso delle intestazioni di indirizzamento) o sono state elaborate come parte della comunicazione tra il client e il router.

Il posizionamento di un'intestazione nel messaggio in uscita viene determinato dal fatto che essa venga contrassegnata o meno come riconosciuta quando è passata attraverso il livello del canale in ingresso. Le intestazioni non riconosciute (ad esempio le intestazioni personalizzate) non vengono rimosse e passano pertanto attraverso il servizio di routing mediante copia nel messaggio in uscita. Il corpo del messaggio viene copiato nel messaggio in uscita. Il messaggio viene quindi inviato al canale di uscita al quale puntano tutte le intestazioni e verranno creati e aggiunti gli altri dati di envelope specifici di tale protocollo/trasporto di comunicazione.

Questi passaggi di elaborazione vengono eseguiti quando il comportamento di elaborazione SOAP è specificato. Questo comportamento del > soapProcessingExtension è un comportamento dell'endpoint applicato a tutti gli endpoint client (in uscita) all'avvio del servizio di routing. [ \<](soapprocessing.md) per impostazione predefinita, il comportamento del [ \<> di routing](routing-of-servicebehavior.md) crea e associa un nuovo `processMessages` `true` [ \<comportamento di > soapProcessingExtension](soapprocessing.md) con impostato su per ogni endpoint client. Se si dispone di un protocollo che il servizio di routing non interpreta o si desidera eseguire l'override del comportamento di elaborazione predefinito, è possibile disabilitare l'elaborazione SOAP per l'intero servizio di routing o solo per determinati endpoint.  Per disabilitare l'elaborazione SOAP per l'intero servizio di routing su tutti gli endpoint, `soapProcessing` impostare l'attributo [ \<](routing-of-servicebehavior.md) del comportamento `false`del > di routing su. Per disattivare l'elaborazione SOAP per un determinato endpoint, utilizzare questo comportamento e impostare l'attributo `processMessages` su `false`, quindi collegare questo comportamento all'endpoint che non si desidera venga eseguito con il codice di elaborazione predefinito.  Quando il comportamento del [ \<> di routing](routing-of-servicebehavior.md) configura il servizio di routing, la riapplicazione del comportamento dell'endpoint verrà ignorata perché ne esiste già una.
