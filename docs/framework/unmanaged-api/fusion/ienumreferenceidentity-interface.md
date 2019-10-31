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
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131739"
---
# <a name="ienumreferenceidentity-interface"></a>Interfaccia IEnumReferenceIdentity
Funge da enumeratore per una raccolta di oggetti `IReferenceIdentity`.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia per un nuovo `IEnumReferenceIdentity` contenente gli stessi membri di questo `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Ottiene il numero specificato di oggetti `IReferenceIdentity`, a partire dalla posizione corrente.|  
|`IEnumReferenceIdentity::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IReferenceIdentity](ireferenceidentity-interface.md)
