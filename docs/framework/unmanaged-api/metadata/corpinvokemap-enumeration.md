---
title: Enumerazione CorPinvokeMap
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 17b7af7016cf88fd3ae263dd952502d515b0c833
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441553"
---
# <a name="corpinvokemap-enumeration"></a>Enumerazione CorPinvokeMap
Specifica le opzioni per una chiamata PInvoke.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|description|  
|------------|-----------------|  
|`pmNoMangle`|Usare il nome di ogni membro come specificato.|  
|`pmCharSetMask`|Riservato.|  
|`pmCharSetNotSpec`|Riservato.|  
|`pmCharSetAnsi`|Eseguire il marshalling delle stringhe come stringhe di caratteri a più byte.|  
|`pmCharSetUnicode`|Eseguire il marshalling delle stringhe come caratteri Unicode a 2 byte.|  
|`pmCharSetAuto`|Eseguire automaticamente il marshalling delle stringhe appropriate per il sistema operativo di destinazione. Il valore predefinito è Unicode in Windows NT, Windows 2000, Windows XP e la famiglia Windows Server 2003; il valore predefinito è ANSI in Windows 98 e Windows me.|  
|`pmBestFitUseAssem`|Riservato.|  
|`pmBestFitEnabled`|Eseguire il mapping più appropriato di caratteri Unicode privi di una corrispondenza esatta nel set di caratteri ANSI.|  
|`pmBestFitDisabled`|Non eseguire il mapping più appropriato di caratteri Unicode. In questo caso, tutti i caratteri unmappable verranno sostituiti da'?'.|  
|`pmBestFitMask`|Riservato.|  
|`pmThrowOnUnmappableCharUseAssem`|Riservato.|  
|`pmThrowOnUnmappableCharEnabled`|Genera un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.|  
|`pmThrowOnUnmappableCharDisabled`|Non generare un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.|  
|`pmThrowOnUnmappableCharMask`|Riservata|  
|`pmSupportsLastError`|Consentire al chiamato di chiamare la funzione Win32 `SetLastError` prima di restituire dal metodo con attributi.|  
|`pmCallConvMask`|Riservata|  
|`pmCallConvWinapi`|Usare la convenzione di chiamata della piattaforma predefinita. In Windows, ad esempio, il valore predefinito è `StdCall` e Windows CE .NET è `Cdecl`.|  
|`pmCallConvCdecl`|Utilizzare la convenzione di chiamata `Cdecl`. In questo caso, il chiamante pulisce lo stack. In questo modo è possibile chiamare funzioni con `varargs`, ovvero funzioni che accettano un numero variabile di parametri.|  
|`pmCallConvStdcall`|Utilizzare la convenzione di chiamata `StdCall`. In questo caso, il chiamato pulisce lo stack. Si tratta della convenzione predefinita per la chiamata di funzioni non gestite con platform invoke.|  
|`pmCallConvThiscall`|Utilizzare la convenzione di chiamata `ThisCall`. In questo caso, il primo parametro è il puntatore `this` e viene archiviato nel registro ECX. Gli altri parametri vengono inseriti nello stack. La convenzione di chiamata `ThisCall` viene utilizzata per chiamare metodi sulle classi esportate da una DLL non gestita.|  
|`pmCallConvFastcall`|Riservato.|  
|`pmMaxValue`|Riservato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
