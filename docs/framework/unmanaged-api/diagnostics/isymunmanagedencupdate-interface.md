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
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501742"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="eb865-102">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="eb865-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="eb865-103">Fornisce funzioni per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="eb865-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb865-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="eb865-104">Methods</span></span>  
  
|<span data-ttu-id="eb865-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="eb865-105">Method</span></span>|<span data-ttu-id="eb865-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb865-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb865-107">Metodo GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="eb865-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="eb865-108">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="eb865-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="eb865-109">Metodo GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="eb865-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="eb865-110">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="eb865-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="eb865-111">Metodo InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="eb865-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="eb865-112">Consente il calcolo dei limiti del metodo prima della prima chiamata al metodo [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb865-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="eb865-113">Metodo UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="eb865-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="eb865-114">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono state spostate in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="eb865-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="eb865-115">È consentito un Delta per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="eb865-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="eb865-116">Metodo UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="eb865-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="eb865-117">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso del database di programma (PDB), purché le informazioni sulla riga soddisfino i requisiti.</span><span class="sxs-lookup"><span data-stu-id="eb865-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="eb865-118">Le informazioni sulla riga corrette possono essere determinate con le informazioni sulla riga PDB precedenti e un Delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="eb865-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb865-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb865-119">Requirements</span></span>  
 <span data-ttu-id="eb865-120">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eb865-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb865-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb865-121">See also</span></span>

- [<span data-ttu-id="eb865-122">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="eb865-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
