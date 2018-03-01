---
title: Metodo IMetaDataTables::GetTableInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ce9e3beb15724c7d7ddf02cbe7f83795d474139
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgettableinfo-method"></a>Metodo IMetaDataTables::GetTableInfo
Ottiene il nome, dimensioni delle righe, numero di righe, numero di colonne e l'indice della colonna chiave della tabella specificata.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `ixTbl`  
 [in] Identificatore della tabella le cui proprietà da restituire.  
  
 `pcbRow`  
 [out] Puntatore alla dimensione, in byte, di una riga della tabella.  
  
 `pcRows`  
 [out] Puntatore al numero di righe nella tabella.  
  
 `pcCols`  
 [out] Puntatore al numero di colonne della tabella.  
  
 `piKey`  
 [out] Un puntatore all'indice della colonna chiave, oppure -1 se la tabella non ha una colonna chiave.  
  
 `ppName`  
 [out] Un puntatore a un puntatore al nome della tabella.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
