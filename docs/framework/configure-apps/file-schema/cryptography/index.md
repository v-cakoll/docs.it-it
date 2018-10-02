---
title: Schema delle impostazioni di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 71d2edac1dd9a84c9d3c92049d2494c7c5bd54b0
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028218"
---
# <a name="cryptography-settings-schema"></a>Schema delle impostazioni di crittografia
Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.  
  
 [**\<configuration>**](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [**\<mscorlib>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [**\<cryptographySettings>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [**\<cryptoNameMapping>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [**\<cryptoClasses>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [**\<cryptoClass>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>**.|  
|[**\<cryptoClass**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>**.|  
|[**\<cryptographySettings**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|Contiene le impostazioni di crittografia.|  
|[**\<cryptoNameMapping**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Contiene i mapping di classi e nomi descrittivi.|  
|[**Elemento \<mscorlib>** per le impostazioni di crittografia](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|Contiene l'elemento **\<cryptographySettings>**.|  
|[**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.|  
|[**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.|  
|[**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Contiene i mapping di OID ASN.1 e classi.|  
  
## <a name="see-also"></a>Vedere anche  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Servizi di crittografia](../../../../../docs/standard/security/cryptographic-services.md)
