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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fc6d08e960b0ba82c76945a318ec723546f71b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444906"
---
# <a name="assemblyflags-enumeration"></a>Enumerazione AssemblyFlags
Contiene valori che descrivono le funzionalità in fase di esecuzione di un assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`afImplicitExportedTypes`|Specifica che le definizioni dei tipi esportata sono implicite all'interno dei file che costituiscono l'assembly. Nelle versioni di .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.|  
|`afImplicitResources`|Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly. In .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.|  
|`afNonSideBySideAppDomain`|Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso dominio applicazione.|  
|`afNonSideBySideProcess`|Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso processo.|  
|`afNonSideBySideMachine`|Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso computer.|  
  
## <a name="remarks"></a>Note  
 I valori compresi tra 0x0010 e 0x0070, estremi inclusi, vengono utilizzati per descrivere le funzionalità di compatibilità side-by-side dell'assembly di riferimento. Se viene impostato alcuno di questi valori, l'assembly viene considerato compatibile side-by-side.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
