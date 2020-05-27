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
ms.openlocfilehash: 310319e8fefe80017c58706e2beaee5eb1e78422
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007906"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="ba36c-102">Enumerazione CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="ba36c-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="ba36c-103">Contiene valori che descrivono i tipi di convenzioni per le chiamate effettuate in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ba36c-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba36c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba36c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ba36c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ba36c-105">Members</span></span>  
  
|<span data-ttu-id="ba36c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ba36c-106">Member</span></span>|<span data-ttu-id="ba36c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba36c-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="ba36c-108">Indica una convenzione di chiamata predefinita.</span><span class="sxs-lookup"><span data-stu-id="ba36c-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="ba36c-109">Indica che il metodo accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="ba36c-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="ba36c-110">Indica che la chiamata è a un campo.</span><span class="sxs-lookup"><span data-stu-id="ba36c-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="ba36c-111">Indica che la chiamata è a un metodo locale.</span><span class="sxs-lookup"><span data-stu-id="ba36c-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="ba36c-112">Indica che la chiamata è a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ba36c-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="ba36c-113">Indica che la chiamata non è gestita.</span><span class="sxs-lookup"><span data-stu-id="ba36c-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="ba36c-114">Indica una creazione di un'istanza di metodo generica.</span><span class="sxs-lookup"><span data-stu-id="ba36c-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="ba36c-115">Indica una chiamata PInvoke a 64 bit a un metodo che accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="ba36c-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="ba36c-116">Descrive un valore a 4 bit non valido.</span><span class="sxs-lookup"><span data-stu-id="ba36c-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="ba36c-117">Indica che la convenzione di chiamata è descritta dai quattro bit inferiori.</span><span class="sxs-lookup"><span data-stu-id="ba36c-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="ba36c-118">Indica che il bit superiore descrive un `this` parametro.</span><span class="sxs-lookup"><span data-stu-id="ba36c-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="ba36c-119">Indica che un `this` parametro viene descritto in modo esplicito nella firma.</span><span class="sxs-lookup"><span data-stu-id="ba36c-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="ba36c-120">Indica una firma del metodo generico con un numero esplicito di argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="ba36c-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="ba36c-121">Questo precede un numero di parametri normali.</span><span class="sxs-lookup"><span data-stu-id="ba36c-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba36c-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba36c-122">Requirements</span></span>  
 <span data-ttu-id="ba36c-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba36c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba36c-124">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="ba36c-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ba36c-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba36c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba36c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba36c-126">See also</span></span>

- [<span data-ttu-id="ba36c-127">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ba36c-127">Metadata Enumerations</span></span>](metadata-enumerations.md)
