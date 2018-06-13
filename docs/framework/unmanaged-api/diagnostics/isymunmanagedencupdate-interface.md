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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05cbe098b73dd817546dd72f0fc98ad548f75386
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425418"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="e22f8-102">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="e22f8-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="e22f8-103">Fornisce funzioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="e22f8-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e22f8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e22f8-104">Methods</span></span>  
  
|<span data-ttu-id="e22f8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e22f8-105">Method</span></span>|<span data-ttu-id="e22f8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e22f8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e22f8-107">Metodo GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="e22f8-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="e22f8-108">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="e22f8-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="e22f8-109">Metodo GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="e22f8-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="e22f8-110">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="e22f8-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="e22f8-111">Metodo InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="e22f8-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="e22f8-112">Consente di calcolare i limiti del metodo prima della prima chiamata al [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="e22f8-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="e22f8-113">Metodo UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="e22f8-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="e22f8-114">Consente l'aggiornamento delle informazioni di riga per un metodo che non è stato ricompilato, ma le cui righe sono stati spostati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="e22f8-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="e22f8-115">È consentito un delta per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="e22f8-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="e22f8-116">Metodo UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="e22f8-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="e22f8-117">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) di database, purché le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="e22f8-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="e22f8-118">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="e22f8-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e22f8-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e22f8-119">Requirements</span></span>  
 <span data-ttu-id="e22f8-120">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e22f8-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22f8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e22f8-121">See Also</span></span>  
 [<span data-ttu-id="e22f8-122">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e22f8-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
