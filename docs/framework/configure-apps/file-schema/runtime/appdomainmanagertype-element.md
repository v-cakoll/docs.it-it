---
title: <appDomainManagerType> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: bae4aa39f9c43480ac2ef984f78834b68646742d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118235"
---
# <a name="appdomainmanagertype-element"></a>\<elemento > appDomainManagerType
Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerType >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio. Specifica il nome del tipo, incluso lo spazio dei nomi, che funge da gestore del dominio dell'applicazione per il dominio applicazione predefinito nel processo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento sia l'elemento [\<> AppDomainManagerAssembly](appdomainmanagerassembly-element.md) . Se uno di questi elementi non è specificato, l'altro viene ignorato.  
  
 Quando viene caricato il dominio applicazione predefinito, viene generata <xref:System.TypeLoadException> se il tipo specificato non esiste nell'assembly specificato dall'elemento [\<AppDomainManagerAssembly](appdomainmanagerassembly-element.md) . e il processo non viene avviato.  
  
 Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore di dominio dell'applicazione. Usare le proprietà <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> e <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> per specificare un tipo di gestore di dominio dell'applicazione diverso per un nuovo dominio applicazione.  
  
 Per specificare il tipo di gestore di dominio applicazione è necessario che l'applicazione disponga di attendibilità totale. Ad esempio, un'applicazione in esecuzione sul desktop ha attendibilità totale. Se l'applicazione non dispone di attendibilità totale, viene generata un'<xref:System.TypeLoadException>.  
  
 Il formato del tipo e dello spazio dei nomi è identico a quello usato per la proprietà <xref:System.Type.FullName%2A?displayProperty=nameWithType>.  
  
 Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il gestore di dominio dell'applicazione per il dominio applicazione predefinito di un processo è il tipo `MyMgr` nell'assembly `AdMgrExample`.  
  
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
- [\<elemento > appDomainManagerAssembly](appdomainmanagerassembly-element.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Metodo SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
