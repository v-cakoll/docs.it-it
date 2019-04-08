---
title: <supportPortability> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1c3236ed2d79592bca46e925c9f67e5ac9c51
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675335"
---
# <a name="supportportability-element"></a>\<supportPortability > elemento
Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<assemblyBinding > elemento  
\<supportPortability > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|PKT|Attributo obbligatorio.<br /><br /> Specifica il token di chiave pubblica dell'assembly interessato, sotto forma di stringa.|  
|enabled|Attributo facoltativo.<br /><br /> Specifica se deve essere abilitato il supporto per la portabilità tra diverse implementazioni dell'assembly .NET Framework specificato.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|Abilitare il supporto per la portabilità tra diverse implementazioni dell'assembly .NET Framework specificato. Questa è l'impostazione predefinita.|  
|False|Disabilitare il supporto per la portabilità tra diverse implementazioni dell'assembly .NET Framework specificato. In questo modo l'applicazione affinché i riferimenti a più implementazioni dell'assembly specificato.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
  
## <a name="remarks"></a>Note  
 A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], il supporto viene fornito automaticamente per le applicazioni che è possono usare uno dei due implementazioni di .NET Framework, ad esempio l'implementazione di .NET Framework o .NET Framework per l'implementazione di Silverlight. Le due implementazioni di un particolare assembly di .NET Framework sono considerate equivalenti dal binder di assembly. In alcuni scenari, questa funzionalità di portabilità dell'applicazione può causare problemi. In questi scenari il `<supportPortability>` elemento può essere usato per disabilitare la funzionalità.  
  
 Uno scenario di questo tipo è un assembly che deve fare riferimento sia l'implementazione di .NET Framework e .NET Framework per l'implementazione di Silverlight di un particolare assembly di riferimento. Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe essere necessario fare riferimento a entrambi l'implementazione Desktop WPF, per interfaccia utente della finestra di progettazione e il subset di WPF è incluso nell'implementazione di Silverlight. Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly. Questo elemento consente di disattivare il comportamento predefinito e consente la compilazione abbia esito positivo.  
  
> [!IMPORTANT]
>  Affinché il compilatore può passare le informazioni per la logica di associazione degli assembly di common language runtime, è necessario usare il `/appconfig` opzione del compilatore per specificare il percorso del file app. config che contiene questo elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente Abilita i riferimenti sia l'implementazione di .NET Framework a .NET Framework per Silverlight per qualsiasi assembly di .NET Framework presente in entrambe le implementazioni a un'applicazione. Il `/appconfig` opzione del compilatore deve essere usata per specificare il percorso del file app. config.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [/appconfig (opzioni del compilatore C#)](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- [Cenni preliminari sull'unificazione degli Assembly di .NET framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))
