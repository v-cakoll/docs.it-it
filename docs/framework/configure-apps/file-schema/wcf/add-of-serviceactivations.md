---
title: <add> di <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 929773fcb6b6a3ee5c75aa970147277d9dbe7b45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920019"
---
# <a name="add-of-serviceactivations"></a>\<aggiungere > di \<serviceActivations >

Elemento di configurazione che consente di definire le impostazioni di attivazione del servizio virtuale che vengono mappate ai tipi di servizio Windows Communication Foundation (WCF). In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.

\<system.ServiceModel>\
\<serviceHostingEnvironment>

## <a name="syntax"></a>Sintassi

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|DESCRIZIONE|
|---------------|-----------------|
|factory|Stringa che specifica il tipo CLR della factory che genera un elemento di attivazione del servizio.|
|servizio|ServiceType che implementa il servizio, ossia il Typename completo o il Typename breve, quando viene inserito nella cartella App_Code.|
|relativeAddress|Indirizzo relativo all'interno dell'applicazione IIS corrente, ad esempio “Service.svc". In WCF 4.0 questo indirizzo relativo deve contenere una delle estensioni di file note (svc, xamlx, ecc.). Nessun file fisico deve esistere per l'URL relativo|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.|

## <a name="remarks"></a>Note

Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.

Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione. È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale. Inoltre, `serviceHostingEnvironment` è una sezione ereditabile machineToApplication. Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.

L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http. Sono necessarie le estensioni in relativeAddress, ad esempio SVC, xoml o xamlx. È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione. In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
