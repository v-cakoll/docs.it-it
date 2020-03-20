---
title: <relativeBindForResources> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153906"
---
# <a name="relativebindforresources-element"></a>\<elemento> relativeBindForResources
Ottimizza le ricerche degli assembly satellite.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se tramite Common Language Runtime vengono ottimizzate le ricerche degli assembly satellite.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`false`|Tramite il runtime non vengono ottimizzate le ricerche degli assembly satellite. Si tratta del valore predefinito.|  
|`true`|Tramite il runtime vengono ottimizzate le ricerche degli assembly satellite.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
 In generale, Resource Manager esegue il probe per le risorse, come documentato nell'argomento [Packaging and Deploying Resources.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Ciò significa che per la ricerca di una particolare versione localizzata di una risorsa da parte di Gestione risorse l'operazione potrebbe essere eseguita nella Global Assembly Cache, in una cartella di impostazioni cultura specifiche nella codebase dell'applicazione, potrebbe essere eseguita una query su Windows Installer per gli assembly satellite e potrebbe essere generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>. Tramite l'elemento `<relativeBindForResources>` viene ottimizzata la modalità di ricerca degli assembly satellite tramite Gestione Risorse. Le prestazioni possono migliorare durante la ricerca delle risorse nei seguenti casi:  
  
- Quando l'assembly satellite viene distribuito nello stesso percorso dell'assembly di codice. In altre parole, se l'assembly di codice è installato nella Global Assembly Cache, anche gli assembly satellite devono essere installati in questa posizione. Se l'assembly di codice è installato nella codebase dell'applicazione, anche gli assembly satellite devono essere installati in una cartella di impostazioni cultura specifiche nella codebase.  
  
- Quando Windows Installer non viene utilizzato o viene utilizzato solo raramente per installazioni su richiesta di assembly satellite.  
  
- Quando l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> non viene gestito dal codice dell'applicazione.  
  
 L'impostazione dell'attributo `enabled` dell'elemento `<relativeBindForResources>` su `true` consente di ottimizzare la ricerca di assembly satellite da parte di Gestione risorse nel modo seguente:  
  
- Viene utilizzato il percorso dell'assembly del codice padre per cercare l'assembly satellite.  
  
- Non viene eseguita una query su Windows Installer per gli assembly satellite.  
  
- Non viene generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
