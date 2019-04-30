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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939698"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="6131d-102">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="6131d-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="6131d-103">Fornisce funzioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="6131d-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6131d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6131d-104">Methods</span></span>  
  
|<span data-ttu-id="6131d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6131d-105">Method</span></span>|<span data-ttu-id="6131d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6131d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6131d-107">Metodo GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="6131d-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="6131d-108">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6131d-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="6131d-109">Metodo GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="6131d-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="6131d-110">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6131d-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="6131d-111">Metodo InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="6131d-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="6131d-112">Consente i limiti del metodo deve essere calcolata prima della prima chiamata per il [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="6131d-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="6131d-113">Metodo UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="6131d-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="6131d-114">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono spostati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="6131d-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="6131d-115">Valore delta di ogni istruzione è consentito.</span><span class="sxs-lookup"><span data-stu-id="6131d-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="6131d-116">Metodo UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="6131d-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="6131d-117">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) del database, condizione che le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="6131d-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="6131d-118">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe della funzione.</span><span class="sxs-lookup"><span data-stu-id="6131d-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6131d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6131d-119">Requirements</span></span>  
 <span data-ttu-id="6131d-120">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6131d-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6131d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6131d-121">See also</span></span>

- [<span data-ttu-id="6131d-122">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="6131d-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
