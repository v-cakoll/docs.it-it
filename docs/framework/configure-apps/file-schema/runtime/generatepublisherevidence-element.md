---
title: <generatePublisherEvidence> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f029131f5b10cc487021ee15e72552a26c0b04e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275847"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence > elemento
Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza per la sicurezza dall'accesso di codice (CAS).  
  
 \<configuration>  
\<runtime>  
\<generatePublisherEvidence>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Non crea <xref:System.Security.Policy.Publisher> evidenza.|  
|`true`|Crea <xref:System.Security.Policy.Publisher> evidenza. Questa è l'impostazione predefinita.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive, l'elemento non ha alcun effetto sui tempi di caricamento di assembly. Per altre informazioni, vedere la sezione "Semplificazione dei criteri di sicurezza" nella [modifiche della sicurezza](../../../../../docs/framework/security/security-changes.md).  
  
 Common language runtime (CLR) tenta di verificare la firma Authenticode in fase di caricamento per creare <xref:System.Security.Policy.Publisher> evidenza dell'assembly. Tuttavia, per impostazione predefinita, la maggior parte delle applicazioni non sono necessario <xref:System.Security.Policy.Publisher> evidenza. Criterio CAS standard non si basa sul <xref:System.Security.Policy.PublisherMembershipCondition>. È consigliabile evitare il costo di esecuzione automatica non necessari associato alla verifica della firma del server di pubblicazione, a meno che l'applicazione viene eseguita in un computer con criteri personalizzati di autorità di certificazione o non sia progettata per soddisfare le richieste per <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile. (Le richieste per le autorizzazioni di identità sempre esito positivo in un ambiente completamente attendibile).  
  
> [!NOTE]
>  È consigliabile che i servizi usano il `<generatePublisherEvidence>` elemento per migliorare le prestazioni di avvio.  Utilizzo di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato solo nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<generatePublisherEvidence>` elemento per disabilitare la verifica dei criteri dell'editore di autorità di certificazione per un'applicazione.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
