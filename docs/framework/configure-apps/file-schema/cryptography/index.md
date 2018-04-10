---
title: Schema delle impostazioni di crittografia
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
caps.latest.revision: 10
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 6b6d9eeacb38531ced5768f29bf26de3c9294b71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
