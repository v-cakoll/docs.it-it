---
title: Schema delle impostazioni di rete
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 0f5d762a2b688bebcb7c027be6c639b6d64c069d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664113"
---
# <a name="network-settings-schema"></a>Schema delle impostazioni di rete
Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework. La tabella seguente descrive la funzione di ogni elemento di configurazione figlio dell'[elemento \<system.Net> (impostazioni di rete)](system-net-element-network-settings.md).  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<authenticationModules> (impostazioni di rete)](authenticationmodules-element-network-settings.md)|Specifica i moduli usati per autenticare le richieste Internet.|  
|[Elemento \<connectionManagement> (impostazioni di rete)](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a host Internet.|  
|[Elemento \<defaultProxy> (impostazioni di rete)](defaultproxy-element-network-settings.md)|Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.|  
|[Elemento \<mailSettings> (impostazioni di rete)](mailsettings-element-network-settings.md)|Contiene le impostazioni per le opzioni di invio della posta elettronica.|  
|[Elemento \<requestCaching> (impostazioni di rete)](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
|[Elemento \<webRequestModules> (impostazioni di rete)](webrequestmodules-element-network-settings.md)|Specifica i moduli usati per richiedere informazioni da host Internet.|  
  
 Tramite le impostazioni URI viene specificata la modalità di gestione da parte di .NET Framework degli indirizzi Web espressi tramite Uniform Resource Identifier (URI). La tabella seguente descrive la funzione di ogni elemento di configurazione figlio dell'[elemento \<Uri> (impostazioni URI)](uri-element-uri-settings.md).  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[Elemento \<idn> (impostazioni URI)](idn-element-uri-settings.md)|Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.|  
|[Elemento \<iriParsing> (impostazioni URI)](iriparsing-element-uri-settings.md)|Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.|  
|[Elemento \<schemeSettings> (impostazioni URI)](schemesettings-element-uri-settings.md)|Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.|  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione di applicazioni Internet](../../../network-programming/configuring-internet-applications.md)
- [Schema dei file di configurazione](../index.md)
