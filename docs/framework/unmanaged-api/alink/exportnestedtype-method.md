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
ms.openlocfilehash: 570e48788a11045882ef546bf6bc22315c2a02b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777271"
---
# <a name="exportnestedtype-method"></a>Metodo ExportNestedType
Specifica i tipi annidati come esportabili. Il [Metodo ExportType](exporttype-method.md) può anche esportare tipi annidati, ma questo metodo è più veloce.  
  
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
 ID dell'assembly da cui eseguire l'esportazione.  
  
 `FileToken`  
 Token del file o assembly del file che definisce il tipo da rendere esportabile.  
  
 `TypeToken`  
 Token di tipo di tipo da rendere esportabile.  
  
 `ParentType`  
 Token del tipo padre.  
  
 `pszTypename`  
 Nome completo del tipo da esportare.  
  
 `dwFlags`  
 `ComType`flag come `tdPublic` o `tdNested`. Questo valore può essere passato al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Riceve il token per il tipo esportato.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
