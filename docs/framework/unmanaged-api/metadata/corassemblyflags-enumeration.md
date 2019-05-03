---
title: Enumerazione CorAssemblyFlags
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906243"
---
# <a name="corassemblyflags-enumeration"></a>Enumerazione CorAssemblyFlags
Contiene valori che descrivono i metadati applicati alla compilazione di un assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`afPublicKey`|Indica che il riferimento all'assembly contiene la chiave pubblica completa, senza hash.|  
|`afPA_None`|Indica che l'architettura del processore non è specificata.|  
|`afPA_MSIL`|Indica che l'architettura del processore è neutra (PE32).|  
|`afPA_x86`|Indica che l'architettura del processore x86 (PE32).|  
|`afPA_IA64`|Indica che l'architettura del processore Itanium (PE32 +).|  
|`afPA_AMD64`|Indica che l'architettura del processore AMD X64 (PE32 +).|  
|`afPA_ARM`|Indica che l'architettura del processore ARM (PE32).|  
|`afPA_NoPlatform`|Indica che l'assembly è un assembly di riferimento. vale a dire, si applica a qualsiasi architettura, ma non è possibile eseguire su qualsiasi architettura. Di conseguenza, il flag è identico `afPA_Mask`.|  
|`afPA_Specified`|Indica che il flag di architettura del processore deve essere propagato al `AssemblyRef` record.|  
|`afPA_Mask`|Maschera che descrive l'architettura del processore.|  
|`afPA_FullMask`|Specifica che la descrizione dell'architettura del processore è inclusa.|  
|`afPA_Shift`|Indica un conteggio dello spostamento nei flag di architettura di processore da e verso l'indice.|  
|`afEnableJITcompileTracking`|Indica il valore corrispondente dal <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Indica il valore corrispondente dal <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Indica che l'assembly può essere ridestinato in fase di esecuzione a un assembly da un autore diverso.|  
|`afContentType_Mask`|Maschera che descrive il tipo di contenuto.|  
|`afContentType_Default`|Indica il tipo di contenuto predefinito.|  
|`afContentType_WindowsRuntime`|Indica il [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo di contenuto.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
