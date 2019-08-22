---
title: <oidMap> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: e01cdd942237141b8ef35495d3b74d6b2282a865
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664249"
---
# <a name="oidmap-element"></a>\<Elemento > oidMap
Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.  
  
 \<configuration>  
\<mscorlib>  
\<> cryptographySettings  
\<oidMap>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|Esegue il mapping di un OID ASN. 1 a un nome descrittivo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`cryptographySettings`|Contiene le impostazioni di crittografia.|  
|`mscorlib`|Contiene l' `cryptographySettings` elemento.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento > oidMap** per contenere un mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione di tale algoritmo hash.  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema dei file di configurazione](../index.md)
- [Schema delle impostazioni di crittografia](index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
- [Configurazione di classi di crittografia](../../configure-cryptography-classes.md)
- [Mapping di identificatori di oggetti ad algoritmi di crittografia](../../map-object-identifiers-to-cryptography-algorithms.md)
