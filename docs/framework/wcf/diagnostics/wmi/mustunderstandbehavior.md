---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 14150a992130e9ed4734c950d4ed92f1bbd3206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485557"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="d81ea-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="d81ea-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="d81ea-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="d81ea-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d81ea-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d81ea-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d81ea-105">Methods</span></span>  
 <span data-ttu-id="d81ea-106">La classe MustUnderstandBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="d81ea-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d81ea-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d81ea-107">Properties</span></span>  
 <span data-ttu-id="d81ea-108">La classe MustUnderstandBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="d81ea-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="d81ea-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="d81ea-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="d81ea-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="d81ea-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d81ea-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d81ea-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d81ea-112">Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d81ea-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81ea-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d81ea-113">Requirements</span></span>  
  
|<span data-ttu-id="d81ea-114">MOF</span><span class="sxs-lookup"><span data-stu-id="d81ea-114">MOF</span></span>|<span data-ttu-id="d81ea-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d81ea-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d81ea-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d81ea-116">Namespace</span></span>|<span data-ttu-id="d81ea-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d81ea-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d81ea-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d81ea-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
