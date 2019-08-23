---
title: <windows>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: e9f0ed9879cc42ea25b83e6b626139a40a593112
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940303"
---
# <a name="windows-of-clientcredentials-element"></a>\<> di Windows \<dell'elemento ClientCredentials >
Specifica le impostazioni per una credenziale Windows da usare per rappresentare il client.  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<endpointBehaviors>  
\<comportamento >  
\<clientCredentials>  
\<windows>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|Imposta la preferenza di rappresentazione che il client comunica al server. La modalità di rappresentazione selezionata dal client non viene imposta sul server. Di seguito vengono elencati i valori validi:<br /><br /> Identificazione Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.<br />Rappresentazione Il server può rappresentare il contesto di sicurezza del client nel sistema locale.<br />Delegazione Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.<br />Anonimo Il server non può rappresentare o identificare il client.<br />Nessuno Non è stato assegnato un livello di rappresentazione.<br /><br /> L'impostazione predefinita è Identification. L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|L'impostazione di questa proprietà su `true` consente di usare l'autenticazione NTLM se Kerberos non è disponibile.<br /><br /> L'impostazione di questa `false` proprietà su fa sì che Windows Communication Foundation (WCF) faccia il possibile tentativo di generare un'eccezione se viene utilizzata l'autenticazione NTLM. Si noti che l'impostazione di questa proprietà su `false` potrebbe non impedire l'invio di credenziali NTLM nella rete.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Specifica le credenziali usate per autenticare il client presso il servizio.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [Protezione di client](../../../wcf/securing-clients.md)
- [Uso di certificati](../../../wcf/feature-details/working-with-certificates.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
