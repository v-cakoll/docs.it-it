---
title: <disableFusionUpdatesFromADManager> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c8c1cac68aca1c40826ff549d62d9636d9b0c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085883"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager > elemento
Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<disableFusionUpdatesFromADManager>  
  
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
 Inizia con il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], è il comportamento predefinito per consentire la <xref:System.AppDomainManager> oggetto eseguire l'override delle impostazioni di configurazione tramite il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà o il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo del <xref:System.AppDomainSetup> oggetto che viene passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo, in una sottoclasse di <xref:System.AppDomainManager>. Per il dominio applicazione predefinito, le impostazioni modificate si sostituiscono le impostazioni specificate per il file di configurazione dell'applicazione. Per altri domini applicazione, queste sostituiscono le impostazioni di configurazione che sono state passate per il <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> (metodo).  
  
 È possibile passare nuove informazioni di configurazione, o passa un valore null (`Nothing` in Visual Basic) per eliminare le informazioni di configurazione che è state passate.  
  
 Non passare le informazioni di configurazione su entrambi i <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà e il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> (metodo). Se si passa le informazioni di configurazione su entrambi, le informazioni passate per il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà viene ignorata, perché il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo esegue l'override delle informazioni di configurazione dal file di configurazione dell'applicazione. Se si usa la <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà, è possibile passare null (`Nothing` in Visual Basic) per il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> per eliminare qualsiasi byte di configurazione che sono state specificate nella chiamata al metodo il <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> (metodo).  
  
 Oltre alle informazioni di configurazione, è possibile modificare le impostazioni seguenti nel <xref:System.AppDomainSetup> oggetto che viene passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, e <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Come alternativa all'uso di `<disableFusionUpdatesFromADManager>` elemento, è possibile disabilitare il comportamento predefinito tramite la creazione di un'impostazione del Registro di sistema oppure impostando una variabile di ambiente. Nel Registro di sistema, creare un valore DWORD denominato `COMPLUS_disableFusionUpdatesFromADManager` sotto `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`e impostare il valore su 1. Nella riga di comando, impostare la variabile di ambiente `COMPLUS_disableFusionUpdatesFromADManager` su 1.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare la possibilità di eseguire l'override delle impostazioni Fusion usando il `<disableFusionUpdatesFromADManager>` elemento.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
