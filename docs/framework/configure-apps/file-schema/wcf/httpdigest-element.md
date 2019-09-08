---
title: <httpDigest> Elemento
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 121df39c7e4ce4de5c1f0ef87921f6269d7cc1c0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785832"
---
# <a name="httpdigest-element"></a>\<Elemento > httpDigest
Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> httpDigest**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`impersonationLevel`|Imposta la preferenza di rappresentazione che il client comunica al server. La modalità di rappresentazione selezionata dal client non viene imposta sul server. Di seguito vengono elencati i valori validi:<br /><br /> Identificazione Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.<br />Rappresentazione Il server può rappresentare il contesto di sicurezza del client nel sistema locale.<br />Delegazione Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.<br />Anonimo Il server non può rappresentare o identificare il client.<br />Nessuno Non è stato assegnato un livello di rappresentazione.<br /><br /> L'impostazione predefinita è Identification. L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Specifica le credenziali usate per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Un digest è un hash determinato mediante un algoritmo e un insieme di input. L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input. Il client può calcolare l'hash e inviarlo al servizio. Il servizio calcola anche l'hash e confronta i valori. Una corrispondenza convalida il client.  
  
 Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS). Per ulteriori informazioni, vedere [autenticazione del digest in IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Uso di certificati](../../../wcf/feature-details/working-with-certificates.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
