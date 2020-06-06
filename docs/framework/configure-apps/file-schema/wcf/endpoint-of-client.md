---
title: <endpoint> di <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855315"
---
# <a name="endpoint-of-client"></a>\<endpoint> di \<client>
Specifica proprietà di contratto, associazione e indirizzo dell'endpoint del canale usato dai client per connettersi agli endpoint del servizio nel server.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|address|Attributo stringa obbligatorio.<br /><br /> Specifica l'indirizzo dell'endpoint. Il valore predefinito è una stringa vuota. L'indirizzo deve essere un URI assoluto.|  
|behaviorConfiguration|Stringa che contiene il nome del comportamento da usare per creare un'istanza dell'endpoint. Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito. Il valore predefinito è una stringa vuota.|  
|binding|Attributo stringa obbligatorio.<br /><br /> Stringa che indica il tipo di associazione da usare. Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento. Il tipo viene registrato in base al nome di sezione invece che al nome del tipo di associazione.|  
|bindingConfiguration|Facoltativa. Stringa che contiene il nome della configurazione di associazione da usare quando viene creata un'istanza dell'endpoint. La configurazione di associazione deve essere nell'ambito del punto in cui l'endpoint viene definito. Il valore predefinito è una stringa vuota.<br /><br /> Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione. Impostare questo attributo se si sta tentando di usare un'associazione personalizzata. In caso contrario, può venire generata un'eccezione.|  
|contract|Attributo stringa obbligatorio.<br /><br /> Stringa che indica quale contratto viene esposto da questo endpoint. L'assembly deve implementare il tipo di contratto.|  
|endpointConfiguration|Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard. Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.|  
|kind|Stringa che specifica il tipo di endpoint standard applicato. Il tipo deve essere registrato nella `<extensions>` sezione o in Machine. config. Se non viene specificato alcun valore, viene creato un endpoint del canale comune.|  
|name|Attributo stringa facoltativo. L'attributo identifica in modo univoco un endpoint per un dato contratto. È possibile definire più client per un determinato tipo di contratto. Ogni definizione deve essere differenziata da un nome di configurazione univoco. Se questo attributo viene omesso, l'endpoint corrispondente viene usato come endpoint predefinito associato al tipo di contratto specificato. Il valore predefinito è una stringa vuota.<br /><br /> L'attributo `name` di un'associazione viene usato per l'esportazione della definizione tramite WSDL.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<headers>](headers.md)|Raccolte di intestazioni di indirizzo.|  
|[\<identity>](identity.md)|Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<client>](client.md)|Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.|  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di configurazione dell'endpoint di un canale.  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [Configurazione del client WCF](../../../wcf/feature-details/client-configuration.md)
- [Client](../../../wcf/feature-details/clients.md)
