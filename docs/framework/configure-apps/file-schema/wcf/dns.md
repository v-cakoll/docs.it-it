---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452227"
---
# <a name="dns"></a>> DNS \<
Specifica l'identità prevista del server. Questa identità è valida per la modalità di autenticazione tramite certificato X509 se il certificato del server contiene un DNS con lo stesso valore. Questa identità è inoltre valida per la modalità di autenticazione Windows se il nome SPN presenta lo stesso valore.  
  
Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**client**](client.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**endpoint**](endpoint-of-client.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**identità**](identity.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**DNS** >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|value|DNS del certificato. DNS è un protocollo conforme a standard di settore usato per individuare i computer di una rete basata su IP. Gli utenti possono ricordare i nomi visualizzati, ad esempio `https://go.microsoft.com/fwlink/?prd=10929` o `https://go.microsoft.com/fwlink/?LinkID=96165`, più facilmente degli indirizzi basati su numeri, ad esempio 207.46.131.137.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[identità \<>](identity.md)|Specifica l'identità del servizio da autenticare presso il client.|  
  
## <a name="example"></a>Esempio  
 Nel codice di configurazione seguente viene specificato il DNS di un certificato X.509 usato per autenticare un server.  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [identità \<>](identity.md)
