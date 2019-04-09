---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165475"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="70517-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="70517-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="70517-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="70517-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70517-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70517-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="70517-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="70517-105">Methods</span></span>  
 <span data-ttu-id="70517-106">La classe MustUnderstandBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="70517-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="70517-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="70517-107">Properties</span></span>  
 <span data-ttu-id="70517-108">La classe MustUnderstandBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="70517-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="70517-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="70517-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="70517-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="70517-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="70517-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="70517-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70517-112">Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="70517-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70517-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="70517-113">Requirements</span></span>  
  
|<span data-ttu-id="70517-114">MOF</span><span class="sxs-lookup"><span data-stu-id="70517-114">MOF</span></span>|<span data-ttu-id="70517-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="70517-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="70517-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="70517-116">Namespace</span></span>|<span data-ttu-id="70517-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="70517-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70517-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70517-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
