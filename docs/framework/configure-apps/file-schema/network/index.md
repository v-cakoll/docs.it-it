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
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698157"
---
# <a name="network-settings-schema"></a>Schema delle impostazioni di rete
Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework.

Le impostazioni @no__t -0system. net > specificano il modo in cui il .NET Framework si connette alla rete. La tabella seguente descrive la funzione di ogni elemento di configurazione figlio dell'[elemento \<system.Net> (impostazioni di rete)](system-net-element-network-settings.md).  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<authenticationModules> (impostazioni di rete)](authenticationmodules-element-network-settings.md)|Specifica i moduli usati per autenticare le richieste Internet.|  
|[Elemento \<connectionManagement> (impostazioni di rete)](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a host Internet.|  
|[Elemento \<defaultProxy> (impostazioni di rete)](defaultproxy-element-network-settings.md)|Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.|  
|[Elemento \<mailSettings> (impostazioni di rete)](mailsettings-element-network-settings.md)|Contiene le impostazioni per le opzioni di invio della posta elettronica.|  
|[Elemento \<requestCaching> (impostazioni di rete)](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
|[Elemento \<webRequestModules> (impostazioni di rete)](webrequestmodules-element-network-settings.md)|Specifica i moduli usati per richiedere informazioni da host Internet.|  
  
Le impostazioni di > \<uri specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier). Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [elemento \<uri > (impostazioni URI)](uri-element-uri-settings.md).  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<idn> (impostazioni URI)](idn-element-uri-settings.md)|Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.|  
|[Elemento \<iriParsing> (impostazioni URI)](iriparsing-element-uri-settings.md)|Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.|  
|[Elemento \<schemeSettings> (impostazioni URI)](schemesettings-element-uri-settings.md)|Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.|  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione di applicazioni Internet](../../../network-programming/configuring-internet-applications.md)
- [Schema dei file di configurazione](../index.md)
