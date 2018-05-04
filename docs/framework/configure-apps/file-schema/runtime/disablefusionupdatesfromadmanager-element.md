---
title: '&lt;disableFusionUpdatesFromADManager&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e5e33cd3d250b26f0a83a87c4f7ce438af22e96
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a>&lt;disableFusionUpdatesFromADManager&gt; elemento
Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<disableFusionUpdatesFromADManager >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se l'opzione predefinita di eseguire l'override delle impostazioni Fusion è disabilitato.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Non disabilitare la possibilità di eseguire l'override delle impostazioni Fusion. Si tratta del comportamento predefinito, a partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
|1|Disabilitare la possibilità di eseguire l'override delle impostazioni Fusion. Viene ripristinato il comportamento delle versioni precedenti di .NET Framework.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], il comportamento predefinito consiste nel consentire la <xref:System.AppDomainManager> oggetto per eseguire l'override delle impostazioni di configurazione utilizzando il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà o <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo il <xref:System.AppDomainSetup> oggetto che viene passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> (metodo), in una sottoclasse di <xref:System.AppDomainManager>. Per il dominio applicazione predefinito, le impostazioni modificate si sostituiscono le impostazioni specificate dal file di configurazione dell'applicazione. Per altri domini applicazione, sostituiscono le impostazioni di configurazione che sono state passate al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> metodo.  
  
 È possibile passare nuove informazioni di configurazione o passare null (`Nothing` in Visual Basic) per eliminare le informazioni di configurazione che è state passate.  
  
 Non passare le informazioni di configurazione sia il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà e <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo. Se si passano le informazioni di configurazione per entrambi, le informazioni passate per il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà viene ignorata, poiché il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo esegue l'override delle informazioni di configurazione dal file di configurazione dell'applicazione. Se si utilizza il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà, è possibile passare null (`Nothing` in Visual Basic) per il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> eliminare qualsiasi byte di configurazione che sono state specificate nella chiamata al metodo di <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> (metodo).  
  
 Oltre alle informazioni di configurazione, è possibile modificare le impostazioni seguenti nella <xref:System.AppDomainSetup> oggetto che viene passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, e <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Come alternativa all'utilizzo di `<disableFusionUpdatesFromADManager>` elemento, è possibile disabilitare il comportamento predefinito creando un'impostazione del Registro di sistema o impostando una variabile di ambiente. Nel Registro di sistema, creare un valore DWORD denominato `COMPLUS_disableFusionUpdatesFromADManager` in `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`e impostare il valore su 1. Nella riga di comando, impostare la variabile di ambiente `COMPLUS_disableFusionUpdatesFromADManager` su 1.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare la possibilità di eseguire l'override delle impostazioni Fusion utilizzando il `<disableFusionUpdatesFromADManager>` elemento.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
