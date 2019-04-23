---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973967"
---
# <a name="callbackbehavior"></a>CallbackBehavior
CallbackBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe CallbackBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe CallbackBehavior dispone delle proprietà seguenti:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Se True, la sessione viene chiusa automaticamente quando un servizio chiude una sessione duplex.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Tipo di dati: stringa  
Tipo di accesso: Sola lettura  
  
 Specifica se il servizio supporta un solo thread, più thread o chiamate rientranti.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che specifica se inviare dati di serializzazione sconosciuti in transito.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Se attivato, i dettagli sulle eccezioni nel callback vengono collegati agli errori restituiti al servizio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di elementi consentiti in un oggetto serializzato.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se utilizzare il contesto di sincronizzazione corrente per scegliere il thread di esecuzione.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se il sistema o l'applicazione impone l'elaborazione delle intestazioni MustUnderstand SOAP.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
