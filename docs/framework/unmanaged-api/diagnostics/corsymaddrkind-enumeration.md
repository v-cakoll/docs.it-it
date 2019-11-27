---
title: Enumerazione CorSymAddrKind
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
ms.openlocfilehash: 12f31d0bf224e38418818122dad3586ec687b2ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448584"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="bff7e-102">Enumerazione CorSymAddrKind</span><span class="sxs-lookup"><span data-stu-id="bff7e-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="bff7e-103">Indica il tipo di indirizzo di memoria.</span><span class="sxs-lookup"><span data-stu-id="bff7e-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bff7e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="bff7e-105">Members</span><span class="sxs-lookup"><span data-stu-id="bff7e-105">Members</span></span>  
  
|<span data-ttu-id="bff7e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bff7e-106">Member</span></span>|<span data-ttu-id="bff7e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bff7e-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="bff7e-108">Indica una variabile locale Microsoft Intermediate Language (MSIL) o un indice di parametro.</span><span class="sxs-lookup"><span data-stu-id="bff7e-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="bff7e-109">Indica un indirizzo virtuale relativo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="bff7e-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="bff7e-110">Indica un registro della CPU.</span><span class="sxs-lookup"><span data-stu-id="bff7e-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="bff7e-111">Indica che il primo indirizzo è un registro e il secondo indirizzo è un offset.</span><span class="sxs-lookup"><span data-stu-id="bff7e-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="bff7e-112">Indica un offset da un indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="bff7e-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="bff7e-113">Indica che il primo indirizzo è la parte inferiore di un registro e il secondo indirizzo è la parte alta.</span><span class="sxs-lookup"><span data-stu-id="bff7e-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="bff7e-114">Indica che il primo indirizzo è la parte inferiore di un registro, il secondo è la parte superiore e il terzo è un offset.</span><span class="sxs-lookup"><span data-stu-id="bff7e-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="bff7e-115">Indica che il primo indirizzo è un registro, il secondo è un offset e il terzo è la parte superiore del registro.</span><span class="sxs-lookup"><span data-stu-id="bff7e-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="bff7e-116">Indica che il primo indirizzo è l'inizio di un campo e il secondo indirizzo è la lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="bff7e-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="bff7e-117">Indica che il primo indirizzo è la sezione e il secondo indirizzo è un offset.</span><span class="sxs-lookup"><span data-stu-id="bff7e-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bff7e-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bff7e-118">Requirements</span></span>  
 <span data-ttu-id="bff7e-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bff7e-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff7e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bff7e-120">See also</span></span>

- [<span data-ttu-id="bff7e-121">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="bff7e-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
