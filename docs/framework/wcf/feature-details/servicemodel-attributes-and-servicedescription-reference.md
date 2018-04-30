---
title: Attributi ServiceModel e riferimento a ServiceDescription
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba8888c2a1bd3c16ab6d216c365870c0df0e499a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Attributi ServiceModel e riferimento a ServiceDescription
Il *albero di descrizione* è la gerarchia dei tipi (a partire dal <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> classe) che descrivono ogni aspetto di un servizio. In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene utilizzato un albero di descrizione per compilare un runtime di servizio valido, per pubblicare asserzioni (metadati) Web Services Description Language (WSDL), XML Schema Definition Language (XSD) e di criteri sul servizio che i client possono utilizzare per connettersi al servizio e utilizzarlo, nonché per generare varie rappresentazioni di codice e di file di configurazione dei valori dell'albero di descrizione.  
  
 In questo argomento viene illustrato come le proprietà relative al contratto vengono ottenute dal contratto di servizio e come vengono implementate e aggiunte alla struttura di descrizione. In alcuni casi, i valori degli attributi vengono convertiti in proprietà di comportamento e il comportamento viene quindi inserito nell'albero di descrizione. Per ulteriori informazioni sul modo in cui vengono convertiti i valori di struttura ad albero di descrizione in metadati, vedere [ServiceDescription e riferimento a WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Operazioni di mapping all'albero di descrizione  
 Nelle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], i contratti di servizio vengono modellati da interfacce (o classi) che utilizzano attributi per contrassegnare l'interfaccia o la classe e i relativi metodi come raggruppamento di operazioni. Quando una classe <xref:System.ServiceModel.ServiceHost> viene aperta, eventuali implementazioni e contratti di servizio vengono analizzati e vengono uniti alle informazioni di configurazione in una struttura di descrizione.  
  
 Esistono due tipi di modelli dell'operazione: il *parametro* modello e *contratto di messaggio* modello. Il modello parametro utilizza metodi gestiti che non dispongono di un parametro o di un tipo di valore restituito contrassegnato dalla classe <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. In questo modello gli sviluppatori controllano la serializzazione di parametri e di valori restituiti ma [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera i valori utilizzati per popolare la struttura di descrizione per il servizio e il relativo contratto.  
  
 Le associazioni specificate nei file di configurazione vengono caricate direttamente nella proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType>.  
  
|Proprietà ServiceBehaviorAttribute|Valore dell'albero di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|nome|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Imposta la proprietà <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> per tutte le operazioni.|  
|MaxItemsInObjectGraph|Imposta la proprietà <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> per tutte le operazioni.|  
  
|Proprietà ServiceContractAttribute|Valore dell'albero di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> aggiunti a tutte le operazioni <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> ed eventuali livelli di protezione figlio. Per ulteriori informazioni sulla gerarchia del livello di protezione, vedere [Understanding Protection Level](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Valore ServiceKnownTypesAttribute|Valore della struttura di descrizione interessato|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Valore OperationContractAttribute|Valore dell'albero di descrizione interessato|  
|--------------------------------------|-------------------------------------|  
|Operazione|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> per il messaggio di output o di input, a seconda del contratto o del contratto callback.|  
|AsyncPattern|Se true, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> e <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Esegue il mapping a un solo <xref:System.ServiceModel.Description.MessageDescription> in <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|nome|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> ed eventuali livelli di protezione figlio. Per ulteriori informazioni sulla gerarchia del livello di protezione, vedere [Understanding Protection Level](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> per il messaggio di output o di input, a seconda del contratto o del contratto callback.|  
  
|Valore FaultContractAttribute|Valore dell'albero di descrizione interessato|  
|----------------------------------|-------------------------------------|  
|Operazione|<xref:System.ServiceModel.Description.FaultDescription.Action%2A> a seconda del contratto o del contratto callback.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|nome|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Valore DataContractFormatAttribute|Valore dell'albero di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|Usa|Il valore <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> è impostato su <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> per l'operazione.|  
  
|Valore XmlSerializerFormatAttribute|Valore dell'albero di descrizione interessato|  
|----------------------------------------|-------------------------------------|  
|Stile|Questa proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute> è impostata su <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> per l'operazione.|  
|Usa|<xref:System.ServiceModel.XmlSerializerFormatAttribute> è impostato su <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> per l'operazione.|  
  
|Valore TransactionFlowAttribute|Valore dell'albero di descrizione interessato|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> viene aggiunto come comportamento dell'operazione alla proprietà <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Valore MessageContractAttribute|Valore dell'albero di descrizione interessato|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Valore MessageHeaderAttribute|Valore dell'albero di descrizione interessato|  
|----------------------------------|-------------------------------------|  
|Attore|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> per l'intestazione corrispondente in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> per l'intestazione corrispondente in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> per l'intestazione corrispondente in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> per l'intestazione corrispondente in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> per l'intestazione corrispondente in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> per l'intestazione corrispondente in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Valore MessageBodyMemberAttribute|Valore dell'albero di descrizione interessato|  
|--------------------------------------|-------------------------------------|  
|nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> per la parte corrispondente in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> per la parte corrispondente in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Ordinamento|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> per la parte corrispondente in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> per la parte corrispondente in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Valore MessageHeaderArrayAttribute|Valore dell'albero di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|Attore|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Valore MessagePropertyAttribute|Valore dell'albero di descrizione interessato|  
|------------------------------------|-------------------------------------|  
|nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Valore MessageParameterAttribute|Valore dell'albero di descrizione interessato|  
|-------------------------------------|-------------------------------------|  
|nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> per la parte corrispondente in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 Per ulteriori informazioni sul modo in cui vengono convertiti i valori di struttura ad albero di descrizione in metadati, vedere [ServiceDescription e riferimento a WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di riferimento su ServiceDescription e WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)
