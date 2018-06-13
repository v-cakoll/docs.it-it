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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b249d26335a66b55d0643f3e75bfd90554f731e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448869"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>Enumerazione CorUnmanagedCallingConvention
Specifica le convenzioni di chiamata per codice non gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|La convenzione di chiamata del linguaggio C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|La convenzione di chiamata standard.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|"This" convenzione di chiamata.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|La convenzione di chiamata "veloce".|  
|`IMAGE_CEE_CS_CALLCONV_C`|Non usato.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Non usato.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Non usato.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Non usato.|  
  
## <a name="remarks"></a>Note  
 Common Language Runtime non supporta la convenzione di chiamata "veloce" in .NET Framework versione 1.0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
