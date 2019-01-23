---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: d0bf59e6064748a045f761777a2f8f3e88f1cb5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504327"
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
