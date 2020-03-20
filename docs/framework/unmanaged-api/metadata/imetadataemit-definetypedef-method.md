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
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175759"
---
# <a name="imetadataemitdefinetypedef-method"></a>Metodo IMetaDataEmit::DefineTypeDef
Crea una definizione di tipo per un tipo Common Language Runtime e ottiene un token di metadati per tale definizione di tipo.  
  
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
 [in] Nome del tipo in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` attributi. Si tratta di `CoreTypeAttr` una maschera di bit di valori.  
  
 `tkExtends`  
 [in] Token della classe base. Deve essere un `mdTypeDef` o `mdTypeRef` un token.  
  
 `rtkImplements`  
 [in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `ptd`  
 [fuori] Token `mdTypeDef` assegnato.  
  
## <a name="remarks"></a>Osservazioni  
 Un flag `dwTypeDefFlags` in specifica se il tipo creato è un tipo di riferimento del sistema di tipi comune (classe o interfaccia) o un tipo di valore di sistema di tipo comune.  
  
 A seconda dei parametri forniti, questo metodo, come effetto `mdInterfaceImpl` collaterale, può anche creare un record per ogni interfaccia ereditata o implementata da questo tipo. Tuttavia, questo metodo non `mdInterfaceImpl` restituisce nessuno di questi token. Se un client desidera aggiungere `mdInterfaceImpl` o modificare un `IMetaDataImport` token in un secondo momento, deve utilizzare l'interfaccia per enumerarli. Se si desidera utilizzare la `[default]` semantica COM dell'interfaccia, è necessario `rtkImplements`fornire l'interfaccia predefinita come primo elemento in ; un attributo personalizzato impostato sulla classe indicherà che la classe dispone `mdInterfaceImpl` di un'interfaccia predefinita (che si presuppone sempre essere il primo token dichiarato per la classe).  
  
 Ogni elemento `rtkImplements` della matrice `mdTypeDef` `mdTypeRef` contiene un o token. L'ultimo elemento nella `mdTokenNil`matrice deve essere .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
