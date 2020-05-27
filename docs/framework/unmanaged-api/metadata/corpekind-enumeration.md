---
title: Enumerazione CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 8b6eab8156f72847eb6dd3369950f9b46a3fc877
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007559"
---
# <a name="corpekind-enumeration"></a>Enumerazione CorPEKind
Contiene valori che descrivono un file eseguibile portabile (PE), come restituito da una chiamata a [IMetaDataImport2:: GetPEKind](imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`peNot`|Indica che non si tratta di un file PE.|  
|`peILOnly`|Indica che il file PE contiene solo codice gestito.|  
|`pe32BitRequired`|Indica che il file PE esegue chiamate Win32.|  
|`pe32Plus`|Indica che il file PE viene eseguito su una piattaforma a 64 bit.|  
|`pe32Unmanaged`|Indica che il file PE è codice nativo.|  
|pe32BitPreferred|Indica che il file PE è indipendente dalla piattaforma e preferisce essere caricato in un ambiente a 32 bit.|  
  
## <a name="remarks"></a>Commenti  
 Questi valori possono essere utilizzati in combinazioni bit per bit.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
