---
title: '&lt;supportPortability&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52ef9cce9ee28c6329f688bb9ac751f0f9016657
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltsupportportabilitygt-element"></a>&lt;supportPortability&gt; elemento
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
|enabled|Attributo facoltativo.<br /><br /> Specifica se deve essere abilitato il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|Abilitare il supporto per la portabilità tra implementazioni dell'assembly .NET Framework specificato. Questa è l'impostazione predefinita.|  
|False|Disabilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato. In questo modo l'applicazione di riferimenti a più implementazioni dell'assembly specificato.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
  
## <a name="remarks"></a>Note  
 A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], il supporto viene fornito automaticamente per le applicazioni che è possono utilizzare uno dei due implementazioni di .NET Framework, ad esempio l'implementazione di .NET Framework o .NET Framework per Silverlight. Le due implementazioni di un particolare assembly di .NET Framework vengono considerate equivalenti dal gestore di associazione di assembly. In alcuni scenari, questa funzionalità di portabilità dell'applicazione può causare problemi. In tali scenari, il `<supportPortability>` elemento può essere usato per disabilitare la funzionalità.  
  
 Uno scenario di questo tipo è un assembly che deve fare riferimento all'implementazione di .NET Framework sia .NET Framework per Silverlight di implementazione di un particolare assembly di riferimento. Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe essere necessario fare riferimento sia all'implementazione Desktop WPF, per l'interfaccia utente della finestra di progettazione e il subset di WPF incluso nell'implementazione di Silverlight. Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly. Questo elemento disabilita il comportamento predefinito e consente la compilazione abbia esito positivo.  
  
> [!IMPORTANT]
>  Affinché il compilatore passare le informazioni per la logica di associazione di assembly di common language runtime, è necessario utilizzare il `/appconfig` l'opzione del compilatore per specificare il percorso del file app. config che contiene questo elemento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente a un'applicazione di riferimenti all'implementazione di .NET Framework sia .NET Framework per Silverlight di implementazione di un assembly di .NET Framework presente in entrambe le implementazioni. Il `/appconfig` opzione del compilatore deve essere usata per specificare il percorso del file app. config.  
  
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
 [/appconfig (opzioni del compilatore c#)](http://msdn.microsoft.com/library/ee523958.aspx)  
 [Panoramica di unificazione degli Assembly di .NET framework](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
