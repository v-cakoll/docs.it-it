---
title: Metodo ExportType
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ce6478f0331c590a2384a4e7e9b5621c050715d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623638"
---
# <a name="exporttype-method"></a>Metodo ExportType
Specifica che un tipo può essere esportato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly da cui esportare.  
  
 `FileToken`  
 Assembly o token ID di file che definisce il tipo può essere esportato.  
  
 `TypeToken`  
 Token del tipo da rendere esportabile.  
  
 `pszTypename`  
 Nome completo del tipo da rendere esportabile.  
  
 `dwFlags`  
 `ComType` ad esempio i flag `tdPublic` o `tdNested`. Questo parametro può essere passato a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Riceve il token del tipo esportato.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
