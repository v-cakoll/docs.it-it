---
title: Metodo SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a19762cbec91871d7af617957896e4ee34944fba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949071"
---
# <a name="setassemblyfile-method"></a>Metodo SetAssemblyFile
Assegna il nome dell'assembly da compilare. Non per essere utilizzato durante la creazione di moduli non associati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszFilename`  
 Nome completo del file manifesto.  
  
 `pEmitter`  
 Puntatore alla [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia.  
  
 `afFlags`  
 Contrassegna come definito in [enumerazione AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).  
  
 `pAssemblyID`  
 Puntatore all'ID dell'assembly risultante.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
