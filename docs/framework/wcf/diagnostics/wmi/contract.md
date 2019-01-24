---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: c602ea2b708fced37c5b309596fe2312be21e741
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603560"
---
# <a name="contract"></a>Contratto
Contratto  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe Contract non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe Contract ha le proprietà seguenti:  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 ID del dominio applicazione che ospita il contratto.  
  
### <a name="behaviors"></a>comportamenti  
 Tipo di dati: Matrice di Behavior  
  
 Tipo di accesso: Sola lettura  
  
 Comportamenti associati al contratto.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome del contratto in WSDL.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Spazio dei nomi dell'elemento `portType` in WSDL.  
  
### <a name="operations"></a>Operazioni  
 Tipo di dati: Matrice di Operation  
  
 Tipo di accesso: Sola lettura  
  
 Operazioni di questo contratto.  
  
### <a name="processid"></a>ProcessId  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 ID del processo che ospita il contratto.  
  
### <a name="ref"></a>ref  
 Tipo di dati: Contratto  
  
 Tipo di accesso: Sola lettura  
  
 Tipo di callback se il contratto è duplex.  
  
### <a name="sessionmode"></a>SessionMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.  
  
### <a name="type"></a>Tipo  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Tipo del contratto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Description.ContractDescription>
