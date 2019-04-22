---
title: Elemento <servicePointManager> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: 407ed85de109a671030eccff8ddd92af91628014
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202209"
---
# <a name="servicepointmanager-element-network-settings"></a>\<servicePointManager > (impostazioni di rete)
Consente di configurare le connessioni alle risorse di rete.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<servicePointManager>  
  
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
|`checkCertificateName`|Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome host del server prima di usare il certificato. Il valore predefinito è `true`.|  
|`checkCertificateRevocationList`|Specifica se il sistema deve verificare se è stato revocato il certificato prima di usare il certificato. Il valore predefinito è `false`.|  
|`dnsRefreshTimeout`|Specifica la durata del servizio DNS (Domain Name) vengono memorizzati nella cache le soluzioni in combinazione con l'opzione DNS Round Robin, in millisecondi. Il valore predefinito è 120.000 millisecondi (due minuti).|  
|`enableDnsRoundRobin`|Specifica se le risoluzioni DNS dell'host di nomi con più indirizzi IP (Internet Protocol) restituiti tutti gli indirizzi, o solo il primo. Il valore predefinito è `false`.|  
|`encryptionPolicy`|Specifica i criteri di crittografia applicati a una sessione SSL/TLS in un <xref:System.Net.ServicePointManager> istanza. I possibili valori sono equivalenti ai valori per il <xref:System.Net.Security.EncryptionPolicy> enumerazione. L'uso di <xref:System.Security.Authentication.CipherAlgorithmType.Null> è obbligatorio quando il criterio di crittografia è impostato su `NoEncryption`. Il valore predefinito è `RequireEncryption`.|  
|`expect100Continue`|Specifica se i metodi POST devono prevedere di ricevere un `100-continue` risposta dal server. Il valore predefinito è `true`.|  
|`useNagleAlgorithm`|Specifica se le connessioni controllate dal punto di Gestione servizi usano l'algoritmo Nagle. Il valore predefinito è `true`.|  
  
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

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
