---
title: Metodo IMetaDataTables::GetNextBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 151fdf06f6203eabf2fc3e37bd30399b52394124
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextblob-method"></a>Metodo IMetaDataTables::GetNextBlob
Ottiene l'indice del successivo oggetto binario di grandi dimensioni (BLOB) nella tabella.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ixBlob`  
 [in] L'indice, come restituito da una colonna di BLOB.  
  
 `pNext`  
 [out] Un puntatore all'indice del successivo BLOB.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataTables (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
