---
title: AssemblyFlags Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444307"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags Enumeration
Contiene valori che descrivono le funzionalità di run-time di un assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Specifica che le definizioni dei tipi esportati sono implicite all'interno dei file che costituiscono l'assembly. In .NET Framework versioni 1,0 e 1,1, questo valore viene sempre impostato.|  
|`afImplicitResources`|Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly. In .NET Framework 1,0 e 1,1, questo valore viene sempre impostato.|  
|`afNonSideBySideAppDomain`|Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso dominio applicazione.|  
|`afNonSideBySideProcess`|Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso processo.|  
|`afNonSideBySideMachine`|Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso computer.|  
  
## <a name="remarks"></a>Note  
 I valori compresi tra 0x0010 e 0x0070, inclusi, vengono utilizzati per descrivere le funzionalità di compatibilità affiancata dell'assembly a cui si fa riferimento. Se nessuno di questi valori è impostato, si presuppone che l'assembly sia compatibile side-by-side.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MsCorEE. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
