---
title: '&lt;relativeBindForResources&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3aa3ca9c9d0e64b2290b503f09b83140b4d029b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534796"
---
# <a name="ltrelativebindforresourcesgt-element"></a>&lt;relativeBindForResources&gt; Element
Ottimizza le ricerche degli assembly satellite.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<relativeBindForResources > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se tramite Common Language Runtime vengono ottimizzate le ricerche degli assembly satellite.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Tramite il runtime non vengono ottimizzate le ricerche degli assembly satellite. Rappresenta il valore predefinito.|  
|`true`|Tramite il runtime vengono ottimizzate le ricerche degli assembly satellite.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 In generale, Resource Manager vengono cercate le risorse, come documentato nel [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) argomento. Ciò significa che per la ricerca di una particolare versione localizzata di una risorsa da parte di Gestione risorse l'operazione potrebbe essere eseguita nella Global Assembly Cache, in una cartella di impostazioni cultura specifiche nella codebase dell'applicazione, potrebbe essere eseguita una query su Windows Installer per gli assembly satellite e potrebbe essere generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>. Tramite l'elemento `<relativeBindForResources>` viene ottimizzata la modalità di ricerca degli assembly satellite tramite Gestione Risorse. Le prestazioni possono migliorare durante la ricerca delle risorse nei seguenti casi:  
  
-   Quando l'assembly satellite viene distribuito nello stesso percorso dell'assembly di codice. In altre parole, se l'assembly di codice è installato nella Global Assembly Cache, anche gli assembly satellite devono essere installati in questa posizione. Se l'assembly di codice è installato nella codebase dell'applicazione, anche gli assembly satellite devono essere installati in una cartella di impostazioni cultura specifiche nella codebase.  
  
-   Quando Windows Installer non viene utilizzato o viene utilizzato solo raramente per installazioni su richiesta di assembly satellite.  
  
-   Quando l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> non viene gestito dal codice dell'applicazione.  
  
 L'impostazione dell'attributo `enabled` dell'elemento `<relativeBindForResources>` su `true` consente di ottimizzare la ricerca di assembly satellite da parte di Gestione risorse nel modo seguente:  
  
-   Viene utilizzato il percorso dell'assembly del codice padre per cercare l'assembly satellite.  
  
-   Non viene eseguita una query su Windows Installer per gli assembly satellite.  
  
-   Non viene generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche
- [Creazione del pacchetto e distribuzione delle risorse](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
