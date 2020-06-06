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
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698157"
---
# <a name="network-settings-schema"></a>Schema delle impostazioni di rete
Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework.

Le \<system.net> impostazioni specificano il modo in cui il .NET Framework si connette alla rete. Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [ \<system.Net> elemento (impostazioni di rete)](system-net-element-network-settings.md).  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<authenticationModules>Elemento (impostazioni di rete)](authenticationmodules-element-network-settings.md)|Specifica i moduli usati per autenticare le richieste Internet.|  
|[\<connectionManagement>Elemento (impostazioni di rete)](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a host Internet.|  
|[\<defaultProxy>Elemento (impostazioni di rete)](defaultproxy-element-network-settings.md)|Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.|  
|[\<mailSettings>Elemento (impostazioni di rete)](mailsettings-element-network-settings.md)|Contiene le impostazioni per le opzioni di invio della posta elettronica.|  
|[\<requestCaching>Elemento (impostazioni di rete)](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
|[\<webRequestModules>Elemento (impostazioni di rete)](webrequestmodules-element-network-settings.md)|Specifica i moduli usati per richiedere informazioni da host Internet.|  
  
Le \<uri> impostazioni specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier). Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [ \<uri> elemento (impostazioni URI)](uri-element-uri-settings.md).  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<idn>Elemento (impostazioni URI)](idn-element-uri-settings.md)|Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.|  
|[\<iriParsing>Elemento (impostazioni URI)](iriparsing-element-uri-settings.md)|Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.|  
|[\<schemeSettings>Elemento (impostazioni URI)](schemesettings-element-uri-settings.md)|Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.|  
  
## <a name="see-also"></a>Vedi anche

- [Configurazione di applicazioni Internet](../../../network-programming/configuring-internet-applications.md)
- [Schema del file di configurazione](../index.md)
