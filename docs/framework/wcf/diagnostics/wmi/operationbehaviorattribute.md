---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963046"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe OperationBehaviorAttribute non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe OperationBehaviorAttribute dispone delle proprietà seguenti:  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Stato della funzionalità di eliminazione automatica per i parametri.  
  
### <a name="impersonation"></a>Rappresentazione  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Indica il livello di rappresentazione del chiamante supportato dall'operazione.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Indica quando riciclare l'oggetto nel corso della chiamata a un'operazione.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Indica se eseguire automaticamente il commit della transazione corrente se non si verifica alcuna eccezione non gestita.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Indica se l'operazione richiede una transazione.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.OperationBehaviorAttribute>
