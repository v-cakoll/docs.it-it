---
title: '&lt;bypassTrustedAppStrongNames&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0343aef083076249325b9577f90964d066867f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a>&lt;bypassTrustedAppStrongNames&gt; elemento
Specifica se ignorare la convalida di nomi sicuri per gli assembly con attendibilità che vengono caricati in un oggetto attendibilità <xref:System.AppDomain>.  
  
 \<configuration>  
\<runtime >  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se è abilitata la funzionalità che consente di evitare la convalida di nomi sicuri agli assembly totalmente attendibili. Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati correttezza quando l'assembly viene caricato. Il valore predefinito è `true`.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Le firme con nome sicuro su assembly con attendibilità non vengono convalidate quando gli assembly vengono caricati in un oggetto attendibilità <xref:System.AppDomain>. Questa è l'impostazione predefinita.|  
|`false`|Le firme con nome sicuro su assembly con attendibilità vengono convalidate quando gli assembly vengono caricati in un oggetto attendibilità <xref:System.AppDomain>. La firma nome sicuro viene verificata solo la correttezza di firma; non verrà confrontato con un altro nome sicuro per trovare una corrispondenza.|  
  
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
  
-   Completamente attendibile senza il <xref:System.Security.Policy.StrongName> evidenza (ad esempio, ha `MyComputer` prova della zona).  
  
-   Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.  
  
-   Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.  
  
-   Non ha firma ritardata.  
  
> [!NOTE]
>  Se questa funzionalità è stata disattivata per tutte le applicazioni del computer tramite una chiave del Registro di sistema, questa impostazione del file di configurazione non ha alcun effetto. Per ulteriori informazioni, vedere [procedura: disabilitare la funzionalità di Bypass del nome sicuro](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma nome sicuro su assembly totalmente attendibili.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
