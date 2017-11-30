---
title: Metodo IInstallReferenceEnum::GetNextInstallReferenceItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum.GetNextInstallReferenceItem
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db7e8bfaf396293f89f4b2e2bb20b5f6f532db19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a>Metodo IInstallReferenceEnum::GetNextInstallReferenceItem
Ottiene un puntatore al successivo [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) contenuto nell'oggetto [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppRefItem`  
 [out] L'oggetto restituito `IInstallReferenceItem` puntatore.  
  
 `dwFlags`  
 [in] Riservato per l'estensibilità futura. `dwFlags`deve essere 0 (zero).  
  
 `pvReserved`  
 [in] Riservato per l'estensibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IInstallReferenceItem (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [IInstallReferenceEnum (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
