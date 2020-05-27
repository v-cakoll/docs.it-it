---
title: Enumerazione CorNativeType
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: dd97c479f12e7bdb015b39a802b398ca2b0bcd3f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007637"
---
# <a name="cornativetype-enumeration"></a>Enumerazione CorNativeType
Contiene valori che descrivono tipi non gestiti nativi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|Obsoleto.|  
|`NATIVE_TYPE_VOID`|Obsoleto.|  
|`NATIVE_TYPE_BOOLEAN`|Valore booleano a 4 byte, dove TRUE è diverso da zero e FALSE è zero.|  
|`NATIVE_TYPE_I1`|Valore intero con segno a 8 bit.|  
|`NATIVE_TYPE_U1`|Valore intero senza segno a 8 bit.|  
|`NATIVE_TYPE_I2`|Valore intero con segno a 16 bit.|  
|`NATIVE_TYPE_U2`|Valore intero senza segno a 16 bit.|  
|`NATIVE_TYPE_I4`|Valore intero a 32 bit con segno.|  
|`NATIVE_TYPE_U4`|Valore intero senza segno a 32 bit.|  
|`NATIVE_TYPE_I8`|Valore intero con segno a 64 bit.|  
|`NATIVE_TYPE_U8`|Valore intero senza segno a 64 bit.|  
|`NATIVE_TYPE_R4`|Valore numerico a virgola mobile a 4 byte.|  
|`NATIVE_TYPE_R8`|Valore numerico a virgola mobile a 8 byte.|  
|`NATIVE_TYPE_SYSCHAR`|Obsoleto.|  
|`NATIVE_TYPE_VARIANT`|Obsoleto.|  
|`NATIVE_TYPE_CURRENCY`|Tipo COM numerico che corrisponde al <xref:System.Decimal> tipo gestito.|  
|`NATIVE_TYPE_PTR`|Obsoleto.|  
|`NATIVE_TYPE_DECIMAL`|Obsoleto.|  
|`NATIVE_TYPE_DATE`|Obsoleto.|  
|`NATIVE_TYPE_BSTR`|Interoperabilità COM.|  
|`NATIVE_TYPE_LPSTR`|Valore stringa LPSTR.|  
|`NATIVE_TYPE_LPWSTR`|Valore stringa LPWSTR.|  
|`NATIVE_TYPE_LPTSTR`|Valore stringa LPTSTR.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|Valore stringa fisso definito dal sistema.|  
|`NATIVE_TYPE_OBJECTREF`|Obsoleto.|  
|`NATIVE_TYPE_IUNKNOWN`|Interoperabilità COM.|  
|`NATIVE_TYPE_IDISPATCH`|Interoperabilità COM.|  
|`NATIVE_TYPE_STRUCT`|Valore della struttura nativa.|  
|`NATIVE_TYPE_INTF`|Interoperabilità COM.|  
|`NATIVE_TYPE_SAFEARRAY`|Interoperabilità COM.|  
|`NATIVE_TYPE_FIXEDARRAY`|Valore di matrice a lunghezza fissa.|  
|`NATIVE_TYPE_INT`|Valore intero con segno a 16 bit nativo.|  
|`NATIVE_TYPE_UINT`|Valore di Unsigned Integer a 16 bit nativo.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|Obsoleto.<br /><br /> Usare NATIVE_TYPE_STRUCT.|  
|`NATIVE_TYPE_BYVALSTR`|Interoperabilità COM.|  
|`NATIVE_TYPE_ANSIBSTR`|Interoperabilità COM.|  
|`NATIVE_TYPE_TBSTR`|Interoperabilità COM.<br /><br /> Selezionare BSTR o ANSIBSTR a seconda della piattaforma.|  
|`NATIVE_TYPE_VARIANTBOOL`|Valore booleano a 2 byte, dove TRUE è-1 e FALSE è zero.|  
|`NATIVE_TYPE_FUNC`|Un puntatore di funzione.|  
|`NATIVE_TYPE_ASANY`|Riferimento a qualsiasi tipo nativo.|  
|`NATIVE_TYPE_ARRAY`|Riferimento a una matrice con membri di un tipo non specificato.|  
|`NATIVE_TYPE_LPSTRUCT`|Puntatore di tipo Integer a 32 bit a una struttura.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|Tipo nativo del gestore di marshalling personalizzato.<br /><br /> Questo deve essere seguito da una stringa con il formato seguente: "nome del tipo nativo/nome del tipo del gestore di marshalling 0Custom/cookie 0Optional/0" o "{GUID di tipo nativo}/0Custom nome tipo del gestore di marshalling/0Optional cookie/0"|  
|`NATIVE_TYPE_ERROR`|Interoperabilità COM.<br /><br /> Con ELEMENT_TYPE_I4 questo tipo viene mappato a VT_HRESULT.|  
|`NATIVE_TYPE_IINSPECTABLE`|Tipo nativo `IInspectable` .|  
|`NATIVE_TYPE_HSTRING`|Oggetto nativo `HString` .|  
|`NATIVE_TYPE_MAX`|Valore non valido.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [Enumerazioni dei metadati](metadata-enumerations.md)
