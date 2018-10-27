---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 0f3efc446104a1afff507f6e7d2cd8c01c4ed417
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452599"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="7a489-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="7a489-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="7a489-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="7a489-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a489-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a489-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7a489-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7a489-105">Methods</span></span>  
 <span data-ttu-id="7a489-106">La classe MustUnderstandBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="7a489-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7a489-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7a489-107">Properties</span></span>  
 <span data-ttu-id="7a489-108">La classe MustUnderstandBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="7a489-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="7a489-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="7a489-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="7a489-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="7a489-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a489-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7a489-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a489-112">Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7a489-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a489-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a489-113">Requirements</span></span>  
  
|<span data-ttu-id="7a489-114">MOF</span><span class="sxs-lookup"><span data-stu-id="7a489-114">MOF</span></span>|<span data-ttu-id="7a489-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7a489-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7a489-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7a489-116">Namespace</span></span>|<span data-ttu-id="7a489-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7a489-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a489-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a489-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
