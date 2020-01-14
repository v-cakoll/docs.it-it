---
title: Enumerazione CorElementType
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
ms.openlocfilehash: a4e9268d292004f447b30c82f1db4d0fe58404fe
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937955"
---
# <a name="corelementtype-enumeration"></a><span data-ttu-id="e9010-102">Enumerazione CorElementType</span><span class="sxs-lookup"><span data-stu-id="e9010-102">CorElementType Enumeration</span></span>

<span data-ttu-id="e9010-103">Specifica un Common Language Runtime <xref:System.Type>, un modificatore di tipo o informazioni su un tipo in una firma del tipo di metadati.</span><span class="sxs-lookup"><span data-stu-id="e9010-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9010-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9010-104">Syntax</span></span>

```cpp
typedef enum CorElementType {
    ELEMENT_TYPE_END            = 0x0,
    ELEMENT_TYPE_VOID           = 0x1,
    ELEMENT_TYPE_BOOLEAN        = 0x2,
    ELEMENT_TYPE_CHAR           = 0x3,
    ELEMENT_TYPE_I1             = 0x4,
    ELEMENT_TYPE_U1             = 0x5,
    ELEMENT_TYPE_I2             = 0x6,
    ELEMENT_TYPE_U2             = 0x7,
    ELEMENT_TYPE_I4             = 0x8,
    ELEMENT_TYPE_U4             = 0x9,
    ELEMENT_TYPE_I8             = 0xa,
    ELEMENT_TYPE_U8             = 0xb,
    ELEMENT_TYPE_R4             = 0xc,
    ELEMENT_TYPE_R8             = 0xd,
    ELEMENT_TYPE_STRING         = 0xe,

    ELEMENT_TYPE_PTR            = 0xf,
    ELEMENT_TYPE_BYREF          = 0x10,

    ELEMENT_TYPE_VALUETYPE      = 0x11,
    ELEMENT_TYPE_CLASS          = 0x12,
    ELEMENT_TYPE_VAR            = 0x13,
    ELEMENT_TYPE_ARRAY          = 0x14,
    ELEMENT_TYPE_GENERICINST    = 0x15,
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,

    ELEMENT_TYPE_I              = 0x18,
    ELEMENT_TYPE_U              = 0x19,
    ELEMENT_TYPE_FNPTR          = 0x1B,
    ELEMENT_TYPE_OBJECT         = 0x1C,
    ELEMENT_TYPE_SZARRAY        = 0x1D,
    ELEMENT_TYPE_MVAR           = 0x1e,

    ELEMENT_TYPE_CMOD_REQD      = 0x1F,
    ELEMENT_TYPE_CMOD_OPT       = 0x20,

    ELEMENT_TYPE_INTERNAL       = 0x21,
    ELEMENT_TYPE_MAX            = 0x22,

    ELEMENT_TYPE_MODIFIER       = 0x40,
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER

} CorElementType;
```

## <a name="members"></a><span data-ttu-id="e9010-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e9010-105">Members</span></span>

|<span data-ttu-id="e9010-106">Member</span><span class="sxs-lookup"><span data-stu-id="e9010-106">Member</span></span>|<span data-ttu-id="e9010-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9010-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="e9010-108">Per uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9010-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="e9010-109">Tipo void.</span><span class="sxs-lookup"><span data-stu-id="e9010-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="e9010-110">Tipo booleano</span><span class="sxs-lookup"><span data-stu-id="e9010-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="e9010-111">Tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="e9010-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="e9010-112">Intero con segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="e9010-113">Intero senza segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="e9010-114">Intero con segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="e9010-115">Intero senza segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="e9010-116">Intero con segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="e9010-117">Intero senza segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="e9010-118">Intero con segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="e9010-119">Intero senza segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="e9010-120">Virgola mobile A 4 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="e9010-121">Virgola mobile a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="e9010-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="e9010-122">Tipo System. String.</span><span class="sxs-lookup"><span data-stu-id="e9010-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="e9010-123">Modificatore di tipo puntatore.</span><span class="sxs-lookup"><span data-stu-id="e9010-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="e9010-124">Modificatore di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="e9010-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="e9010-125">Modificatore di tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="e9010-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="e9010-126">Modificatore del tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="e9010-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="e9010-127">Modificatore di tipo di variabile di classe.</span><span class="sxs-lookup"><span data-stu-id="e9010-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="e9010-128">Modificatore di tipo matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="e9010-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="e9010-129">Modificatore di tipo per i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="e9010-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="e9010-130">Riferimento tipizzato.</span><span class="sxs-lookup"><span data-stu-id="e9010-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="e9010-131">Dimensioni di un intero nativo.</span><span class="sxs-lookup"><span data-stu-id="e9010-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="e9010-132">Dimensioni di un intero nativo senza segno.</span><span class="sxs-lookup"><span data-stu-id="e9010-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="e9010-133">Puntatore a una funzione.</span><span class="sxs-lookup"><span data-stu-id="e9010-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="e9010-134">Tipo System. Object.</span><span class="sxs-lookup"><span data-stu-id="e9010-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="e9010-135">Modificatore di tipo matrice A dimensione inferiore a zero singolo.</span><span class="sxs-lookup"><span data-stu-id="e9010-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="e9010-136">Modificatore di tipo di variabile di metodo.</span><span class="sxs-lookup"><span data-stu-id="e9010-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="e9010-137">Modificatore obbligatorio del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="e9010-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="e9010-138">Modificatore facoltativo del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="e9010-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="e9010-139">Per uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9010-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="e9010-140">Tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="e9010-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="e9010-141">Per uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9010-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="e9010-142">Modificatore di tipo che è una sentinella per un elenco di un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="e9010-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="e9010-143">Per uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9010-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9010-144">Note</span><span class="sxs-lookup"><span data-stu-id="e9010-144">Remarks</span></span>

