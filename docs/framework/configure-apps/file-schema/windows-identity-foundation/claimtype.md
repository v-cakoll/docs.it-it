---
title: '&lt;Tipo di attestazione&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084215"
---
# <a name="ltclaimtypegt"></a>&lt;Tipo di attestazione&gt;
Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimTypeRequired >  
\<tipo di attestazione >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Tipo di attestazione. In genere un URI. Obbligatorio.|  
|facoltativi|Valore booleano che specifica se il tipo di attestazione è facoltativo. Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.|
