---
title: Attributi ServiceModel e riferimento a ServiceDescription
ms.date: 03/30/2017
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
ms.openlocfilehash: 5e39a63d399edccc580b27ad4bfbc9ab05015ef9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600348"
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Attributi ServiceModel e riferimento a ServiceDescription
L' *albero di descrizione* è la gerarchia dei tipi (a partire dalla <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> classe) che insieme descrivono ogni aspetto di un servizio. Windows Communication Foundation (WCF) utilizza un albero di descrizione per compilare un runtime del servizio valido, per pubblicare Web Services Description Language (WSDL), il linguaggio XSD (XML Schema Definition) e le asserzioni di criteri (metadati) relativi al servizio che i client possono utilizzare per connettersi al servizio e utilizzarlo, nonché per generare varie rappresentazioni di file di codice e di configurazione dei valori della struttura di descrizione.  
  
 In questo argomento viene illustrato come le proprietà relative al contratto vengono ottenute dal contratto di servizio e come vengono implementate e aggiunte all'albero di descrizione. In alcuni casi, i valori degli attributi vengono convertiti in proprietà di comportamento e il comportamento viene quindi inserito nell'albero di descrizione. Per ulteriori informazioni su come i valori della struttura di descrizione vengono convertiti in metadati, vedere [ServiceDescription e riferimenti WSDL](servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Operazioni di mapping all'albero di descrizione  
 Nelle applicazioni WCF i contratti di servizio vengono modellati da interfacce (o classi) che usano attributi per contrassegnare l'interfaccia o la classe e i relativi metodi come raggruppamento di operazioni. Quando una classe <xref:System.ServiceModel.ServiceHost> viene aperta, eventuali implementazioni e contratti di servizio vengono analizzati e vengono uniti alle informazioni di configurazione in una struttura di descrizione.  
  
 Esistono due tipi di modelli di operazione: il modello di *parametro* e il modello di *contratto del messaggio* . Il modello parametro utilizza metodi gestiti che non dispongono di un parametro o di un tipo di valore restituito contrassegnato dalla classe <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. In questo modello gli sviluppatori controllano la serializzazione di parametri e valori restituiti, mentre WCF genera i valori usati per popolare l'albero di descrizione per il servizio e il relativo contratto.  
  
 Le associazioni specificate nei file di configurazione vengono caricate direttamente nella proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType>.  
  
|Proprietà ServiceBehaviorAttribute|Valore della struttura di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|Nome|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Imposta la proprietà <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> per tutte le operazioni.|  
|MaxItemsInObjectGraph|Imposta la proprietà <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> per tutte le operazioni.|  
  
|Proprietà ServiceContractAttribute|Valore della struttura di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> aggiunti a tutte le operazioni <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> ed eventuali livelli di protezione figlio. Per ulteriori informazioni sulla gerarchia a livello di protezione, vedere [informazioni sul livello di protezione](../understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Valore ServiceKnownTypesAttribute|Valore della struttura di descrizione interessato|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Valore OperationContractAttribute|Valore della struttura di descrizione interessato|  
|--------------------------------------|-------------------------------------|  
|Azione|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> per il messaggio di output o di input, a seconda del contratto o del contratto callback.|  
|AsyncPattern|Se true, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> e <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Esegue il mapping a un solo <xref:System.ServiceModel.Description.MessageDescription> in <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|Nome|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> ed eventuali livelli di protezione figlio. Per ulteriori informazioni sulla gerarchia a livello di protezione, vedere [informazioni sul livello di protezione](../understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> per il messaggio di output o di input, a seconda del contratto o del contratto callback.|  
  
|Valore FaultContractAttribute|Valore della struttura di descrizione interessato|  
|----------------------------------|-------------------------------------|  
|Azione|<xref:System.ServiceModel.Description.FaultDescription.Action%2A> a seconda del contratto o del contratto callback.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|Nome|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Valore DataContractFormatAttribute|Valore della struttura di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|Uso|Il valore <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> è impostato su <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> per l'operazione.|  
  
|Valore XmlSerializerFormatAttribute|Valore della struttura di descrizione interessato|  
|----------------------------------------|-------------------------------------|  
|Stile|Questa proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute> è impostata su <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> per l'operazione.|  
|Uso|<xref:System.ServiceModel.XmlSerializerFormatAttribute> è impostato su <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> per l'operazione.|  
  
|Valore TransactionFlowAttribute|Valore della struttura di descrizione interessato|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> viene aggiunto come comportamento dell'operazione alla proprietà <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Valore MessageContractAttribute|Valore della struttura di descrizione interessato|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Valore MessageHeaderAttribute|Valore della struttura di descrizione interessato|  
|----------------------------------|-------------------------------------|  
|Attore|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>per l'intestazione corrispondente in<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>per l'intestazione corrispondente in<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>per l'intestazione corrispondente in<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>per l'intestazione corrispondente in<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>per l'intestazione corrispondente in<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>per l'intestazione corrispondente in<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Valore MessageBodyMemberAttribute|Valore della struttura di descrizione interessato|  
|--------------------------------------|-------------------------------------|  
|Nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>per la parte corrispondente in<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>per la parte corrispondente in<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|JSON|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A>per la parte corrispondente in<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>per la parte corrispondente in<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Valore MessageHeaderArrayAttribute|Valore della struttura di descrizione interessato|  
|---------------------------------------|-------------------------------------|  
|Attore|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|Nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Spazio dei nomi|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Valore MessagePropertyAttribute|Valore della struttura di descrizione interessato|  
|------------------------------------|-------------------------------------|  
|Nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Valore MessageParameterAttribute|Valore della struttura di descrizione interessato|  
|-------------------------------------|-------------------------------------|  
|Nome|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>per la parte corrispondente in<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 Per ulteriori informazioni su come i valori della struttura di descrizione vengono convertiti in metadati, vedere [ServiceDescription e riferimenti WSDL](servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>Vedere anche

- [ServiceDescription e riferimento a WSDL](servicedescription-and-wsdl-reference.md)
