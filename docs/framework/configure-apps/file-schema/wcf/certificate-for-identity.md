---
title: <certificate> per <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850011"
---
# <a name="certificate-for-identity"></a>\<> del certificato \<per l'identità >
Specifica un certificato X.509 usato per convalidare un server presso un client.  
  
Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identità**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificato**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|encodedValue|Codifica Base64 del certificato.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Specifica l'identità del servizio da autenticare presso il client.|  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene specificata la rappresentazione codificata di un certificato usato per convalidare un server presso un client.  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
