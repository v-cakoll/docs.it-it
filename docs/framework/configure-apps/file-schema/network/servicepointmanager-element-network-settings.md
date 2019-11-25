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
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089123"
---
# <a name="servicepointmanager-element-network-settings"></a>Elemento > di \<servicePointManager (impostazioni di rete)
Configura le connessioni alle risorse di rete.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**Impostazioni**](settings-element-network-settings.md)\<
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**ServicePointManager** >

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
|`checkCertificateName`|Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome host del server prima di utilizzare il certificato. Il valore predefinito è `true`.|  
|`checkCertificateRevocationList`|Specifica se il sistema deve controllare se il certificato è stato revocato prima di utilizzare il certificato. Il valore predefinito è `false`.|  
|`dnsRefreshTimeout`|Specifica la durata della memorizzazione nella cache delle risoluzioni di Domain Name Service (DNS) in combinazione con l'opzione del round robin DNS, in millisecondi. Il valore predefinito è 120.000 millisecondi (due minuti).|  
|`enableDnsRoundRobin`|Specifica se le risoluzioni DNS dei nomi host con più indirizzi IP (Internet Protocol) restituiscono tutti gli indirizzi oppure solo la prima. Il valore predefinito è `false`.|  
|`encryptionPolicy`|Specifica i criteri di crittografia applicati a una sessione SSL/TLS in un'istanza di <xref:System.Net.ServicePointManager>. I valori possibili sono equivalenti ai valori per l'enumerazione <xref:System.Net.Security.EncryptionPolicy>. Quando i criteri di crittografia sono impostati su `NoEncryption`, è necessario utilizzare <xref:System.Security.Authentication.CipherAlgorithmType.Null>. Il valore predefinito è `RequireEncryption`.|  
|`expect100Continue`|Specifica se i metodi POST devono ricevere una risposta `100-continue` dal server. Il valore predefinito è `true`.|  
|`useNagleAlgorithm`|Specifica se le connessioni controllate da Gestione punti di servizio utilizzano l'algoritmo Nagle. Il valore predefinito è `true`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Schema delle impostazioni di rete](index.md)
