---
title: Enumerazione CorMethodImpl
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: b32e8f0b03ef6d550c384f3d932cc295a7270028
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007663"
---
# <a name="cormethodimpl-enumeration"></a>Enumerazione CorMethodImpl
Contiene valori che descrivono funzionalità di implementazione dei metodi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`miCodeTypeMask`|Flag che descrivono il tipo di codice.|  
|`miIL`|Specifica che l'implementazione del metodo è Microsoft Intermediate Language (MSIL).|  
|`miNative`|Specifica che l'implementazione del metodo è nativa.|  
|`miOPTIL`|Specifica che l'implementazione del metodo è OPTIl.|  
|`miRuntime`|Specifica che l'implementazione del metodo viene fornita dal Common Language Runtime.|  
|`miManagedMask`|Flag che indicano se il codice è gestito o non gestito.|  
|`miUnmanaged`|Specifica che l'implementazione del metodo non è gestita.|  
|`miManaged`|Specifica che l'implementazione del metodo è gestita.|  
|`miForwardRef`|Specifica che il metodo è definito. Questo flag viene utilizzato principalmente negli scenari di Unione.|  
|`miPreserveSig`|Specifica che la firma del metodo non può essere alterata per una conversione HRESULT.|  
|`miInternalCall`|Riservato per uso interno da parte del Common Language Runtime.|  
|`miSynchronized`|Specifica che il metodo è a thread singolo tramite il corpo.|  
|`miNoInlining`|Specifica che il metodo non può essere impostato come inline.|  
|`miAggressiveInlining`|Specifica che, se possibile, il metodo deve essere inline.|  
|`miNoOptimization`|Specifica che il metodo non deve essere ottimizzato.|  
|`miMaxMethodImplVal`|Valore massimo valido per un oggetto `CorMethodImpl` .|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
