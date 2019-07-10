---
title: Metodo ExportNestedType
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfaedad48291ac09f6959bc7b314ae0d9da76e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742051"
---
# <a name="exportnestedtype-method"></a>Metodo ExportNestedType
Specifica i tipi annidati come esportabile. Il [metodo ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) possono anche esportazione dei tipi nidificati, ma questo metodo è più veloce.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly da cui esportare.  
  
 `FileToken`  
 Token file o l'Assembly del file che definisce il tipo da rendere esportabile.  
  
 `TypeToken`  
 Tipo di token del tipo da rendere esportabile.  
  
 `ParentType`  
 Token del tipo padre.  
  
 `pszTypename`  
 Nome completo del tipo da esportare.  
  
 `dwFlags`  
 `ComType` ad esempio i flag `tdPublic` o `tdNested`. Questo valore può essere passato a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
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
