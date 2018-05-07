---
title: ServiceDescription e riferimento a WSDL
ms.date: 03/30/2017
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
ms.openlocfilehash: e70d653519c13d2f40fa2a579b674893e1b7ab02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="servicedescription-and-wsdl-reference"></a>ServiceDescription e riferimento a WSDL
Questo argomento viene descritto come Windows Communication Foundation (WCF) esegue il mapping di documenti Web Services Description Language (WSDL) da e verso <xref:System.ServiceModel.Description.ServiceDescription> istanze.  
  
## <a name="how-servicedescription-maps-to-wsdl-11"></a>Mapping di ServiceDescription a WSDL 1.1  
 È possibile usare WCF per esportare documenti WSDL da un <xref:System.ServiceModel.Description.ServiceDescription> istanza per il servizio. I documenti WSDL vengono generati automaticamente per il servizio quando si pubblicano endpoint di metadati.  
  
 È inoltre possibile importare istanze <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> e <xref:System.ServiceModel.Channels.Binding> da documenti WSDL usando il tipo `WsdlImporter`.  
  
 I documenti WSDL, esportati da WCF, importano qualsiasi definizione di XML Schema utilizzati da documenti XSD esterni. Per ogni spazio dei nomi di destinazione che i tipi di dati usano nel servizio viene esportato un documento XSD separato. Analogamente, per ogni spazio dei nomi di destinazione usato dai contratti di servizio viene esportato un documento WSDL separato.  
  
### <a name="servicedescription"></a>ServiceDescription  
 Un'istanza <xref:System.ServiceModel.Description.ServiceDescription> esegue il mapping a un elemento `wsdl:service`. Un'istanza <xref:System.ServiceModel.Description.ServiceDescription> contiene una raccolta di istanze <xref:System.ServiceModel.Description.ServiceEndpoint>, ognuna delle quali esegue il mapping a singoli elementi `wsdl:port`.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Il `wsdl:service` /@name valore per il servizio.|  
|`Namespace`|Valore targetNamespace per la definizione `wsdl:service` del servizio.|  
|`Endpoints`|Definizioni di `wsdl:port` per il servizio.|  
  
### <a name="serviceendpoint"></a>ServiceEndpoint  
 Un'istanza <xref:System.ServiceModel.Description.ServiceEndpoint> esegue il mapping a un elemento `wsdl:port`. Un'istanza <xref:System.ServiceModel.Description.ServiceEndpoint> contiene un indirizzo, un'associazione e un contratto.  
  
 I comportamenti dell'endpoint che implementano l'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> possono modificare l'elemento `wsdl:port` per l'endpoint al quale sono associati.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Il `wsdl:port` /@name valore per l'endpoint e `wsdl:binding` /@name valore per l'associazione dell'endpoint.|  
|`Address`|Indirizzo per la definizione di `wsdl:port` per l'endpoint.<br /><br /> Il trasporto per l'endpoint determina il formato dell'indirizzo. Ad esempio, per i trasporti supportati WCF è possibile un indirizzo SOAP o un riferimento dell'endpoint.|  
|`Binding`|Definizione di `wsdl:binding` per l'endpoint.<br /><br /> A differenza di `wsdl:binding` definizioni, le associazioni in WCF non vengono associate ad alcun contratto.|  
|`Contract`|Definizione di `wsdl:portType` per l'endpoint.|  
|`Behaviors`|I comportamenti dell'endpoint che implementano l'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> possono modificare l'elemento `wsdl:port` per l'endpoint.|  
  
### <a name="bindings"></a>Associazioni  
 L'istanza di associazione per un'istanza `ServiceEndpoint` esegue il mapping a una definizione di `wsdl:binding`. A differenza `wsdl:binding` definizioni, che devono essere associate a uno specifico `wsdl:portType` definizione, le associazioni WCF sono indipendenti da qualsiasi contratto.  
  
 Un'associazione è costituita da una raccolta di elementi di associazione. Ogni elemento descrive alcuni aspetti relativi alla modalità di comunicazione tra l'endpoint e i client. Un'associazione comprende inoltre una classe <xref:System.ServiceModel.Channels.MessageVersion> che indica le classi <xref:System.ServiceModel.EnvelopeVersion> e <xref:System.ServiceModel.Channels.AddressingVersion> per l'endpoint.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Utilizzato nel nome predefinito di un endpoint, ovvero il nome dell'associazione seguito dal nome del contratto separati da un carattere di sottolineatura.|  
|`Namespace`|`targetNamespace` per la definizione di `wsdl:binding`.<br /><br /> Se alla porta WSDL è associato un criterio, al momento dell'importazione viene eseguito il mapping dello spazio dei nomi di associazione importato a `targetNamespace` per la definizione di `wsdl:port`.|  
|Elemento `BindingElementCollection` restituito dal metodo `CreateBindingElements`().|Varie estensioni specifiche del dominio alla definizione di `wsdl:binding`, in genere asserzioni di criteri.|  
|`MessageVersion`|`EnvelopeVersion` e `AddressingVersion` per l'endpoint.<br /><br /> Quando viene specificato `MessageVersion.None`, l'associazione WSDL non contiene un'associazione SOAP e la porta WSDL non include il contenuto WS-Addressing. Questa impostazione viene in genere usata per endpoint XML (POX) obsoleti.|  
  
