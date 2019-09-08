---
title: Interfaccia IEnumReferenceIdentity
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796436"
---
# <a name="ienumreferenceidentity-interface"></a>Interfaccia IEnumReferenceIdentity
Funge da enumeratore per una raccolta di `IReferenceIdentity` oggetti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` nuovo oggetto che contiene gli stessi membri `IEnumReferenceIdentity`di questo oggetto.|  
|`IEnumReferenceIdentity::Next`|Ottiene il numero specificato di `IReferenceIdentity` oggetti, a partire dalla posizione corrente.|  
|`IEnumReferenceIdentity::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumReferenceIdentity`oggetto.|  
|`IEnumReferenceIdentity::Skip`|Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IReferenceIdentity](ireferenceidentity-interface.md)
