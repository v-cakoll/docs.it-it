---
title: Enumerazione AssemblyFlags
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
ms.openlocfilehash: 1cb84b94b37a2e9e8dd4d20d09cbca82db290c0f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009452"
---
# <a name="assemblyflags-enumeration"></a>Enumerazione AssemblyFlags
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Specifica che le definizioni dei tipi esportati sono implicite all'interno dei file che costituiscono l'assembly. In .NET Framework versioni 1,0 e 1,1, questo valore viene sempre impostato.|  
|`afImplicitResources`|Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly. In .NET Framework 1,0 e 1,1, questo valore viene sempre impostato.|  
|`afNonSideBySideAppDomain`|Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso dominio applicazione.|  
|`afNonSideBySideProcess`|Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso processo.|  
|`afNonSideBySideMachine`|Specifica che l'assembly non può essere eseguito con altre versioni se sono in esecuzione nello stesso computer.|  
  
## <a name="remarks"></a>Commenti  
 I valori compresi tra 0x0010 e 0x0070, inclusi, vengono utilizzati per descrivere le funzionalità di compatibilità affiancata dell'assembly a cui si fa riferimento. Se nessuno di questi valori è impostato, si presuppone che l'assembly sia compatibile side-by-side.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MsCorEE. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
