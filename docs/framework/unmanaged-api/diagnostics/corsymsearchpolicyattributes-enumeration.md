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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29766636cd151744d25cf66deb60cd2e066e1b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775786"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="de718-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="de718-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="de718-103">Specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="de718-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="de718-104">Queste costanti vengono utilizzate per la [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="de718-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="de718-105">È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="de718-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de718-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de718-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="de718-107">Membri</span><span class="sxs-lookup"><span data-stu-id="de718-107">Members</span></span>  
  
|<span data-ttu-id="de718-108">Member</span><span class="sxs-lookup"><span data-stu-id="de718-108">Member</span></span>|<span data-ttu-id="de718-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de718-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="de718-110">Esegue una query il Registro di sistema per i percorsi di ricerca simbolo.</span><span class="sxs-lookup"><span data-stu-id="de718-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="de718-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="de718-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="de718-112">Cerca nel percorso specificato nella directory di Debug.</span><span class="sxs-lookup"><span data-stu-id="de718-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="de718-113">Cerca il file PDB nel punto in cui il file .exe è.</span><span class="sxs-lookup"><span data-stu-id="de718-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de718-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de718-114">Requirements</span></span>  
 <span data-ttu-id="de718-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="de718-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de718-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de718-116">See also</span></span>

- [<span data-ttu-id="de718-117">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="de718-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
