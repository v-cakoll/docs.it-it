---
title: Contratto
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: e4a21e95a6f1f1860ed36c968d17bb8ac8465dce
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868440"
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
  
## <a name="properties"></a>Properties  
 La classe Contract ha le proprietà seguenti:  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 ID del dominio applicazione che ospita il contratto.  
  
### <a name="behaviors"></a>comportamenti  
 Tipo di dati: Matrice di comportamenti  
  
 Tipo di accesso: Sola lettura  
  
 Comportamenti associati al contratto.  
  
### <a name="name"></a>NOME  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome del contratto in WSDL.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Spazio dei nomi dell'elemento `portType` in WSDL.  
  
### <a name="operations"></a>Operazioni  
 Tipo di dati: Matrice Operation  
  
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
  
### <a name="type"></a>Type  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Tipo del contratto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ContractDescription>
