---
title: Metodo IMetaDataTables2::GetMetaDataStorage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStorage
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b86542a55c0b4e778dfd956961f5a14a1c9d6f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables2getmetadatastorage-method"></a>Metodo IMetaDataTables2::GetMetaDataStorage
Ottiene le dimensioni e il contenuto dei metadati archiviati nella sezione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppvMd`  
 [in, out] Un puntatore a una sezione di metadati.  
  
 `pcbMd`  
 [out] Le dimensioni del flusso di metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataTables2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [IMetaDataTables (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
