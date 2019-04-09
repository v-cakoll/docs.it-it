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
ms.openlocfilehash: 378322c28d59b2a6e7c09f2f2c4bf55bb019d01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171840"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="c2dff-102">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="c2dff-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="c2dff-103">Fornisce funzioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="c2dff-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2dff-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2dff-104">Methods</span></span>  
  
|<span data-ttu-id="c2dff-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c2dff-105">Method</span></span>|<span data-ttu-id="c2dff-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2dff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2dff-107">Metodo GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="c2dff-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="c2dff-108">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="c2dff-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="c2dff-109">Metodo GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="c2dff-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="c2dff-110">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="c2dff-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="c2dff-111">Metodo InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="c2dff-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="c2dff-112">Consente i limiti del metodo deve essere calcolata prima della prima chiamata per il [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c2dff-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="c2dff-113">Metodo UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="c2dff-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="c2dff-114">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono spostati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c2dff-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="c2dff-115">Valore delta di ogni istruzione è consentito.</span><span class="sxs-lookup"><span data-stu-id="c2dff-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="c2dff-116">Metodo UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="c2dff-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="c2dff-117">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) del database, condizione che le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="c2dff-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="c2dff-118">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe della funzione.</span><span class="sxs-lookup"><span data-stu-id="c2dff-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2dff-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2dff-119">Requirements</span></span>  
 <span data-ttu-id="c2dff-120">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2dff-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2dff-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2dff-121">See also</span></span>

- [<span data-ttu-id="c2dff-122">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c2dff-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
