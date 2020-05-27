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
ms.openlocfilehash: 199a649b0481c2a740926636345eefbda6831ef2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007546"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`pmNoMangle`|Usare il nome di ogni membro come specificato.|  
|`pmCharSetMask`|Riservato.|  
|`pmCharSetNotSpec`|Riservato.|  
|`pmCharSetAnsi`|Esegue il marshalling delle stringhe come stringhe di caratteri a più byte.|  
|`pmCharSetUnicode`|Esegue il marshalling delle stringhe come caratteri Unicode a 2 byte.|  
|`pmCharSetAuto`|Esegue automaticamente il marshalling delle stringhe in modo appropriato per il sistema operativo di destinazione. Il valore predefinito è Unicode in Windows NT, Windows 2000, Windows XP e la famiglia Windows Server 2003; il valore predefinito è ANSI in Windows 98 e Windows me.|  
|`pmBestFitUseAssem`|Riservato.|  
|`pmBestFitEnabled`|Eseguire il mapping più appropriato di caratteri Unicode privi di una corrispondenza esatta nel set di caratteri ANSI.|  
|`pmBestFitDisabled`|Non eseguire il mapping più appropriato di caratteri Unicode. In questo caso, tutti i caratteri unmappable verranno sostituiti da'?'.|  
|`pmBestFitMask`|Riservato.|  
|`pmThrowOnUnmappableCharUseAssem`|Riservato.|  
|`pmThrowOnUnmappableCharEnabled`|Genera un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.|  
|`pmThrowOnUnmappableCharDisabled`|Non generare un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.|  
|`pmThrowOnUnmappableCharMask`|Riservato|  
|`pmSupportsLastError`|Consentire al chiamato di chiamare la funzione Win32 `SetLastError` prima di restituire dal metodo con attributi.|  
|`pmCallConvMask`|Riservato|  
|`pmCallConvWinapi`|Usare la convenzione di chiamata della piattaforma predefinita. In Windows, ad esempio, il valore predefinito è `StdCall` e Windows CE .NET è `Cdecl` .|  
|`pmCallConvCdecl`|Utilizzare la `Cdecl` convenzione di chiamata. In questo caso, il chiamante pulisce lo stack. In questo modo è possibile chiamare funzioni con `varargs` , ovvero funzioni che accettano un numero variabile di parametri.|  
|`pmCallConvStdcall`|Utilizzare la `StdCall` convenzione di chiamata. In questo caso, il chiamato pulisce lo stack. Si tratta della convenzione predefinita per chiamare funzioni non gestite tramite platform invoke.|  
|`pmCallConvThiscall`|Utilizzare la `ThisCall` convenzione di chiamata. In questo caso, il primo parametro è il `this` puntatore e viene archiviato nel registro ecx. Altri parametri vengono inseriti nello stack. La `ThisCall` convenzione di chiamata viene utilizzata per chiamare metodi sulle classi esportate da una dll non gestita.|  
|`pmCallConvFastcall`|Riservato.|  
|`pmMaxValue`|Riservato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
