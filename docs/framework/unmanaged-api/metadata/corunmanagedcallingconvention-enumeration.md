---
title: Enumerazione CorUnmanagedCallingConvention
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008950"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>Enumerazione CorUnmanagedCallingConvention
Specifica le convenzioni di chiamata per il codice non gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Convenzione di chiamata del linguaggio C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Convenzione di chiamata standard.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Convenzione di chiamata "This".|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Convenzione di chiamata "Fast".|  
|`IMAGE_CEE_CS_CALLCONV_C`|Non usato.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Non usato.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Non usato.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Non usato.|  
  
## <a name="remarks"></a>Commenti  
 CLR non supporta la convenzione di chiamata "Fast" nella versione .NET Framework 1,0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
