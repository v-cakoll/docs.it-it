---
title: Metodo IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450220"
---
# <a name="imetadataemitdefinetypedef-method"></a>Metodo IMetaDataEmit::DefineTypeDef
Crea una definizione di tipo per un tipo di Common Language Runtime e ottiene un token di metadati per la definizione del tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szTypeDef`  
 in Nome del tipo in Unicode.  
  
 `dwTypeDefFlags`  
 [in] attributi `TypeDef`. Si tratta di una maschera di maschera dei valori `CoreTypeAttr`.  
  
 `tkExtends`  
 in Token della classe di base. Deve essere un `mdTypeDef` o un token di `mdTypeRef`.  
  
 `rtkImplements`  
 in Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `ptd`  
 out Token `mdTypeDef` assegnato.  
  
## <a name="remarks"></a>Osservazioni  
 Un flag in `dwTypeDefFlags` specifica se il tipo da creare è un tipo di riferimento Common Type System (classe o interfaccia) o un tipo di valore Common Type System.  
  
 A seconda dei parametri forniti, questo metodo, come effetto collaterale, può anche creare un record `mdInterfaceImpl` per ogni interfaccia ereditata o implementata da questo tipo. Tuttavia, questo metodo non restituisce alcuno di questi token di `mdInterfaceImpl`. Se un client desidera aggiungere o modificare un token di `mdInterfaceImpl` in un secondo momento, è necessario utilizzare l'interfaccia `IMetaDataImport` per enumerarli. Se si desidera utilizzare la semantica COM dell'interfaccia `[default]`, è necessario fornire l'interfaccia predefinita come primo elemento nel `rtkImplements`; un attributo personalizzato impostato sulla classe indicherà che la classe dispone di un'interfaccia predefinita (che viene sempre considerata il primo token di `mdInterfaceImpl` dichiarato per la classe).  
  
 Ogni elemento della matrice `rtkImplements` include un token `mdTypeDef` o `mdTypeRef`. L'ultimo elemento nella matrice deve essere `mdTokenNil`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
