---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855014"
---
# \<service>
L'elemento `service` contiene le impostazioni di un servizio Windows Communication Foundation (WCF). Contiene anche endpoint che espongono il servizio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
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
|[\<endpoint>](endpoint-element.md)|Raccolta di elementi `endpoint` che espongono questo servizio.|  
|[\<host>](host.md)|Specifica l'host dell'istanza del servizio. L'elemento è di tipo <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<services>](services.md)|Elemento radice di tutti gli elementi di configurazione WCF.|  
  
## <a name="remarks"></a>Commenti  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [Configurazione dei servizi](../../../wcf/configuring-services.md)
