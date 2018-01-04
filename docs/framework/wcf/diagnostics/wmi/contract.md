---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04a5cb87b9ed61fd278ce0f2e05e5f1c954de5b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="contract"></a>Contratto
Contratto  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 ID del dominio applicazione che ospita il contratto.  
  
### <a name="behaviors"></a>Comportamenti  
 Tipo di dati: matrice di Behavior  
  
 Tipo di accesso: sola lettura  
  
 Comportamenti associati al contratto.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome del contratto in WSDL.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Spazio dei nomi dell'elemento `portType` in WSDL.  
  
### <a name="operations"></a>Operazioni  
 Tipo di dati: matrice di Operation  
  
 Tipo di accesso: sola lettura  
  
 Operazioni di questo contratto.  
  
### <a name="processid"></a>ProcessId  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 ID del processo che ospita il contratto.  
  
### <a name="ref"></a>ref  
 Tipo di dati: contratto  
  
 Tipo di accesso: sola lettura  
  
 Tipo di callback se il contratto è duplex.  
  
### <a name="sessionmode"></a>SessionMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.  
  
### <a name="type"></a>Tipo  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Tipo del contratto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ContractDescription>
