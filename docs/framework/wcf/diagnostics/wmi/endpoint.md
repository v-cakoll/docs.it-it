---
title: Endpoint
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795903"
---
# <a name="endpoint"></a>Endpoint
Endpoint  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe Endpoint definisce il metodo seguente.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](getoperationcounterinstancename.md)|Recupera il nome dell'istanza del contatore delle prestazioni dell'operazione.|  
  
## <a name="properties"></a>Properties  
 La classe Endpoint ha le proprietà seguenti:  
  
### <a name="address"></a>Indirizzo  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 URI che contiene l'indirizzo dell'endpoint.  
  
### <a name="addressheaders"></a>AddressHeaders  
 Tipo di dati: matrice di stringhe  
  
 Tipo di accesso: Sola lettura  
  
 Raccolta di intestazioni di indirizzo associato a questo endpoint.  
  
### <a name="addressidentity"></a>AddressIdentity  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Identità dell'endpoint.  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 ID del dominio applicazione che ospita l'endpoint.  
  
### <a name="behaviors"></a>comportamenti  
 Tipo di dati: Matrice di comportamenti  
  
 Tipo di accesso: Sola lettura  
  
 Raccolta dei comportamenti implementati da questo endpoint.  
  
### <a name="binding"></a>Associazione  
 Tipo di dati: Associazione  
  
 Tipo di accesso: Sola lettura  
  
 Associazione usata da questo endpoint.  
  
### <a name="contractname"></a>ContractName  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Stringa che specifica il contratto che viene esposto da questo endpoint.  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome dell'istanza del contatore delle prestazioni dell'endpoint.  
  
### <a name="listenuri"></a>ListenUri  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 URI sul quale resta in attesa l'endpoint.  
  
### <a name="name"></a>Name  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome univoco di questo endpoint.  
  
### <a name="processid"></a>ProcessId  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 ID del processo che ospita l'endpoint.  
  
### <a name="ref"></a>ref  
 Tipo di dati: Contratto  
  
 Tipo di accesso: Sola lettura  
  
 Contratto esposto dall'endpoint.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|
