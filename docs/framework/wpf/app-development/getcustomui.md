---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005717"
---
# <a name="getcustomui"></a><span data-ttu-id="98eea-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="98eea-102">GetCustomUI</span></span>
<span data-ttu-id="98eea-103">Chiamato da PresentationHost. exe per ottenere i messaggi di errore e di stato personalizzati dall'host, se implementati.</span><span class="sxs-lookup"><span data-stu-id="98eea-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98eea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98eea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="98eea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98eea-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="98eea-106">out Puntatore all'assembly che contiene l'interfaccia utente di avanzamento fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="98eea-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="98eea-107">out Il nome della classe che rappresenta l'interfaccia utente di avanzamento fornita dall'host, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> è il relativo elemento di livello principale.</span><span class="sxs-lookup"><span data-stu-id="98eea-107">[out] The name of the class that is the host-supplied progress user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="98eea-108">Questa classe risiede nell'assembly specificato da `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="98eea-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="98eea-109">out Puntatore all'assembly che contiene l'interfaccia utente degli errori fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="98eea-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="98eea-110">out Il nome della classe che rappresenta l'interfaccia utente degli errori fornita dall'host, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> è il relativo elemento di livello principale.</span><span class="sxs-lookup"><span data-stu-id="98eea-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="98eea-111">Questa classe risiede nell'assembly specificato da `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="98eea-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="98eea-112">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98eea-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="98eea-113">HRESULT: Ignorato.</span><span class="sxs-lookup"><span data-stu-id="98eea-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98eea-114">Note</span><span class="sxs-lookup"><span data-stu-id="98eea-114">Remarks</span></span>  
 <span data-ttu-id="98eea-115">Un'applicazione host può presentare un tema specifico a cui le interfacce utente predefinite di PresentationHost. exe potrebbero non essere conformi.</span><span class="sxs-lookup"><span data-stu-id="98eea-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="98eea-116">In tal caso, l'applicazione host può implementare [GetCustomUI](getcustomui.md) per restituire le interfacce utente di stato e di errore in PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="98eea-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="98eea-117">PresentationHost. exe chiamerà sempre [GetCustomUI](getcustomui.md) prima di usare le interfacce utente predefinite.</span><span class="sxs-lookup"><span data-stu-id="98eea-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="98eea-118">Questa funzione viene chiamata una sola volta durante l'inizializzazione di PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="98eea-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98eea-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98eea-119">See also</span></span>

- [<span data-ttu-id="98eea-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="98eea-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
