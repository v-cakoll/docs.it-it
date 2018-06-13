---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 5498c300ab126bbc4e08cd228e3e7b48e905932e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352544"
---
# <a name="servicehost"></a>@ServiceHost
Associa la factory usata per creare l'host del servizio al servizio da ospitare e agli altri aspetti di programmazione necessari per accedere al codice host fornito nel file .svc o per compilarlo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a>Attributi  
  
#### <a name="service"></a>Servizio  
 Nome del tipo CLR del servizio ospitato. Deve essere un nome completo di un tipo che implementa uno o più dei contatti del servizio.  
  
#### <a name="factory"></a>Factory  
 Nome del tipo CLR della factory dell'host del servizio usato per creare un'istanza dell'host del servizio. L'attributo è facoltativo. Se non viene specificato, viene usata la factory <xref:System.ServiceModel.Activation.ServiceHostFactory> predefinita, che restituisce un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.  
  
#### <a name="debug"></a>Debug  
 Indica se il servizio Windows Communication Foundation (WCF) deve essere compilato con simboli di debug. `true` Se il servizio WCF deve essere compilato con simboli di debug. in caso contrario, `false`.  
  
#### <a name="language"></a>Linguaggio  
 Specifica il linguaggio usato per la compilazione di tutto il codice inline contenuto nel file con estensione svc. I valori possono rappresentare qualsiasi linguaggio supportato da .NET, inclusi C#, VB e JS, che fanno riferimento, rispettivamente, a C#, Visual Basic .NET e JScript .NET. L'attributo è facoltativo.  
  
#### <a name="codebehind"></a>CodeBehind  
 Specifica il file di origine per l'implementazione del servizio Web XML, quando la classe di implementazione non si trova nello stesso file e non è stata compilata in un assembly e inserita nella directory \Bin.  
  
## <a name="remarks"></a>Note  
 Il <xref:System.ServiceModel.ServiceHost> utilizzato per ospitare il servizio è un punto di estensibilità all'interno del modello di programmazione di Windows Communication Foundation (WCF). Poiché un modello di factory può essere un tipo polimorfico di cui l'ambiente host non deve creare un'istanza direttamente, tale modello viene usato per creare un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.  
  
 L'implementazione predefinita usa la factory <xref:System.ServiceModel.Activation.ServiceHostFactory> per creare un'istanza dell'host <xref:System.ServiceModel.ServiceHost>. È però possibile fornire una propria factory (uno che restituisca l'host derivato) specificando il nome del tipo CLR dell'implementazione di factory nel [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva.  
  
 Per utilizzare è factory host del servizio personalizzato personalizzati anziché la factory predefinita, solo specificare il nome del tipo nel [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva come indicato di seguito:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 È consigliabile garantire che le implementazioni presentino la massima semplicità possibile. Se si usa un'elevata quantità di logica personalizzata, quest'ultima è più riutilizzabile se inserita nell'host anziché nella factory.  
  
 Ad esempio, per abilitare un endpoint compatibile con AJAX per `MyService`, specificare il <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> per il valore del `Factory` attributo, anziché il valore predefinito <xref:System.ServiceModel.Activation.ServiceHostFactory>nella [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva come Nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Host di servizi personalizzati](../../../../../docs/framework/wcf/samples/custom-service-host.md)
