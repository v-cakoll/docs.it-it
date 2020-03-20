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
ms.openlocfilehash: 09a351db65c7ed310d3eb68c71a5207ed6040dd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177966"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="c9310-102">Enumerazione CorNativeType</span><span class="sxs-lookup"><span data-stu-id="c9310-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="c9310-103">Contiene valori che descrivono tipi non gestiti nativi.</span><span class="sxs-lookup"><span data-stu-id="c9310-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9310-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9310-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c9310-105">Members</span><span class="sxs-lookup"><span data-stu-id="c9310-105">Members</span></span>  
  
|<span data-ttu-id="c9310-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c9310-106">Member</span></span>|<span data-ttu-id="c9310-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9310-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="c9310-108">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="c9310-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="c9310-110">Valore booleano a 4 byte, dove TRUE è diverso da zero e FALSO è zero.</span><span class="sxs-lookup"><span data-stu-id="c9310-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="c9310-111">Valore integer a 8 bit con segno.</span><span class="sxs-lookup"><span data-stu-id="c9310-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="c9310-112">Valore integer senza segno a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="c9310-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="c9310-113">Valore integer a 16 bit con segno.</span><span class="sxs-lookup"><span data-stu-id="c9310-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="c9310-114">Un valore integer senza segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="c9310-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="c9310-115">Valore intero a 32 bit con segno.</span><span class="sxs-lookup"><span data-stu-id="c9310-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="c9310-116">Valore intero senza segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="c9310-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="c9310-117">Valore integer a 64 bit con segno.</span><span class="sxs-lookup"><span data-stu-id="c9310-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="c9310-118">Un valore integer senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="c9310-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="c9310-119">Valore numerico a virgola mobile a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="c9310-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="c9310-120">Valore numerico a virgola mobile a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="c9310-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="c9310-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="c9310-122">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="c9310-123">Tipo COM numerico che <xref:System.Decimal> corrisponde al tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="c9310-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="c9310-124">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="c9310-125">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="c9310-126">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="c9310-127">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="c9310-128">Valore stringa LPSTR.</span><span class="sxs-lookup"><span data-stu-id="c9310-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="c9310-129">Valore stringa LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="c9310-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="c9310-130">Valore stringa LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="c9310-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="c9310-131">Valore stringa fisso definito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c9310-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="c9310-132">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="c9310-133">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="c9310-134">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="c9310-135">Valore della struttura nativo.</span><span class="sxs-lookup"><span data-stu-id="c9310-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="c9310-136">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="c9310-137">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="c9310-138">Valore di matrice a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="c9310-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="c9310-139">Valore integer con segno a 16 bit nativo.</span><span class="sxs-lookup"><span data-stu-id="c9310-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="c9310-140">Valore unsigned integer a 16 bit nativo.</span><span class="sxs-lookup"><span data-stu-id="c9310-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="c9310-141">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c9310-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="c9310-142">Utilizzare NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="c9310-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="c9310-143">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="c9310-144">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="c9310-145">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="c9310-146">Selezionare BSTR o ANSIBSTR a seconda della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c9310-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="c9310-147">Valore booleano a 2 byte, dove TRUE è -1 e FALSE è zero.</span><span class="sxs-lookup"><span data-stu-id="c9310-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="c9310-148">Un puntatore di funzione.</span><span class="sxs-lookup"><span data-stu-id="c9310-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="c9310-149">Un riferimento a qualsiasi tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="c9310-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="c9310-150">Riferimento a una matrice con membri di un tipo non specificato.</span><span class="sxs-lookup"><span data-stu-id="c9310-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="c9310-151">Puntatore integer a 32 bit a una struttura.</span><span class="sxs-lookup"><span data-stu-id="c9310-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="c9310-152">Tipo nativo del gestore di marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c9310-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="c9310-153">Deve essere seguito da una stringa nel seguente formato: "Nome tipo nativo/nome del gestore di marshalling 0Custom nome di tipo/0Cookie facoltativo/0" o "'GUID di tipo nativo'/0Nome del gestore di marshalling personalizzato/0Cookie facoltativo/0"</span><span class="sxs-lookup"><span data-stu-id="c9310-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="c9310-154">Interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="c9310-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="c9310-155">Con ELEMENT_TYPE_I4 questo tipo esegue il mapping a VT_HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c9310-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="c9310-156">Tipo `IInspectable` nativo.</span><span class="sxs-lookup"><span data-stu-id="c9310-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="c9310-157">Un `HString`nativo .</span><span class="sxs-lookup"><span data-stu-id="c9310-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="c9310-158">Valore non valido.</span><span class="sxs-lookup"><span data-stu-id="c9310-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9310-159">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9310-159">Requirements</span></span>  
 <span data-ttu-id="c9310-160">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9310-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9310-161">**Intestazione:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c9310-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c9310-162">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9310-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9310-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9310-163">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="c9310-164">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c9310-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
