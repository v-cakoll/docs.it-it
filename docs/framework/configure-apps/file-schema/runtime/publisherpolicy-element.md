---
title: '&lt;publisherPolicy&gt; elemento'
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
ms.openlocfilehash: 2cc3b7220fe34f5dc049a3da71b160a88f82fdb1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltpublisherpolicygt-element"></a>&lt;publisherPolicy&gt; elemento
Specifica se il runtime applica i criteri dell'editore.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding >  
\<dependentAssembly >  
\<publisherPolicy >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`apply`|Specifica se applicare i criteri dell'editore.|  
  
## <a name="apply-attribute"></a>applicare l'attributo  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`yes`|Applica i criteri dell'editore. Questa è l'impostazione predefinita.|  
|`no`|Non si applica i criteri dell'editore.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando un fornitore del componente rilascia una nuova versione di un assembly, può includere i criteri dell'editore in modo da applicazioni che utilizzano la versione precedente a questo punto utilizzare la nuova versione. Per specificare se applicare i criteri dell'editore per un particolare assembly, inserire il  **\<publisherPolicy >** elemento il  **\<dependentAssembly >** elemento.  
  
 L'impostazione predefinita per il **applicare** attributo **Sì**. L'impostazione di **applicare** attributo **non** sostituzioni precedenti **Sì** le impostazioni per un assembly.  
  
 Autorizzazione è necessaria per un'applicazione ignorare in modo esplicito criteri editore utilizzando il [ \<publisherPolicy applicare = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione. L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag di <xref:System.Security.Permissions.SecurityPermission>. Per ulteriori informazioni, vedere [autorizzazione di sicurezza il reindirizzamento di Assembly](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di disattivare i criteri dell'editore per l'assembly, `myAssembly`.  
  
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
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Reindirizzamento delle versioni di assembly](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
