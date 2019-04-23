---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772830"
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceBehaviorAttribute non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceBehaviorAttribute dispone delle proprietà seguenti:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Indica se chiudere automaticamente una sessione quando un client chiude una sessione di output.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Tipo di dati: stringa  
Tipo di accesso: Sola lettura  
  
 Indica se un servizio supporta un solo thread, più thread o chiamate rientranti.  
  
### <a name="configurationname"></a>ConfigurationName  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome della configurazione di servizio.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se inviare dati di serializzazione sconosciuti in transito.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.  
  
### <a name="instancecontextmode"></a>InstanceContextMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Specifica quando viene creato un nuovo oggetto servizio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di elementi consentiti in un oggetto serializzato.  
  
### <a name="name"></a>Nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Attributo nome del servizio in WSDL.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Spazio dei nomi di destinazione del servizio in WSDL.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>ReleaseServiceInstanceOnTransactionComplete  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se l'oggetto servizio viene riciclato al completamento della transazione corrente.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se alla chiusura della sessione corrente vengono completate le transazioni in sospeso.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Specifica il livello di isolamento della transazione.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Periodo entro il quale una transazione deve essere completata.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se utilizzare il contesto di sincronizzazione corrente per scegliere l'esecuzione del thread.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se il sistema o l'applicazione impone l'elaborazione delle intestazioni MustUnderstand SOAP.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
