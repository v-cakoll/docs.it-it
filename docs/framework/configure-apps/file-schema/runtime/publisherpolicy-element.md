---
title: <publisherPolicy> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252386"
---
# <a name="publisherpolicy-element"></a>\<Elemento > publisherPolicy apply
Specifica se il runtime applica i criteri dell'editore.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di associazione**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dependentAssembly**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> publisherPolicy apply**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`apply`|Specifica se applicare i criteri dell'editore.|  
  
## <a name="apply-attribute"></a>applica attributo  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`yes`|Applica i criteri dell'editore. Questa è l'impostazione predefinita.|  
|`no`|Non applica i criteri dell'editore.|  
  
### <a name="child-elements"></a>Elementi figlio  

Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`dependentAssembly`|Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly. Usare un `<dependentAssembly>` elemento per ogni assembly.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando un fornitore di componenti rilascia una nuova versione di un assembly, il fornitore può includere un criterio editore, in modo che le applicazioni che usano la versione precedente usino ora la nuova versione. Per specificare se applicare i criteri dell'editore per un particolare assembly, inserire l'  **\<elemento > publisherPolicy apply** nell'elemento  **\<> di dependentAssembly** .  
  
 L'impostazione predefinita per l'attributo **Apply** è **Sì**. L'impostazione dell'attributo **Apply** su **No** sostituisce le impostazioni **Yes** precedenti di un assembly.  
  
 L'autorizzazione è necessaria affinché un'applicazione ignori esplicitamente i criteri del server di pubblicazione usando l' [ \<elemento publisherPolicy apply Apply = "No"/>](publisherpolicy-element.md) nel file di configurazione dell'applicazione. L'autorizzazione viene concessa impostando <xref:System.Security.Permissions.SecurityPermissionFlag> il flag <xref:System.Security.Permissions.SecurityPermission>su. Per altre informazioni, vedere [autorizzazione di sicurezza](../../assembly-binding-redirection-security-permission.md)per il reindirizzamento dell'associazione di assembly.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono disattivati i criteri dell'editore `myAssembly`per l'assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Come il runtime individua gli assembly](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Reindirizzamento delle versioni di assembly](../../redirect-assembly-versions.md)
