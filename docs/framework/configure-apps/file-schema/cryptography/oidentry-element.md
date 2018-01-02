---
title: '&lt;oidEntry&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2d6dfe38f8e632a31f7a20191678f1fff7fd88ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltoidentrygt-element"></a>&lt;oidEntry&gt; elemento
Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.  
  
 \<configuration>  
\<mscorlib >  
\<cryptographySettings >  
\<oidMap >  
\<oidEntry >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**OID**|Attributo obbligatorio.<br /><br /> Specifica l'OID ASN. 1 corrispondente all'algoritmo implementato dalla classe.|  
|**name**|Attributo obbligatorio.<br /><br /> Specifica il valore per il **nome** attributo la [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`cryptographySettings`|Contiene le impostazioni di crittografia.|  
|`mscorlib`|Contiene il `cryptographySettings` elemento.|  
|`oidMap`|Contiene i mapping di ASN. 1 oggetto (OID) identificatore alle classi.|  
  
## <a name="remarks"></a>Note  
 Gli identificatori di oggetto ASN. 1 identificano gli algoritmi in alcuni formati di crittografia. Eseguire il mapping ai nomi descrittivi per gli algoritmi a cui che si desidera identificare gli identificatori di oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il  **\<oidEntry >** elemento per eseguire il mapping di un identificatore di oggetto per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo hash.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Schema delle impostazioni di crittografia](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Servizi di crittografia](../../../../../docs/standard/security/cryptographic-services.md)  
 [Configurazione di classi di crittografia](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Mapping di identificatori di oggetti ad algoritmi di crittografia](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
