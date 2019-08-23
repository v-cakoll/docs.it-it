---
title: <oidEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: cbdf6150010ca2dace3f0610d9caa90c2bf52746
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921050"
---
# <a name="oidentry-element"></a>\<Elemento > oidEntry
Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.  
  
 \<configuration>  
\<mscorlib>  
\<> cryptographySettings  
\<oidMap>  
\<oidEntry>  
  
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
|**name**|Attributo obbligatorio.<br /><br /> Specifica il valore per l'attributo **Name** nel tag del [ \<> nameEntry](nameentry-element.md) .|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`cryptographySettings`|Contiene le impostazioni di crittografia.|  
|`mscorlib`|Contiene l' `cryptographySettings` elemento.|  
|`oidMap`|Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.|  
  
## <a name="remarks"></a>Note  
 Gli identificatori di oggetto ASN. 1 identificano gli algoritmi in alcuni formati crittografici. Eseguire il mapping degli identificatori di oggetto ai nomi descrittivi per gli algoritmi che si desidera identificare.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il **\<oidEntry >** elemento per eseguire il mapping di un identificatore di oggetto per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo di hash.  
  
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

- [Schema dei file di configurazione](../index.md)
- [Schema delle impostazioni di crittografia](index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
- [Configurazione di classi di crittografia](../../configure-cryptography-classes.md)
- [Mapping di identificatori di oggetti ad algoritmi di crittografia](../../map-object-identifiers-to-cryptography-algorithms.md)
