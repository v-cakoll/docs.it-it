---
title: <disableFusionUpdatesFromADManager> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: 4e7375fddaa98b45766b29d911d555f773edcafa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117448"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager> Elemento
Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|Enabled|Attributo obbligatorio.<br /><br /> Specifica se la capacità predefinita di eseguire l'override delle impostazioni Fusion è disabilitata.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Non disabilitare la possibilità di eseguire l'override delle impostazioni Fusion. Si tratta del comportamento predefinito, a partire da .NET Framework 4.|  
|1|Disabilitare la possibilità di eseguire l'override delle impostazioni Fusion. In questo modo viene ripristinato il comportamento delle versioni precedenti del .NET Framework.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Commenti  
 A partire da .NET Framework 4, il comportamento predefinito consiste nel consentire all' <xref:System.AppDomainManager> oggetto di eseguire l'override delle impostazioni di configurazione usando la <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà o il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo dell' <xref:System.AppDomainSetup> oggetto passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo, nella sottoclasse di <xref:System.AppDomainManager> . Per il dominio applicazione predefinito, le impostazioni modificate sostituiscono le impostazioni specificate dal file di configurazione dell'applicazione. Per gli altri domini applicazione, sostituiscono le impostazioni di configurazione passate al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> metodo o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .  
  
 È possibile passare le nuove informazioni di configurazione o passare null ( `Nothing` in Visual Basic) per eliminare le informazioni di configurazione passate.  
  
 Non passare le informazioni di configurazione sia alla <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà che al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo. Se si passano le informazioni di configurazione a entrambe, le informazioni passate alla <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà vengono ignorate, perché il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo esegue l'override delle informazioni di configurazione dal file di configurazione dell'applicazione. Se si usa la <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà, è possibile passare null ( `Nothing` in Visual Basic) al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo per eliminare tutti i byte di configurazione specificati nella chiamata al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> metodo o.  
  
 Oltre alle informazioni di configurazione, è possibile modificare le impostazioni seguenti nell' <xref:System.AppDomainSetup> oggetto passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Metodo: <xref:System.AppDomainSetup.ApplicationBase%2A> ,, <xref:System.AppDomainSetup.ApplicationName%2A> <xref:System.AppDomainSetup.CachePath%2A> , <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A> , <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> , <xref:System.AppDomainSetup.DynamicBase%2A> , <xref:System.AppDomainSetup.LoaderOptimization%2A> , <xref:System.AppDomainSetup.PrivateBinPath%2A> , <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> , <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> e <xref:System.AppDomainSetup.ShadowCopyFiles%2A> .  
  
 In alternativa all'uso dell' `<disableFusionUpdatesFromADManager>` elemento, è possibile disabilitare il comportamento predefinito creando un'impostazione del registro di sistema o impostando una variabile di ambiente. Nel registro di sistema creare un valore DWORD denominato `COMPLUS_disableFusionUpdatesFromADManager` in `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework` , quindi impostare il valore su 1. Nella riga di comando impostare la variabile di ambiente `COMPLUS_disableFusionUpdatesFromADManager` su 1.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare la possibilità di eseguire l'override delle impostazioni Fusion utilizzando l' `<disableFusionUpdatesFromADManager>` elemento.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Modalità di individuazione degli assembly da parte del runtime](../../../deployment/how-the-runtime-locates-assemblies.md)
