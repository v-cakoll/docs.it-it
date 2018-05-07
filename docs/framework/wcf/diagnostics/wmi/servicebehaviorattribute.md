---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: 514af4c6d9eaaf8929ca831e4e786c895d14c67d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Indica se chiudere automaticamente una sessione quando un client chiude una sessione di output.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Tipo di dati: stringa  
Tipo di accesso: sola lettura  
  
 Indica se un servizio supporta un solo thread, più thread o chiamate rientranti.  
  
### <a name="configurationname"></a>ConfigurationName  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome della configurazione di servizio.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se inviare dati di serializzazione sconosciuti in transito.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.  
  
### <a name="instancecontextmode"></a>InstanceContextMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Specifica quando viene creato un nuovo oggetto servizio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di elementi consentiti in un oggetto serializzato.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Attributo nome del servizio in WSDL.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Spazio dei nomi di destinazione del servizio in WSDL.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>ReleaseServiceInstanceOnTransactionComplete  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se l'oggetto servizio viene riciclato al completamento della transazione corrente.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se alla chiusura della sessione corrente vengono completate le transazioni in sospeso.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Specifica il livello di isolamento della transazione.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Periodo entro il quale una transazione deve essere completata.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se utilizzare il contesto di sincronizzazione corrente per scegliere l'esecuzione del thread.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se il sistema o l'applicazione impone l'elaborazione delle intestazioni MustUnderstand SOAP.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>
