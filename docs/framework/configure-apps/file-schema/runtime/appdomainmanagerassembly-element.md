---
title: <appDomainManagerAssembly> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a293af73fde5ee72ba02c7e6613e9c57eae1b9b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658952"
---
# <a name="appdomainmanagerassembly-element"></a>\<Elemento > appDomainManagerAssembly
Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.  
  
 \<configuration>  
\<runtime>  
\<appDomainManagerAssembly>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio. Specifica il nome visualizzato dell'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento sia l' [ \<elemento > AppDomainManagerType](appdomainmanagertype-element.md) . Se uno di questi elementi non è specificato, l'altro viene ignorato.  
  
 Quando viene caricato il dominio applicazione predefinito, <xref:System.TypeLoadException> viene generata un'eccezione se l'assembly specificato non esiste o se l'assembly non contiene il tipo specificato [ \<dall'elemento > AppDomainManagerType](appdomainmanagertype-element.md) e il processo non riesce iniziare. Se l'assembly viene trovato ma le informazioni sulla versione non corrispondono, viene <xref:System.IO.FileLoadException> generata un'eccezione.  
  
 Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore di dominio dell'applicazione. Usare le <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> proprietà <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> e per specificare un tipo di gestore di dominio dell'applicazione diverso per un nuovo dominio applicazione.  
  
 Per specificare il tipo di gestore di dominio applicazione è necessario che l'applicazione disponga di attendibilità totale. Ad esempio, un'applicazione in esecuzione sul desktop ha attendibilità totale. Se l'applicazione non dispone di attendibilità totale, <xref:System.TypeLoadException> viene generata un'eccezione.  
  
 Per il formato del nome visualizzato dell'assembly, vedere la <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> proprietà.  
  
 Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il gestore di dominio dell'applicazione per il dominio applicazione predefinito di un processo `MyMgr` è il tipo `AdMgrExample` nell'assembly.  
  
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
- [\<Elemento > appDomainManagerType](appdomainmanagertype-element.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Metodo SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
