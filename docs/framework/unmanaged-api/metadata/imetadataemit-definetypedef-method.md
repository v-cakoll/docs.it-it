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
ms.openlocfilehash: dc064b00e32bb6b1d8c2d0c20f571b35919eae23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009340"
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
 [in] `TypeDef` attributi. Si tratta di una maschera di maschera di `CoreTypeAttr` valori.  
  
 `tkExtends`  
 in Token della classe di base. Deve essere un `mdTypeDef` `mdTypeRef` token o.  
  
 `rtkImplements`  
 in Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `ptd`  
 out `mdTypeDef`Token assegnato.  
  
## <a name="remarks"></a>Commenti  
 Un flag in `dwTypeDefFlags` specifica se il tipo creato è un tipo di riferimento Common Type System (classe o interfaccia) o un tipo di valore Common Type System.  
  
 A seconda dei parametri forniti, questo metodo, come effetto collaterale, può anche creare un `mdInterfaceImpl` record per ogni interfaccia ereditata o implementata da questo tipo. Tuttavia, questo metodo non restituisce alcuno di questi `mdInterfaceImpl` token. Se un client desidera aggiungere o modificare un token in un secondo momento `mdInterfaceImpl` , deve utilizzare l' `IMetaDataImport` interfaccia per enumerarli. Se si desidera utilizzare la semantica COM dell' `[default]` interfaccia, è necessario fornire l'interfaccia predefinita come primo elemento in `rtkImplements` ; un attributo personalizzato impostato sulla classe indicherà che la classe dispone di un'interfaccia predefinita (che viene sempre considerata il primo `mdInterfaceImpl` token dichiarato per la classe).  
  
 Ogni elemento della `rtkImplements` matrice include un `mdTypeDef` token o `mdTypeRef` . L'ultimo elemento nella matrice deve essere `mdTokenNil` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
