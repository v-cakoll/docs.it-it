---
title: Metodo IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: 612463bca18c23fac0b086adde2d208a0fbc5ae5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008170"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>Metodo IMetaDataAssemblyEmit::DefineAssemblyRef
Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKeyOrToken`  
 in Chiave pubblica del server di pubblicazione dell'assembly a cui si fa riferimento. La funzione helper [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) può essere usata per ottenere l'hash della chiave pubblica da passare come parametro.  
  
 `cbPublicKeyOrToken`  
 in Dimensioni in byte di `pbPublicKeyOrToken` .  
  
 `szName`  
 in Nome di testo leggibile dell'assembly. Questo valore non deve superare i 1024 caratteri.  
  
 `pMetaData`  
 in Istanza di ASSEMBLYMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali dell'assembly a cui si fa riferimento.  
  
 `pbHashValue`  
 in Dati hash associati all'assembly a cui si fa riferimento. Facoltativa.  
  
 `cbHashValue`  
 in Dimensioni in byte di `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 in Combinazione bit per bit di valori [CorAssemblyFlags](corassemblyflags-enumeration.md) che influenzano il comportamento del motore di esecuzione.  
  
 `pmdar`  
 out Puntatore al `AssemblyRef` token di metadati restituito.  
  
## <a name="remarks"></a>Commenti  
 `AssemblyRef`È necessario definire una struttura di metadati per ogni assembly a cui fa riferimento questo assembly.  
  
 In fase di esecuzione, i dettagli di un assembly a cui viene fatto riferimento vengono passati al resolver dell'assembly, con l'indicazione che rappresentano le informazioni "come compilate". Il resolver dell'assembly applica quindi i criteri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
