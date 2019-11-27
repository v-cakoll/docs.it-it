---
title: Interfaccia ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: f3305a7bb003fc50f772f1100f8a17d385e4d5fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449014"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="b5d13-102">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="b5d13-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="b5d13-103">Fornisce funzioni per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="b5d13-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5d13-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b5d13-104">Methods</span></span>  
  
|<span data-ttu-id="b5d13-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b5d13-105">Method</span></span>|<span data-ttu-id="b5d13-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5d13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5d13-107">Metodo GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="b5d13-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="b5d13-108">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="b5d13-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="b5d13-109">Metodo GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="b5d13-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="b5d13-110">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="b5d13-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="b5d13-111">Metodo InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="b5d13-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="b5d13-112">Consente il calcolo dei limiti del metodo prima della prima chiamata al metodo [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5d13-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="b5d13-113">Metodo UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="b5d13-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="b5d13-114">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono state spostate in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="b5d13-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="b5d13-115">È consentito un Delta per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="b5d13-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="b5d13-116">Metodo UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="b5d13-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="b5d13-117">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso del database di programma (PDB), purché le informazioni sulla riga soddisfino i requisiti.</span><span class="sxs-lookup"><span data-stu-id="b5d13-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="b5d13-118">Le informazioni sulla riga corrette possono essere determinate con le informazioni sulla riga PDB precedenti e un Delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="b5d13-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5d13-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5d13-119">Requirements</span></span>  
 <span data-ttu-id="b5d13-120">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b5d13-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d13-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5d13-121">See also</span></span>

- [<span data-ttu-id="b5d13-122">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="b5d13-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
