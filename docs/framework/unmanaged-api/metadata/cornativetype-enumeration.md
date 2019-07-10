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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 846c754aeb0a710fa70e906e666f694eaa77c576
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781704"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="9f050-102">Enumerazione CorNativeType</span><span class="sxs-lookup"><span data-stu-id="9f050-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="9f050-103">Contiene valori che descrivono tipi non gestiti nativi.</span><span class="sxs-lookup"><span data-stu-id="9f050-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f050-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f050-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9f050-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9f050-105">Members</span></span>  
  
|<span data-ttu-id="9f050-106">Member</span><span class="sxs-lookup"><span data-stu-id="9f050-106">Member</span></span>|<span data-ttu-id="9f050-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f050-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="9f050-108">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="9f050-109">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="9f050-110">Un valore booleano a 4 byte, dove TRUE è diverso da zero e FALSE è zero.</span><span class="sxs-lookup"><span data-stu-id="9f050-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="9f050-111">Valore intero con segno a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="9f050-112">Un valore intero senza segno a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="9f050-113">Valore intero con segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="9f050-114">Un valore intero senza segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="9f050-115">Valore intero a 32 bit con segno.</span><span class="sxs-lookup"><span data-stu-id="9f050-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="9f050-116">Valore intero senza segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="9f050-117">Valore intero con segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="9f050-118">Un valore intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="9f050-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="9f050-119">Un valore numerico a virgola mobile a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="9f050-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="9f050-120">8 byte a virgola mobile a valore numerico.</span><span class="sxs-lookup"><span data-stu-id="9f050-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="9f050-121">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="9f050-122">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="9f050-123">Un tipo COM numerico che corrisponde a quella gestita <xref:System.Decimal> tipo.</span><span class="sxs-lookup"><span data-stu-id="9f050-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="9f050-124">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="9f050-125">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="9f050-126">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="9f050-127">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="9f050-128">Valore stringa LPSTR.</span><span class="sxs-lookup"><span data-stu-id="9f050-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="9f050-129">Valore stringa LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="9f050-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="9f050-130">Valore stringa LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="9f050-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="9f050-131">Valore stringa fissa, definito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="9f050-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="9f050-132">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="9f050-133">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="9f050-134">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="9f050-135">Valore di una struttura nativa.</span><span class="sxs-lookup"><span data-stu-id="9f050-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="9f050-136">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="9f050-137">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="9f050-138">Un valore di matrice a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="9f050-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="9f050-139">Valore intero con segno a 16 bit nativo.</span><span class="sxs-lookup"><span data-stu-id="9f050-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="9f050-140">Valore intero senza segno a 16 bit nativo.</span><span class="sxs-lookup"><span data-stu-id="9f050-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="9f050-141">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9f050-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="9f050-142">Usare NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="9f050-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="9f050-143">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="9f050-144">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="9f050-145">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="9f050-146">Selezionare BSTR o ANSIBSTR a seconda della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="9f050-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="9f050-147">Valore booleano a 2 byte, dove TRUE è -1 e FALSE è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="9f050-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="9f050-148">Un puntatore di funzione.</span><span class="sxs-lookup"><span data-stu-id="9f050-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="9f050-149">Un riferimento a qualsiasi tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="9f050-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="9f050-150">Un riferimento a una matrice con i membri di un tipo non specificato.</span><span class="sxs-lookup"><span data-stu-id="9f050-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="9f050-151">Puntatore a 32 bit a una struttura.</span><span class="sxs-lookup"><span data-stu-id="9f050-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="9f050-152">Un tipo nativo di gestore di marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9f050-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="9f050-153">Questo deve essere seguito da una stringa nel formato seguente: "Il gestore di marshalling di tipo nativo 0Nome di nome/tipo/0Cookie/0" o "{nativa digitare GUID} / tipo di gestore di marshalling 0Nome 0Cookie / / 0"</span><span class="sxs-lookup"><span data-stu-id="9f050-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="9f050-154">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="9f050-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="9f050-155">Con ELEMENT_TYPE_I4 questo tipo è mappato a VT_HRESULT.</span><span class="sxs-lookup"><span data-stu-id="9f050-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="9f050-156">Nativo `IInspectable` tipo.</span><span class="sxs-lookup"><span data-stu-id="9f050-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="9f050-157">Nativo `HString`.</span><span class="sxs-lookup"><span data-stu-id="9f050-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="9f050-158">Un valore non valido.</span><span class="sxs-lookup"><span data-stu-id="9f050-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f050-159">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f050-159">Requirements</span></span>  
 <span data-ttu-id="9f050-160">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f050-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f050-161">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="9f050-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9f050-162">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f050-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f050-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f050-163">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="9f050-164">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="9f050-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
