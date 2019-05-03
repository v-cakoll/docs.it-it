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
ms.openlocfilehash: 7c86a4fd2788c8ea2df5d9e54c5c221afd179704
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905996"
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Specifica che le definizioni dei tipi esportata sono implicite all'interno dei file che costituiscono l'assembly. Nelle versioni 1.0 e 1.1 di .NET Framework, questo valore è sempre presuppone che sia impostato.|  
|`afImplicitResources`|Specifica che le definizioni delle risorse sono implicite all'interno dei file che costituiscono l'assembly. In .NET Framework 1.0 e 1.1, questo valore è sempre presuppone che sia impostato.|  
|`afNonSideBySideAppDomain`|Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso dominio applicazione.|  
|`afNonSideBySideProcess`|Specifica che l'assembly non è possibile eseguire con altre versioni se sono in esecuzione nello stesso processo.|  
|`afNonSideBySideMachine`|Specifica che l'assembly non è possibile eseguire con le altre versioni se sono in esecuzione nello stesso computer.|  
  
## <a name="remarks"></a>Note  
 I valori compresi tra 0x0010 e 0x0070, inclusivo, vengono utilizzati per descrivere le funzionalità side-by-side compatibilità dell'assembly di riferimento. Se nessuno di questi valori sono impostate, l'assembly viene considerato compatibile side-by-side.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MsCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