#### <a name="bindingelements"></a>BindingElements  
 Gli elementi di associazione per un endpoint eseguono il mapping a varie estensioni WSDL nell'elemento `wsdl:binding`, ad esempio asserzioni di criteri.  
  
 La classe <xref:System.ServiceModel.Channels.TransportBindingElement> per l'associazione determina l'URI (Uniform Resource Identifier) per un'associazione SOAP.  
  
#### <a name="addressingversion"></a>AddressingVersion  
 L'oggetto `AddressingVersion` in un'associazione esegue il mapping alla versione di indirizzamento usata in `wsd:port`. WCF supporta SOAP 1.1 e SOAP 1.2 indirizzi e WS-Addressing 08/2004 e i riferimenti all'endpoint WS-Addressing 1.0.  
  
#### <a name="envelopeversion"></a>EnvelopeVersion  
 L'oggetto `EnvelopeVersion` in un'associazione esegue il mapping alla versione di SOAP usata in `wsdl:binding`. WCF supporta associazioni SOAP 1.1 e SOAP 1.2.  
  
### <a name="contracts"></a>Contratti  
 L'istanza <xref:System.ServiceModel.Description.ContractDescription> di un'istanza `ServiceEndpoint` esegue il mapping a `wsdl:portType`. Un'istanza `ContractDescription` descrive tutte le operazioni per un determinato contratto.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Il `wsdl:portType` /@name valore per il contratto.|  
|`Namespace`|Valore targetNamespace per la definizione di `wsdl:portType`.|  
|`SessionMode`|Il `wsdl:portType` /@msc:usingSession valore per il contratto. Questo attributo è un'estensione WCF per WSDL 1.1.|  
|`Operations`|Definizioni di `wsdl:operation` per il contratto.|  
  
### <a name="operations"></a>Operazioni  
 Un <xref:System.ServiceModel.Description.OperationDescription> istanza esegue il mapping a un `wsdl:portType` / `wsdl:operation`. Un elemento `OperationDescription` contiene una raccolta di istanze `MessageDescription` che descrivono i messaggi per l'operazione.  
  
 La modalità di esecuzione del mapping di `OperationDescription` a un documento WSDL è fortemente influenzata dai comportamenti di due operazioni: `DataContractSerializerOperationBehavior` e `XmlSerializerOperationBehavior`.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Il `wsdl:portType` / `wsdl:operation` /@name valore per l'operazione.|  
|`ProtectionLevel`|Asserzioni di protezione in un criterio di sicurezza associato ai messaggi `wsdl:binding/wsdl:operation` per questa operazione.|  
|`IsInitiating`|Il `wsdl:portType` / `wsdl:operation` /@msc:isInitiating valore per l'operazione. Questo attributo è un'estensione WCF per WSDL 1.1.|  
|`IsTerminating`|Il `wsdl:portType` / `wsdl:operation` /@msc:isTerminating valore per l'operazione. Questo attributo è un'estensione WCF per WSDL 1.1.|  
|`Messages`|Il `wsdl:portType` / `wsdl:operation` / `wsdl:input` e `wsdl:portType` / `wsdl:operation` / `wsdl:output` messaggi per l'operazione.|  
|`Faults`|Il `wsdl:portType` / `wsdl:operation` / `wsdl:fault` le definizioni per l'operazione.|  
|`Behaviors`|`DataContractSerializerOperationBehavior` e `XmlSerializerOperationBehavior` si riferiscono all'associazione e ai messaggi dell'operazione.|  
  
#### <a name="the-datacontractserializeroperationbehavior"></a>DataContractSerializerOperationBehavior  
 L'elemento `DataContractSerializerOperationBehavior` per un'operazione è un'implementazione dell'interfaccia `IWsdlExportExtension` che esporta i messaggi e l'associazione WSDL per tale operazione. I tipi XML Schema vengono esportati usando `XsdDataContractExporter`. L'elemento `DataContractSerializerOperationBehavior` determina inoltre l'uso, lo stile e l'utilità di esportazione e importazione dello schema da usare per l'operazione.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`DataContractFormatAttribute`|Il `Style` esegue il mapping di proprietà per questo attributo per il `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style valore per l'operazione.<br /><br /> `DataContractSerializerOperationBehavior` supporta soltanto l'uso letterale dei tipi di schema in WSDL.|  
  
#### <a name="the-xmlserializeroperationbehavior"></a>XmlSerializerOperationBehavior  
 L'elemento `XmlSerializerOperationBehavior` per un'operazione è un'implementazione dell'interfaccia `IWsdlExportExtension` che esporta i messaggi e l'associazione WSDL per tale operazione. I tipi XML Schema vengono esportati usando `XmlSchemaExporter`. L'elemento `XmlSerializerOperationBehavior` determina inoltre l'uso, lo stile e l'utilità di esportazione e importazione dello schema da usare per l'operazione.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`XmlSerializerFormatAttribute`|Il `Style` esegue il mapping di proprietà per questo attributo per il `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style valore per l'operazione.<br /><br /> Il `Use` esegue il mapping di proprietà per questo attributo per il `wsdl:binding` / `wsdl:operation` / `soap:operation`/ */@use i valori per tutti i messaggi nell'operazione.|  
  
