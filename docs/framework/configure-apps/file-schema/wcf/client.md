---
title: '&lt;client&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67f91f4462fc8c11b1769d5805a4ad1407385a50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientgt"></a>&lt;client&gt;
L'elemento `client` definisce un elenco di endpoint ai quali può connettersi un client.  
  
 \<System. ServiceModel >  
\<client >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Contiene una raccolta di elementi dell'endpoint che specifica a quali endpoint può connettersi questo client.|  
|[\<metadati >](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|Contiene impostazioni per l'elaborazione di metadati.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Note  
 La sezione `client` definisce un elenco di endpoint ai quali può connettersi un client. Ogni endpoint elencato nella sezione client definisce la propria associazione, comportamento e contratto. È identificato in modo univoco dalla combinazione degli attributi `name` e `contract`. Il codice client specifica il `name` al quale connettere un endpoint per il servizio implementato dal client. Se l'attributo `name` è omesso, l'endpoint si comporta come endpoint predefinito per il contratto che implementa.  
  
 In aggiunta, questa sezione specifica anche impostazioni per l'elaborazione di metadati.  
  
## <a name="example"></a>Esempio  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [Configurazione di Client WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [Client](../../../../../docs/framework/wcf/feature-details/clients.md)
