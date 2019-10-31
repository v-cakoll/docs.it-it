---
title: Interfaccia IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107833"
---
# <a name="ienumidentity_attribute-interface"></a>Interfaccia IEnumIDENTITY_ATTRIBUTE
Funge da enumeratore per gli attributi dell'oggetto di codice nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Ottiene un puntatore a interfaccia per un nuovo `IEnumIDENTITY_ATTRIBUTE` contenente gli stessi membri di questo `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Scrive i dati contenuti negli elementi di questa `IEnumIDENTITY_ATTRIBUTE` nel buffer dei dati specificato.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Ottiene il numero specificato di attributi, a partire dalla posizione corrente.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
