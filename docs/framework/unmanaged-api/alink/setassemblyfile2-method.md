---
title: Metodo SetAssemblyFile2
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59bfc6785d3ad195e219afc323b7fdb513d8fefc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949058"
---
# <a name="setassemblyfile2-method"></a>Metodo SetAssemblyFile2
Imposta il nome e le opzioni per un nuovo assembly. Non chiamare questo metodo quando si creano moduli non associati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome del file manifesto.  
  
 `pEmitter`  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interfaccia per questo file.  
  
 `afFlags`  
 Opzioni rappresentato da [enumerazione AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).  
  
 `pAssemblyID`  
 Riceve l'ID univoco per l'assembly in fase di costruzione.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
