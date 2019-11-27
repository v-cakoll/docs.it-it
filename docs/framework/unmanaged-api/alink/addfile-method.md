---
title: Metodo AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446679"
---
# <a name="addfile-method"></a>Metodo AddFile
Aggiunge file all'assembly. Può essere usato anche per creare moduli non associati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID univoco dell'assembly da incrementare.  
  
 `pszFilename`  
 Nome completo del file da aggiungere.  
  
 `dwFlags`  
 Flag FileDef COM+, ad esempio `ffContainsNoMetaData` e `ffWriteable`. `dwFlags` viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interfaccia di [interfaccia IMetaDataEmit](../metadata/imetadataemit-interface.md) da usare per creare i metadati, se necessario.  
  
 `pFileToken`  
 Puntatore alla posizione in cui verrà archiviato l'ID univoco del file aggiunto.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
