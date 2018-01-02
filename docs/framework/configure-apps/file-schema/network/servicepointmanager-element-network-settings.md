---
title: '&lt;servicePointManager&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 38ffe6728ca05022caca8f5973b546f2b17412d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicepointmanagergt-element-network-settings"></a>&lt;servicePointManager&gt; elemento (impostazioni di rete)
Configura le connessioni alle risorse di rete.  
  
 \<configuration>  
\<System.NET >  
\<Impostazioni >  
\<servicePointManager >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`checkCertificateName`|Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome di host server prima di utilizzare il certificato. Il valore predefinito è `true`.|  
|`checkCertificateRevocationList`|Specifica se il sistema deve verificare se è stato revocato il certificato prima di utilizzare il certificato. Il valore predefinito è `false`.|  
|`dnsRefreshTimeout`|Specifica la durata del servizio DNS (Domain Name) vengono memorizzati nella cache le soluzioni in combinazione con l'opzione DNS Round Robin, in millisecondi. Il valore predefinito è 120.000 millisecondi (due minuti).|  
|`enableDnsRoundRobin`|Specifica se la risoluzione DNS dell'host nomi con più indirizzi IP (Internet Protocol) restituiti tutti gli indirizzi o solo il primo. Il valore predefinito è `false`.|  
|`encryptionPolicy`|Specifica i criteri di crittografia applicato a una sessione SSL/TLS in un <xref:System.Net.ServicePointManager> istanza. I possibili valori sono equivalenti ai valori per il <xref:System.Net.Security.EncryptionPolicy> enumerazione. L'utilizzo di <xref:System.Security.Authentication.CipherAlgorithmType.Null> è necessario quando i criteri di crittografia sono impostato su `NoEncryption`. Il valore predefinito è `RequireEncryption`.|  
|`expect100Continue`|Specifica se i metodi POST devono prevedere di ricevere un `100-continue` risposta dal server. Il valore predefinito è `true`.|  
|`useNagleAlgorithm`|Specifica se le connessioni controllate dal gestore del punto di servizio utilizzano l'algoritmo Nagle. Il valore predefinito è `true`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
