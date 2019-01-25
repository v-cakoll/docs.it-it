---
title: Attributi ServiceModel e riferimento a ServiceDescription
ms.date: 03/30/2017
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
ms.openlocfilehash: 3b1b10f34e300d77943a93d180b5be9e4a3366c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726625"
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Attributi ServiceModel e riferimento a ServiceDescription
Il *albero di descrizione* è la gerarchia dei tipi (a partire dal <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> classe) che descrivono ogni aspetto di un servizio. Windows Communication Foundation (WCF) viene utilizzato un albero di descrizione per compilare un runtime di servizio valido, per pubblicare Web Services Description Language (WSDL), il linguaggio XML Schema definition (XSD) e asserzioni di criteri (metadati) sul servizio che i client possono usare per connettersi e usare il servizio e per generare rappresentazioni diverse di file di codice e la configurazione dei valori di struttura ad albero di descrizione.  
  
 In questo argomento viene illustrato come le proprietà relative al contratto vengono ottenute dal contratto di servizio e come vengono implementate e aggiunte all'albero di descrizione. In alcuni casi, i valori degli attributi vengono convertiti in proprietà di comportamento e il comportamento viene quindi inserito nell'albero di descrizione. Per altre informazioni sul modo in cui i valori della struttura di descrizione vengono convertiti in metadati, vedere [ServiceDescription e riferimento a WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Operazioni di mapping all'albero di descrizione  
 Nelle applicazioni di WCF, i contratti di servizio vengono modellati da interfacce (o classi) che utilizzano attributi per contrassegnare l'interfaccia o classe e i relativi metodi come raggruppamento di operazioni. Quando una classe <xref:System.ServiceModel.ServiceHost> viene aperta, eventuali implementazioni e contratti di servizio vengono analizzati e vengono uniti alle informazioni di configurazione in un albero di descrizione.  
  
 Esistono due tipi di modelli dell'operazione: i *parametri* modello e il *contratto di messaggio* modello. Il modello parametro utilizza metodi gestiti che non dispongono di un parametro o di un tipo di valore restituito contrassegnato dalla classe <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. In questo modello, gli sviluppatori di controllano la serializzazione dei parametri e valori restituiscono, ma WCF genera i valori utilizzati per popolare l'albero di descrizione per il servizio e il relativo contratto.  
  
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
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> ed eventuali livelli di protezione figlio. Per altre informazioni sulla gerarchia del livello di protezione, vedere [Understanding Protection Level](../../../../docs/framework/wcf/understanding-protection-level.md).|  
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
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> ed eventuali livelli di protezione figlio. Per altre informazioni sulla gerarchia del livello di protezione, vedere [Understanding Protection Level](../../../../docs/framework/wcf/understanding-protection-level.md).|  
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
  
 Per altre informazioni sul modo in cui i valori della struttura di descrizione vengono convertiti in metadati, vedere [ServiceDescription e riferimento a WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>Vedere anche
- [Informazioni di riferimento su ServiceDescription e WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)
