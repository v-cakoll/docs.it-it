---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: eedf0ce6cf75b8fb56daf98f2005e66162ce10d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155654"
---
# <a name="usemanagedpresentation"></a>\<useManagedPresentation>
Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust. Questo elemento non ha attributo e è presente come un'opzione vuota.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<useManagedPresentation>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust. I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
