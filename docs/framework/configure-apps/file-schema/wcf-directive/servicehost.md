---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3c7da8d5a473b801da8c48d1cb1504b95cc6c769
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342124"
---
# <a name="servicehost"></a>\@ServiceHost
Associa la factory usata per creare l'host del servizio al servizio da ospitare e agli altri aspetti di programmazione necessari per accedere al codice host fornito nel file .svc o per compilarlo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```  
  
## <a name="attributes"></a>Attributi  
  
#### <a name="service"></a>Servizio  
 Nome del tipo CLR del servizio ospitato. Deve essere un nome completo di un tipo che implementa uno o più dei contatti del servizio.  
  
#### <a name="factory"></a>Factory  
 Nome del tipo CLR della factory dell'host del servizio usato per creare un'istanza dell'host del servizio. L'attributo è facoltativo. Se non viene specificato, viene usata la factory <xref:System.ServiceModel.Activation.ServiceHostFactory> predefinita, che restituisce un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.  
  
#### <a name="debug"></a>Debug  
 Indica se il servizio Windows Communication Foundation (WCF) deve essere compilato con simboli di debug. `true` se il servizio WCF deve essere compilato con i simboli di debug; in caso contrario, `false`.  
  
#### <a name="language"></a>Lingua:  
 Specifica il linguaggio usato per la compilazione di tutto il codice inline contenuto nel file con estensione svc. I valori possono rappresentare qualsiasi. Lingua supportata da NET, tra cui `C#`, `VB`e `JS`, che fanno riferimento C#rispettivamente a, Visual Basic e JScript .NET. L'attributo è facoltativo.  
  
#### <a name="codebehind"></a>CodeBehind  
 Specifica il file di origine per l'implementazione del servizio Web XML, quando la classe di implementazione non si trova nello stesso file e non è stata compilata in un assembly e inserita nella directory \Bin.  
  
## <a name="remarks"></a>Note  
 Il <xref:System.ServiceModel.ServiceHost> utilizzato per ospitare il servizio è un punto di estendibilità all'interno del modello di programmazione Windows Communication Foundation (WCF). Poiché un modello di factory può essere un tipo polimorfico di cui l'ambiente host non deve creare un'istanza direttamente, tale modello viene usato per creare un'istanza dell'host <xref:System.ServiceModel.ServiceHost>.  
  
 L'implementazione predefinita usa la factory <xref:System.ServiceModel.Activation.ServiceHostFactory> per creare un'istanza dell'host <xref:System.ServiceModel.ServiceHost>. È tuttavia possibile specificare una factory personalizzata, ovvero una che restituisce l'host derivato, specificando il nome del tipo CLR dell'implementazione Factory nella direttiva [\@ServiceHost](servicehost.md) .  
  
 Per usare la factory host del servizio personalizzata anziché la factory predefinita, è sufficiente specificare il nome del tipo nella direttiva [@ServiceHost](servicehost.md) come indicato di seguito:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 È consigliabile garantire che le implementazioni presentino la massima semplicità possibile. Se si usa un'elevata quantità di logica personalizzata, quest'ultima è più riutilizzabile se inserita nell'host anziché nella factory.  
  
 Ad esempio, per abilitare un endpoint abilitato per AJAX per `MyService`, specificare il <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> per il valore dell'attributo `Factory`, anziché il <xref:System.ServiceModel.Activation.ServiceHostFactory>predefinito, nella direttiva [@ServiceHost](servicehost.md) come illustrato nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
  
```xml  
<% @ServiceHost
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Host di servizi personalizzati](../../../wcf/samples/custom-service-host.md)
