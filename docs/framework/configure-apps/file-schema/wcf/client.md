---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "72773938"
---
# \<client>
L'elemento `client` definisce un elenco di endpoint ai quali può connettersi un client.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a>Sintassi

```xml
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi
 nessuno

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|Contiene una raccolta di elementi endpoint che specificano gli endpoint a cui il client può connettersi.|
|[\<metadata>](metadata.md)|Contiene impostazioni per l'elaborazione di metadati.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).|

## <a name="remarks"></a>Commenti
 La sezione `client` definisce un elenco di endpoint ai quali può connettersi un client. Ogni endpoint elencato nella sezione client definisce la propria associazione, comportamento e contratto. È identificato in modo univoco dalla combinazione degli attributi `name` e `contract`. Il codice client specifica il `name` al quale connettere un endpoint per il servizio implementato dal client. Se l'attributo `name` è omesso, l'endpoint si comporta come endpoint predefinito per il contratto che implementa.

 In aggiunta, questa sezione specifica anche impostazioni per l'elaborazione di metadati.

## <a name="example"></a>Esempio

```xml
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [Configurazione del client WCF](../../../wcf/feature-details/client-configuration.md)
- [Client](../../../wcf/feature-details/clients.md)
