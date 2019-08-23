---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 12369f1053638583a3864fab396869d0e7045732
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918670"
---
# <a name="transactedbatching"></a>\<> transactedBatching

Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.

\<system.ServiceModel>\
\<comportamenti > \
\<endpointBehaviors>\
\<comportamento > \
\<> transactedBatching

## <a name="syntax"></a>Sintassi

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|DESCRIZIONE|
|---------------|-----------------|
|`maxBatchSize`|Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione. Il valore predefinito è 0.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|

## <a name="remarks"></a>Note

Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione. In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
