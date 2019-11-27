---
title: Enumerazione CorCallingConvention
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
ms.openlocfilehash: 9d4690cb6adedc77717e577d409cb52b18b1b5ca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443829"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="ccb26-102">Enumerazione CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="ccb26-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="ccb26-103">Contiene valori che descrivono i tipi di convenzioni per le chiamate effettuate in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ccb26-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccb26-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="ccb26-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ccb26-105">Members</span></span>  
  
|<span data-ttu-id="ccb26-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ccb26-106">Member</span></span>|<span data-ttu-id="ccb26-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccb26-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="ccb26-108">Indica una convenzione di chiamata predefinita.</span><span class="sxs-lookup"><span data-stu-id="ccb26-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="ccb26-109">Indica che il metodo accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="ccb26-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="ccb26-110">Indica che la chiamata è a un campo.</span><span class="sxs-lookup"><span data-stu-id="ccb26-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="ccb26-111">Indica che la chiamata è a un metodo locale.</span><span class="sxs-lookup"><span data-stu-id="ccb26-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="ccb26-112">Indica che la chiamata è a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ccb26-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="ccb26-113">Indica che la chiamata non è gestita.</span><span class="sxs-lookup"><span data-stu-id="ccb26-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="ccb26-114">Indica una creazione di un'istanza di metodo generica.</span><span class="sxs-lookup"><span data-stu-id="ccb26-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="ccb26-115">Indica una chiamata PInvoke a 64 bit a un metodo che accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="ccb26-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="ccb26-116">Descrive un valore a 4 bit non valido.</span><span class="sxs-lookup"><span data-stu-id="ccb26-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="ccb26-117">Indica che la convenzione di chiamata è descritta dai quattro bit inferiori.</span><span class="sxs-lookup"><span data-stu-id="ccb26-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="ccb26-118">Indica che il bit superiore descrive un parametro di `this`.</span><span class="sxs-lookup"><span data-stu-id="ccb26-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="ccb26-119">Indica che un parametro di `this` viene descritto in modo esplicito nella firma.</span><span class="sxs-lookup"><span data-stu-id="ccb26-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="ccb26-120">Indica una firma del metodo generico con un numero esplicito di argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="ccb26-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="ccb26-121">Questo precede un numero di parametri normali.</span><span class="sxs-lookup"><span data-stu-id="ccb26-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccb26-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ccb26-122">Requirements</span></span>  
 <span data-ttu-id="ccb26-123">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb26-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb26-124">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="ccb26-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ccb26-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb26-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb26-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccb26-126">See also</span></span>

- [<span data-ttu-id="ccb26-127">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ccb26-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
