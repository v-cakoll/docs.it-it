---
title: <appDomainManagerAssembly> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154427"
---
# <a name="appdomainmanagerassembly-element"></a>\<Elemento> appDomainManagerAssembly
Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>appDomainManagerAssembly**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio. Specifica il nome visualizzato dell'assembly che fornisce il gestore del dominio applicazione per il dominio applicazione predefinito nel processo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 Per specificare il tipo di gestore del dominio applicazione, è necessario specificare sia questo elemento che l'elemento [ \<>appDomainManagerType.](appdomainmanagertype-element.md) Se uno di questi elementi non è specificato, l'altro viene ignorato.  
  
 Quando viene caricato il <xref:System.TypeLoadException> dominio applicazione predefinito, viene generata se l'assembly specificato non esiste o se l'assembly non contiene il tipo specificato dall'elemento [ \<>appDomainManagerType;](appdomainmanagertype-element.md) e il processo non si avvia. Se l'assembly viene trovato ma le <xref:System.IO.FileLoadException> informazioni sulla versione non corrispondono, viene generata un'eccezione .  
  
 Quando si specifica il tipo di gestore del dominio applicazione per il dominio applicazione predefinito, gli altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore del dominio applicazione. Utilizzare <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> le <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> proprietà e per specificare un tipo di gestore del dominio applicazione diverso per un nuovo dominio applicazione.  
  
 Per specificare il tipo di gestore del dominio applicazione, è necessario che l'applicazione disponga dell'attendibilità totale. Ad esempio, un'applicazione in esecuzione sul desktop dispone di attendibilità totale. Se l'applicazione non dispone <xref:System.TypeLoadException> di attendibilità totale, viene generata un'eccezione .  
  
 Per il formato del nome visualizzato <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> dell'assembly, vedere la proprietà .  
  
 Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il gestore `MyMgr` del dominio `AdMgrExample` applicazione per il dominio applicazione predefinito di un processo è il tipo nell'assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<Elemento> appDomainManagerType](appdomainmanagertype-element.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Metodo SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
