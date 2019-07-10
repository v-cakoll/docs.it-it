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
ms.openlocfilehash: bb8fba433c5f7ef9701caf61971841672f46b425
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742029"
---
# <a name="exportnestedtypeforwarder-method"></a>Metodo ExportNestedTypeForwarder
Aggiunge un server d'inoltro di tipo per un tipo annidato alla tabella di tipo di assembly specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly da cui esportare.  
  
 `FileToken`  
 ID token o l'assembly del file che definisce il tipo di file.  
  
 `TypeToken`  
 Token per il tipo.  
  
 `ParentType`  
 Token del tipo padre.  
  
 `pszTypename`  
 Nome completo del tipo da esportare.  
  
 `dwFlags`  
 `ComType` ad esempio i flag `tdPublic` o `tdNested`.  
  
 `pType`  
 Riceve il token del tipo di esportazione. Ciò è necessario solo per la creazione di tipi annidati.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
