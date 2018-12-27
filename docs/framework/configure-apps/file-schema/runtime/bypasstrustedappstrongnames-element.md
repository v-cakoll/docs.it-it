---
title: '&lt;bypassTrustedAppStrongNames&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59fe6beb359575c818131e1ae502fdebcec5096c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613752"
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a>&lt;bypassTrustedAppStrongNames&gt; elemento
Specifica se ignorare la convalida di nomi sicuri per gli assembly con attendibilità che vengono caricati con attendibilità <xref:System.AppDomain>.  
  
 \<configuration>  
\<runtime>  
\<bypassTrustedAppStrongNames >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se è abilitata la funzionalità che consente di evitare la convalida di nomi sicuri agli assembly completamente attendibili. Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati la correttezza quando l'assembly viene caricato. Il valore predefinito è `true`.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Le firme con nome sicuro su assembly con attendibilità non vengono convalidate quando gli assembly vengono caricati in un oggetto attendibilità <xref:System.AppDomain>. Questa è l'impostazione predefinita.|  
|`false`|Le firme con nome sicuro su assembly con attendibilità vengono convalidate quando gli assembly vengono caricati in un oggetto attendibilità <xref:System.AppDomain>. La firma con nome sicuro viene controllata solo la correttezza della firma; non verrà confrontato a un altro nome sicuro per trovare una corrispondenza.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Questa funzionalità con nome sicuro evita l'overhead della verifica della firma con nome sicuro di assembly completamente attendibili.  
  
 Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:  
  
-   Completamente attendibile senza il <xref:System.Security.Policy.StrongName> evidenza (ad esempio, ha `MyComputer` evidenza della zona).  
  
-   Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.  
  
-   Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.  
  
-   Non ha firma ritardata.  
  
> [!NOTE]
>  Se questa funzionalità è stata disattivata per tutte le applicazioni nel computer usando una chiave del Registro di sistema, questa impostazione di file di configurazione non ha alcun effetto. Per altre informazioni, vedere [Procedura: Disabilitare la funzionalità di ignorare il nome sicuro](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro su assembly completamente attendibili.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Procedura: Disabilitare la funzionalità di ignorare il nome sicuro](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
