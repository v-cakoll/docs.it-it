---
title: Metodo IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876f74d7fe7555f71db0bd77e68f657dfc80b179
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478960"
---
# <a name="imetadatatablesgettableinfo-method"></a>Metodo IMetaDataTables::GetTableInfo
Ottiene il nome, dimensioni delle righe, numero di righe, il numero di colonne e indice della colonna chiave della tabella specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ixTbl`  
 [in] L'identificatore della tabella le cui proprietà da restituire.  
  
 `pcbRow`  
 [out] Un puntatore alla dimensione, espressa in byte, di una riga della tabella.  
  
 `pcRows`  
 [out] Puntatore al numero di righe della tabella.  
  
 `pcCols`  
 [out] Puntatore al numero di colonne della tabella.  
  
 `piKey`  
 [out] Un puntatore all'indice della colonna chiave, oppure -1 se la tabella non dispone di alcuna colonna chiave.  
  
 `ppName`  
 [out] Un puntatore a un puntatore al nome della tabella.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
