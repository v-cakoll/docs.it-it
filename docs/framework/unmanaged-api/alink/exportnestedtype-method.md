---
title: Metodo ExportNestedType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedType
helpviewer_keywords: ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6d40fffb2d40012d69599ad1bfcdbdaf454aa02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtype-method"></a>Metodo ExportNestedType
Specifica i tipi annidati come esportabile. Il [metodo ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) può anche esportazione dei tipi annidati, ma questo metodo è più veloce.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly da cui esportare.  
  
 `FileToken`  
 Token di file o l'Assembly del file che definisce il tipo da rendere esportabile.  
  
 `TypeToken`  
 Tipo di token di tipo da rendere esportabile.  
  
 `ParentType`  
 Token di tipo padre.  
  
 `pszTypename`  
 Nome completo del tipo da esportare.  
  
 `dwFlags`  
 `ComType`flag come `tdPublic` o `tdNested`. Questo valore può essere passato a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Riceve il token del tipo esportato.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