<span data-ttu-id="e9010-145">I modificatori di tipo costituiscono la base per la rappresentazione di tipi più complessi.</span><span class="sxs-lookup"><span data-stu-id="e9010-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="e9010-146">Un valore del modificatore di tipo `CorElementType` viene applicato al valore che lo segue immediatamente nella firma del tipo.</span><span class="sxs-lookup"><span data-stu-id="e9010-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="e9010-147">Il valore che segue il valore del modificatore di tipo `CorElementType` può essere un valore di tipo semplice `CorElementType`, un token di metadati o un altro valore, come specificato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e9010-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="e9010-148">Tutti i numeri *(numero, numero*di *argomenti*, *token di metadati*, *rango*, *conteggio*e *limite*) vengono archiviati come numeri interi compressi.</span><span class="sxs-lookup"><span data-stu-id="e9010-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="e9010-149">Per informazioni dettagliate, vedere l' [Common Language Infrastructure standard ECMA-335-(CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) nel sito Web ECMA.</span><span class="sxs-lookup"><span data-stu-id="e9010-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="e9010-150">Modificatore di tipo</span><span class="sxs-lookup"><span data-stu-id="e9010-150">Type modifier</span></span>|<span data-ttu-id="e9010-151">Formato</span><span class="sxs-lookup"><span data-stu-id="e9010-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="e9010-152">ELEMENT_TYPE_PTR \<un valore `CorElementType` ></span><span class="sxs-lookup"><span data-stu-id="e9010-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="e9010-153">ELEMENT_TYPE_BYREF \<un valore `CorElementType` ></span><span class="sxs-lookup"><span data-stu-id="e9010-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="e9010-154">ELEMENT_TYPE_VALUETYPE \<un token di metadati `mdTypeDef` ></span><span class="sxs-lookup"><span data-stu-id="e9010-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="e9010-155">ELEMENT_TYPE_CLASS \<un token di metadati `mdTypeDef` ></span><span class="sxs-lookup"><span data-stu-id="e9010-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="e9010-156">Numero \<ELEMENT_TYPE_VAR ></span><span class="sxs-lookup"><span data-stu-id="e9010-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="e9010-157">ELEMENT_TYPE_ARRAY \<un valore `CorElementType` > \<Rank > \<count1 > \<bound1 >... \<countn > \<</span><span class="sxs-lookup"><span data-stu-id="e9010-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="e9010-158">ELEMENT_TYPE_GENERICINST \<un token di metadati `mdTypeDef` > \<numero di argomenti > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="e9010-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="e9010-159">ELEMENT_TYPE_FNPTR \<firma completa per la funzione, inclusa la convenzione di chiamata ></span><span class="sxs-lookup"><span data-stu-id="e9010-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="e9010-160">ELEMENT_TYPE_SZARRAY \<un valore `CorElementType` ></span><span class="sxs-lookup"><span data-stu-id="e9010-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="e9010-161">Numero \<ELEMENT_TYPE_MVAR ></span><span class="sxs-lookup"><span data-stu-id="e9010-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="e9010-162">ELEMENT_TYPE_\<un token di metadati `mdTypeRef` o `mdTypeDef` ></span><span class="sxs-lookup"><span data-stu-id="e9010-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="e9010-163">E_T_CMOD_OPT \<un token di metadati `mdTypeRef` o `mdTypeDef` ></span><span class="sxs-lookup"><span data-stu-id="e9010-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="e9010-164">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e9010-164">Requirements</span></span>

<span data-ttu-id="e9010-165">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9010-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e9010-166">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="e9010-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="e9010-167">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9010-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e9010-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9010-168">See also</span></span>

- [<span data-ttu-id="e9010-169">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="e9010-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