### <a name="messages"></a>Messages  
 Oggetto `MessageDescription` istanza esegue il mapping a un `wsdl:message` a cui fa riferimento un `wsdl:portType` / `wsdl:operation` / `wsdl:input` o `wsdl:portType` / `wsdl:operation` / `wsdl:output`messaggio in un'operazione. Un elemento `MessageDescription` è costituito da un corpo e da intestazioni.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Action`|Azione SOAP o WS-Addressing per il messaggio.<br /><br /> Le operazioni che usano la stringa di azione "*" non sono rappresentate in WSDL.|  
|`Direction`|`MessageDirection.Input` esegue il mapping a `wsdl:input`.<br /><br /> `MessageDirection.Output` esegue il mapping a `wsdl:output`.|  
|`ProtectionLevel`|Asserzioni di protezione in un criterio di sicurezza associato alla definizione di `wsdl:message` per questo messaggio.|  
|`Body`|Corpo del messaggio.|  
|`Headers`|Intestazioni del messaggio.|  
|`ContractDescription.Name`, `OperationContract.Name`|Durante l'esportazione, utilizzato per derivare il `wsdl:message` /@name valore.|  
  
#### <a name="message-body"></a>Corpo del messaggio  
 Oggetto `MessageBodyDescription` istanza esegue il mapping per il `wsdl:message` / `wsdl:part` le definizioni per il corpo di un messaggio. Il corpo del messaggio può essere wrapped o bare.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`WrapperName`|Se lo stile non è RPC, il `WrapperName` esegue il mapping al nome dell'elemento a cui fa riferimento il `wsdl:message` / `wsdl:part` con @name impostato su "parameters".|  
|`WrapperNamespace`|Se lo stile non è RPC, il `WrapperNamespace` esegue il mapping allo spazio dei nomi di elemento per il `wsdl:message` / `wsdl:part` con @name impostato su "parameters".|  
|`Parts`|Parti del messaggio per questo corpo del messaggio.|  
|`ReturnValue`|L'elemento figlio dell'elemento wrapper se un elemento wrapper esiste (stile incapsulato da documenti o stile RPC), il primo `wsdl:message` / `wsdl:part` nel messaggio.|  
  
#### <a name="message-parts"></a>Parti del messaggio  
 Oggetto `MessagePartDescription` istanza esegue il mapping a un `wsdl:message` / `wsdl:part` e il tipo di XML schema o l'elemento che fa riferimento la parte di messaggio.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Il `wsd:message` / `wsdl:part` /@name valore per la parte del messaggio e il nome dell'elemento che fa riferimento la parte di messaggio.|  
|`Namespace`|Spazio dei nomi dell'elemento al quale fa riferimento la parte del messaggio.|  
|`Index`|L'indice del `wsdl:message` / `wsdl:part` per il messaggio.|  
|`ProtectionLevel`|Asserzioni di protezione in un criterio di sicurezza associato alla definizione di `wsdl:message` per questa parte del messaggio. Nel criterio vengono impostati parametri per fare riferimento alla parte del messaggio specifica.|  
|`MessageType`|Tipo di XML Schema dell'elemento al quale fa riferimento la parte del messaggio.|  
  
#### <a name="message-headers"></a>Intestazioni del messaggio  
 Un'istanza `MessageHeaderDescription` è una parte del messaggio che esegue il mapping a un'associazione `soap:header` per la parte del messaggio.  
  
### <a name="faults"></a>Errori  
 Oggetto `FaultDescription` istanza esegue il mapping a un `wsdl:portType` / `wsdl:operation` / `wsdl:fault` definizione e l'identificatore associato `wsdl:message` definizione. L'elemento `wsdl:message` viene aggiunto allo stesso spazio dei nomi di destinazione del tipo di porta WSDL associato. L'elemento `wsdl:message` ha una sola parte di messaggio denominata "detail" che fa riferimento all'elemento XML Schema che corrisponde al valore della proprietà `DefaultType` per l'istanza `FaultDescription`.  
  
|Proprietà|Mapping WSDL|  
|----------------|------------------|  
|`Name`|Il `wsdl:portType` / `wsdl:operation` / `wsdl:fault` /@name valore per il messaggio di errore.|  
|`Namespace`|Spazio dei nomi dell'elemento XML Schema al quale fa riferimento il messaggio di dettaglio dell'errore.|  
|`Action`|Azione SOAP o WS-Addressing per l'errore.|  
|`ProtectionLevel`|Asserzioni di protezione in un criterio di sicurezza associato alla definizione di `wsdl:message` per questo errore.|  
|`DetailType`|Tipo XML Schema dell'elemento al quale fa riferimento il messaggio dettagliato.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Utilizzato per derivare il `wsdl:message` /@name valore per il messaggio di errore.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description>
