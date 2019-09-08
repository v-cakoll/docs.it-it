---
title: Metodo IInstallReferenceEnum::GetNextInstallReferenceItem
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20e2bff4257df64f761fd8fff880643d4e786748
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796452"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a>Metodo IInstallReferenceEnum::GetNextInstallReferenceItem
Ottiene un puntatore al successivo oggetto [IInstallReferenceItem](iinstallreferenceitem-interface.md) contenuto nell'oggetto [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppRefItem`  
 out Puntatore restituito `IInstallReferenceItem` .  
  
 `dwFlags`  
 in Riservato per l'estendibilità futura. `dwFlags`deve essere 0 (zero).  
  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IInstallReferenceItem](iinstallreferenceitem-interface.md)
- [Interfaccia IInstallReferenceEnum](iinstallreferenceenum-interface.md)
