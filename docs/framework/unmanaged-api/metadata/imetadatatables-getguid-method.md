---
title: Metodo IMetaDataTables::GetGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97f1bbd8ff04ccfbfe93fd5b75fc89fc28f393d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449108"
---
# <a name="imetadatatablesgetguid-method"></a>Metodo IMetaDataTables::GetGuid
Ottiene un GUID della riga in corrispondenza dell'indice specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ixGuid`  
 [in] Indice della riga da cui ottenere il GUID.  
  
 `ppGuid`  
 [out] Un puntatore a un puntatore al GUID.  
  
## <a name="remarks"></a>Note  
 Non è consigliabile l'utilizzo di questo metodo, perché non restituisce risultati coerenti. Per informazioni sulla tabella dei GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "partizione II: metadati definizione e la semantica". La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
