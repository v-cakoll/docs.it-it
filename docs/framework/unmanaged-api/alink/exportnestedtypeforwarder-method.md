---
title: Metodo ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dfb31a2fad8a07b3821ac85bbb43b25693f11d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="exportnestedtypeforwarder-method"></a>Metodo ExportNestedTypeForwarder
Aggiunge un server d'inoltro di tipo per un tipo annidato per la tabella dei tipi dell'assembly specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExportNestedTypeForwarder(  
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
 ID di token o l'assembly del file che definisce il tipo di file.  
  
 `TypeToken`  
 Token per il tipo.  
  
 `ParentType`  
 Token di tipo padre.  
  
 `pszTypename`  
 Nome completo del tipo da esportare.  
  
 `dwFlags`  
 `ComType` flag, ad esempio `tdPublic` o `tdNested`.  
  
 `pType`  
 Riceve il token del tipo di esportazione. Ciò è necessario solo per la creazione di tipi annidati.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
