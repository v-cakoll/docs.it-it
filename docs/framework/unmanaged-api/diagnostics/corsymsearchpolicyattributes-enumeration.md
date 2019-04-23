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
ms.openlocfilehash: 8a9b0f085820bac12638c0310ab23b2eafacb23b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186173"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="dd58a-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="dd58a-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="dd58a-103">Specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="dd58a-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="dd58a-104">Queste costanti vengono utilizzate per la [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="dd58a-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd58a-105">È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="dd58a-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd58a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd58a-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="dd58a-107">Membri</span><span class="sxs-lookup"><span data-stu-id="dd58a-107">Members</span></span>  
  
|<span data-ttu-id="dd58a-108">Member</span><span class="sxs-lookup"><span data-stu-id="dd58a-108">Member</span></span>|<span data-ttu-id="dd58a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd58a-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="dd58a-110">Esegue una query il Registro di sistema per i percorsi di ricerca simbolo.</span><span class="sxs-lookup"><span data-stu-id="dd58a-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="dd58a-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="dd58a-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="dd58a-112">Cerca nel percorso specificato nella directory di Debug.</span><span class="sxs-lookup"><span data-stu-id="dd58a-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="dd58a-113">Cerca il file PDB nel punto in cui il file .exe è.</span><span class="sxs-lookup"><span data-stu-id="dd58a-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd58a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd58a-114">Requirements</span></span>  
 <span data-ttu-id="dd58a-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dd58a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd58a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd58a-116">See also</span></span>

- [<span data-ttu-id="dd58a-117">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="dd58a-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
