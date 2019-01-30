---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 57fbdd2cf7c398e611f835eeb4e924fb4f3e0c9e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270303"
---
# <a name="service"></a>\<service>
L'elemento `service` contiene le impostazioni di un servizio Windows Communication Foundation (WCF). Contiene anche endpoint che espongono il servizio.  
  
 \<system.ServiceModel>  
\<services>  
\<service>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|behaviorConfiguration|Stringa che contiene il nome del comportamento da usare per creare l'istanza del servizio. Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito. Il valore predefinito è una stringa vuota.|  
|name|Attributo stringa obbligatorio che specifica il tipo del servizio per cui creare un'istanza. Questa impostazione deve corrispondere a un tipo valido. Il formato deve essere `Namespace.Class.`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Raccolta di elementi `endpoint` che espongono questo servizio.|  
|[\<host>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Specifica l'host dell'istanza del servizio. L'elemento è di tipo <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Elemento radice di tutti gli elementi di configurazione WCF.|  
  
## <a name="remarks"></a>Note  
 I servizi vengono definiti nella sezione `services` del file di configurazione. Un assembly può contenere un numero qualsiasi di servizi. Ogni servizio dispone di una propria sezione di configurazione `service`. Questa sezione e il relativo contenuto definiscono il contratto di servizio, il comportamento e gli endpoint del particolare servizio.  
  
 L'elemento `behaviorConfiguration` è anche facoltativo. Identifica il comportamento usato dal servizio. Il comportamento specificato in questo attributo deve collegarsi a un comportamento nell'ambito nello stesso file di configurazione.  
  
 Ogni servizio espone uno o più endpoint, i quali sono provvisti di un proprio indirizzo e associazione. Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file. Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`. L'attributo `name` descrive la sezione in cui è definita l'associazione. L'attributo `bindingConfiguration` definisce quale configurazione viene usata tra quelle contenute nella sezione di associazione. In una sezione di associazione è possibile definire diverse configurazioni.  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di una configurazione di servizio.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.ServiceElement>
- [Configurazione dei servizi](../../../../../docs/framework/wcf/configuring-services.md)
