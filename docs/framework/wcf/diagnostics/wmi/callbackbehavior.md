---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5387e197cdf26a393ba23fd5696eb095dfd17a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="callbackbehavior"></a>CallbackBehavior
CallbackBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Se True, la sessione viene chiusa automaticamente quando un servizio chiude una sessione duplex.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Tipo di dati: stringa  
Tipo di accesso: sola lettura  
  
 Specifica se il servizio supporta un solo thread, più thread o chiamate rientranti.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore che specifica se inviare dati di serializzazione sconosciuti in transito.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Se attivato, i dettagli sulle eccezioni nel callback vengono collegati agli errori restituiti al servizio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di elementi consentiti in un oggetto serializzato.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se utilizzare il contesto di sincronizzazione corrente per scegliere il thread di esecuzione.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se il sistema o l'applicazione impone l'elaborazione delle intestazioni MustUnderstand SOAP.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
