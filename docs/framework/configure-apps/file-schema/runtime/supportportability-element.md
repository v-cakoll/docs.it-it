---
title: <supportPortability> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 63c309a8a93c1d31ed8f73a495cf5154c3590d56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115647"
---
# <a name="supportportability-element"></a>\<supportPortability> Elemento
Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**  
  
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
|Enabled|Attributo facoltativo.<br /><br /> Specifica se è necessario abilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Description|  
|-----------|-----------------|  
|true|Abilita il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato. Questo è il valore predefinito.|  
|false|Disabilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato. Ciò consente all'applicazione di avere riferimenti a più implementazioni dell'assembly specificato.|  
  
### <a name="child-elements"></a>Elementi figlio  

No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
  
## <a name="remarks"></a>Commenti  

A partire da .NET Framework 4, il supporto viene fornito automaticamente per le applicazioni che possono usare una delle due implementazioni del .NET Framework, ad esempio l'implementazione di .NET Framework o la .NET Framework per l'implementazione di Silverlight. Le due implementazioni di un particolare assembly di .NET Framework sono considerate equivalenti dal binder di assembly. In alcuni scenari questa funzionalità di portabilità dell'applicazione causa problemi. In questi scenari, l' `<supportPortability>` elemento può essere usato per disabilitare la funzionalità.  
  
Uno di questi scenari è costituito da un assembly che deve fare riferimento sia all'implementazione di .NET Framework sia al .NET Framework per l'implementazione Silverlight di un particolare assembly di riferimento. Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe dover fare riferimento sia all'implementazione desktop WPF, per l'interfaccia utente della finestra di progettazione, sia al subset di WPF incluso nell'implementazione di Silverlight. Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly. Questo elemento Disabilita il comportamento predefinito e consente la compilazione in modo che abbia esito positivo.  
  
> [!IMPORTANT]
> Affinché il compilatore passi le informazioni alla logica di associazione degli assembly del Common Language Runtime, è necessario usare l' `/appconfig` opzione del compilatore per specificare il percorso del file app. config che contiene questo elemento.  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente viene abilitata un'applicazione per avere riferimenti sia all'implementazione di .NET Framework sia al .NET Framework per l'implementazione Silverlight di qualsiasi assembly .NET Framework esistente in entrambe le implementazioni. `/appconfig`Per specificare il percorso del file app. config, è necessario usare l'opzione del compilatore.  
  
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
  
## <a name="see-also"></a>Vedi anche

- [-appconfig (opzioni del compilatore C#)](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- [Cenni preliminari sull'unificazione degli assembly .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))
