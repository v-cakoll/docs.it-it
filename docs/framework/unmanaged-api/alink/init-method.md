---
title: Metodo Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b512389078ab022208c4b163edc8501a900669ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="init-method"></a>Metodo Init
Prepara oggetti che implementano il [interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) per l'utilizzo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `pDispenser`  
 [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) puntatore per il dispenser di metadati.  
  
 `pErrorHandler`  
 [Interfaccia IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) puntatore a un'interfaccia di gestione degli errori facoltativo.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
