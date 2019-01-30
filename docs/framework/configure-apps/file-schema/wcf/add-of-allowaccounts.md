---
title: <add> di <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 6edf0bc2d532deb01f24450b9868bbc240bab413
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259617"
---
# <a name="add-of-allowaccounts"></a>\<aggiungere > di \<allowAccounts >
Specifica un account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.  
  
 \<system.serviceModel.activation>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|securityIdentifier|Stringa che specifica un identificatore univoco usato per identificare un account utente. I valori predefiniti sono LocalSystem, Administrators, NS, LS e IIS_USRS.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<allowAccounts>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Una raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente i cinque identificatori predefiniti per gli account utente vengono aggiunti a questa raccolta.  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
