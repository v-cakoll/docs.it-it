---
title: <appDomainManagerType> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154426"
---
# <a name="appdomainmanagertype-element"></a>\<Elemento> appDomainManagerType
Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>appDomainManagerType**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio. Specifica il nome del tipo, incluso lo spazio dei nomi, che funge da gestore del dominio applicazione per il dominio applicazione predefinito nel processo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 Per specificare il tipo di gestore del dominio applicazione, è necessario specificare sia questo elemento che l'elemento [ \<>appDomainManagerAssembly.](appdomainmanagerassembly-element.md) Se uno di questi elementi non è specificato, l'altro viene ignorato.  
  
 Quando viene caricato il <xref:System.TypeLoadException> dominio applicazione predefinito, viene generata se il tipo specificato non esiste nell'assembly specificato dall'elemento [ \<appDomainManagerAssembly>;](appdomainmanagerassembly-element.md) e il processo non si avvia.  
  
 Quando si specifica il tipo di gestore del dominio applicazione per il dominio applicazione predefinito, gli altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore del dominio applicazione. Utilizzare <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> le <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> proprietà e per specificare un tipo di gestore del dominio applicazione diverso per un nuovo dominio applicazione.  
  
 Per specificare il tipo di gestore del dominio applicazione, è necessario che l'applicazione disponga dell'attendibilità totale. Ad esempio, un'applicazione in esecuzione sul desktop dispone di attendibilità totale. Se l'applicazione non dispone <xref:System.TypeLoadException> di attendibilità totale, viene generata un'eccezione .  
  
 Il formato del tipo e dello spazio dei <xref:System.Type.FullName%2A?displayProperty=nameWithType> nomi è lo stesso formato utilizzato per la proprietà.  
  
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
- [\<Elemento> appDomainManagerAssembly](appdomainmanagerassembly-element.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Metodo SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
