---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9312d25842ccfcdf84e678d34b9bfde3fe7dd0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753983"
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a>&lt;NetFx40_LegacySecurityPolicy&gt; elemento
Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.  
  
 \<configuration>  
\<runtime>  
<NetFx40_LegacySecurityPolicy>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime utilizza criteri CAS legacy.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il runtime utilizza criteri CAS legacy. Questa è l'impostazione predefinita.|  
|`true`|Il runtime utilizza criteri CAS legacy.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 3.5 e versioni precedenti, questi criteri sono sempre attivo. Nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], è necessario abilitare questi criteri.  
  
 Questi criteri sono specifica della versione. Criteri personalizzati di autorità di certificazione presenti nelle versioni precedenti di .NET Framework devono essere specificati nuovamente nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 L'applicazione di `<NetFx40_LegacySecurityPolicy>` elemento da un [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly non influisce sulla [codice SecurityTransparent](../../../../../docs/framework/misc/security-transparent-code.md); vengono comunque applicate le regole di trasparenza.  
  
> [!IMPORTANT]
>  L'applicazione di `<NetFx40_LegacySecurityPolicy>` elemento può comportare sanzioni significativo delle prestazioni per gli assembly di immagini native creati dal [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) che non sono installati nel [cache assembly globali ](../../../../../docs/framework/app-domains/gac.md). La riduzione delle prestazioni è causato dall'impossibilità di runtime per caricare gli assembly come le immagini native quando viene applicato l'attributo, che che siano caricati gli assembly come just-in-time.  
  
> [!NOTE]
>  Se si specifica una versione di .NET Framework di destinazione che è anteriore di [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] nelle impostazioni del progetto per il progetto di Visual Studio, criteri di sicurezza verranno abilitato, inclusi eventuali criteri personalizzati di autorità di certificazione specificata per tale versione. Tuttavia, non sarà in grado di utilizzare i nuovi [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] tipi e membri. È inoltre possibile specificare una versione precedente di .NET Framework tramite il [ \<supportedRuntime > elemento](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) nello schema delle impostazioni di avvio nel [file di configurazione applicazione](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  Sintassi del file di configurazione è tra maiuscole e minuscole. Utilizzare la sintassi fornita nella sezione esempio e la sintassi.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato solo nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare i criteri CAS legacy per un'applicazione.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
