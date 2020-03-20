---
title: Enumerazione CorSymSearchPolicyAttributes
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178340"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="73185-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="73185-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="73185-103">Specifica il criterio da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="73185-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="73185-104">Queste costanti vengono utilizzate dai metodi [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="73185-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="73185-105">È un rischio per la sicurezza aprire un file di database di programma (PDB) da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="73185-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73185-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73185-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="73185-107">Members</span><span class="sxs-lookup"><span data-stu-id="73185-107">Members</span></span>  
  
|<span data-ttu-id="73185-108">Membro</span><span class="sxs-lookup"><span data-stu-id="73185-108">Member</span></span>|<span data-ttu-id="73185-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73185-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="73185-110">Esegue una query nel Registro di sistema per i percorsi di ricerca dei simboli.</span><span class="sxs-lookup"><span data-stu-id="73185-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="73185-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="73185-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="73185-112">Cerca il percorso specificato nella directory Debug.</span><span class="sxs-lookup"><span data-stu-id="73185-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="73185-113">Cerca il file PDB nel punto in cui si trova il file .exe.</span><span class="sxs-lookup"><span data-stu-id="73185-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73185-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73185-114">Requirements</span></span>  
 <span data-ttu-id="73185-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73185-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73185-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73185-116">See also</span></span>

- [<span data-ttu-id="73185-117">Enumerazioni dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="73185-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
