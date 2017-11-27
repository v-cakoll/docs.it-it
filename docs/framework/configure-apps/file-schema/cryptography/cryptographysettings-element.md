---
title: '&lt;cryptographySettings&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0f023dbc3049f558acfc0fb83056f462d390fa7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptographysettingsgt-element"></a>&lt;cryptographySettings&gt; elemento
Contiene le impostazioni di crittografia.  
  
 \<configuration>  
\<mscorlib >  
\<cryptographySettings >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cryptoNameMapping >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Contiene i mapping di classi e nomi descrittivi.|  
|[\<oidMap >](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Contiene i mapping di ASN. 1 oggetto (OID) identificatore alle classi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`mscorlib`|Contiene il `cryptographySettings` elemento.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il  **\<cryptographySettings >** per contenere i mapping dei nomi di crittografia e degli OID. In questo esempio viene configurato in modo che <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> restituisce un `MyHashClass` oggetto e `MyCryptoClass` classe esegue il mapping all'identificatore di oggetto 1.3.36.2.1.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
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
