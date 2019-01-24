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
ms.openlocfilehash: 006360203518f74adb964634af52505a71d51473
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587099"
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
  
#### <a name="parameters"></a>Parametri  
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
