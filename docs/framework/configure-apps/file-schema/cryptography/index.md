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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927624"
---
# <a name="cryptography-settings-schema"></a>Schema delle impostazioni di crittografia
Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.  
  
 [ **\<configuration>** ](../configuration-element.md)  
  
 [ **\<mscorlib>** ](mscorlib-element-for-cryptography-settings.md)  
  
 [ **\<cryptographySettings>** ](cryptographysettings-element.md)  
  
 [ **\<cryptoNameMapping>** ](cryptonamemapping-element.md)  
  
 [ **\<cryptoClasses>** ](cryptoclasses-element.md)  
  
 [ **\<cryptoClass>** ](cryptoclass-element.md)  
  
 [ **\<nameEntry>** ](nameentry-element.md)  
  
 [ **\<oidMap>** ](oidmap-element.md)  
  
 [ **\<oidEntry>** ](oidentry-element.md)  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[ **\<cryptoClasses**>](cryptoclasses-element.md)|Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .|  
|[ **\<cryptoClass**>](cryptoclass-element.md)|Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .|  
|[ **\<cryptographySettings**>](cryptographysettings-element.md)|Contiene le impostazioni di crittografia.|  
|[ **\<cryptoNameMapping**>](cryptonamemapping-element.md)|Contiene i mapping di classi e nomi descrittivi.|  
|[**Elemento \<mscorlib>** per le impostazioni di crittografia](mscorlib-element-for-cryptography-settings.md)|Contiene l'elemento **\<cryptographySettings>** .|  
|[ **\<nameEntry>** ](nameentry-element.md)|Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.|  
|[ **\<oidEntry>** ](oidentry-element.md)|Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.|  
|[ **\<oidMap>** ](oidmap-element.md)|Contiene i mapping di OID ASN.1 e classi.|  
  
## <a name="see-also"></a>Vedere anche

- [Schema dei file di configurazione](../index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
