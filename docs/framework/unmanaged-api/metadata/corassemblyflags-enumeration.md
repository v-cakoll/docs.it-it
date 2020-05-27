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
ms.openlocfilehash: b1a83f07f03ddb17d5c306453cf838101a77ed65
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007936"
---
# <a name="corassemblyflags-enumeration"></a>Enumerazione CorAssemblyFlags
Contiene valori che descrivono i metadati applicati alla compilazione di un assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`afPublicKey`|Indica che il riferimento all'assembly include la chiave pubblica completa e senza hash.|  
|`afPA_None`|Indica che l'architettura del processore non è specificata.|  
|`afPA_MSIL`|Indica che l'architettura del processore è neutra (PE32).|  
|`afPA_x86`|Indica che l'architettura del processore è x86 (PE32).|  
|`afPA_IA64`|Indica che l'architettura del processore è Itanium (PE32 +).|  
|`afPA_AMD64`|Indica che l'architettura del processore è AMD x64 (PE32 +).|  
|`afPA_ARM`|Indica che l'architettura del processore è ARM (PE32).|  
|`afPA_NoPlatform`|Indica che l'assembly è un assembly di riferimento. ovvero si applica a qualsiasi architettura, ma non può essere eseguita su qualsiasi architettura. Il flag è quindi uguale a `afPA_Mask` .|  
|`afPA_Specified`|Indica che i flag di architettura del processore devono essere propagati al `AssemblyRef` record.|  
|`afPA_Mask`|Maschera che descrive l'architettura del processore.|  
|`afPA_FullMask`|Specifica che è inclusa la descrizione dell'architettura del processore.|  
|`afPA_Shift`|Indica un conteggio dei turni nei flag di architettura del processore da e verso l'indice.|  
|`afEnableJITcompileTracking`|Indica il valore corrispondente da <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> dell'oggetto <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afDisableJITcompileOptimizer`|Indica il valore corrispondente da <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> dell'oggetto <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afRetargetable`|Indica che l'assembly può essere ridestinato in fase di esecuzione a un assembly di un server di pubblicazione diverso.|  
|`afContentType_Mask`|Maschera che descrive il tipo di contenuto.|  
|`afContentType_Default`|Indica il tipo di contenuto predefinito.|  
|`afContentType_WindowsRuntime`|Indica il tipo di contenuto Windows Runtime.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
